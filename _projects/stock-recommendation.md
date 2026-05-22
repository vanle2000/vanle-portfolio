---
title: "Stock Recommendation System"
category: "Data Engineering & ML"
tags: ["PySpark", "TensorFlow", "FastAPI", "LinearSVR", "Autoencoder", "Docker", "Walk-forward CV", "PCA"]
result: "LinearSVR R²=0.997 under walk-forward CV · FastAPI production service · 45 tests"
github: "https://github.com/vanle2000/Stock-based-Recommendation-System"
---

## The Problem

Building a stock recommendation system has two distinct challenges that most toy implementations conflate:

1. **Price prediction**: given a stock's technical indicators today, predict tomorrow's closing price
2. **Stock similarity**: given a portfolio holding, find other stocks that behave similarly across market regimes

Both problems are technically interesting. Both are also easy to do wrong — and the wrong version produces metrics that look impressive while being meaningless (or worse, misleading in production).

## The Data Leakage Problem

The first version of this system used a standard 80/20 train/test split and reported **R² = 0.997** for LinearSVR price prediction. That number is real — and completely misleading.

Time-series data has temporal structure. If you train on 2018–2023 data and test on randomly shuffled samples from the same period, the model has seen the future. Financial time series are highly autocorrelated — yesterday's price is the strongest predictor of today's price. A standard split lets the model learn this leak.

**Fix: Walk-Forward Validation**

```python
TimeSeriesSplit(n_splits=5, gap=1)
```

- Each fold trains on data ending at time T and tests on data starting at T+1
- The `gap=1` parameter prevents look-ahead leakage at fold boundaries
- Rolling window ensures the model is always evaluated on data it couldn't have seen

R² under walk-forward CV: still very high (the features genuinely carry signal), but now interpretable.

## Architecture

### Layer 1: PySpark Data Pipeline

**10M+ OHLCV records across 3,600+ NASDAQ tickers**, merged with ticker metadata (sector, industry, market cap).

Technical indicators engineered per ticker:

| Category | Indicators |
|----------|-----------|
| Trend | SMA(20), SMA(50), EMA(12), EMA(26), MACD, Signal Line |
| Momentum | RSI(14), Stochastic Oscillator |
| Volatility | Bollinger Bands (upper/lower/width), ATR(14) |
| Volume | OBV, Volume SMA |
| Japanese | Ichimoku Cloud (Tenkan, Kijun, Senkou A/B) |

20+ features → PCA compression to 5 principal components. PCA fitted on training data only; test data projected using training PCA (no leakage).

### Layer 2: Price Prediction (LinearSVR)

LinearSVR selected over neural networks for this task: the feature space is small (5 PCA components), the relationships are roughly linear in log-returns, and LinearSVR is interpretable and fast to retrain.

- Target: next-day normalized closing price
- Features: 5 PCA components of technical indicators
- Evaluation: walk-forward CV with `gap=1`

### Layer 3: Recommendation Engine (Autoencoder)

A deep learning autoencoder encodes each stock's behavioral profile into a **latent vector** — a compressed representation of how it moves across market regimes.

Architecture: `Input(5) → Dense(32) → Dense(16) → Dense(8) → Dense(16) → Dense(32) → Output(5)`

Recommendations use **cosine similarity** between latent vectors. Two stocks are "similar" if they behave alike in latent space — not just if they're in the same sector.

**Offline evaluation** (since we can't A/B test in a simulation):
- Ground truth: forward return correlation over the next 30 days
- `Precision@5`: fraction of top-5 recommendations that are in the true top-5 correlated stocks
- `NDCG@5`: ranking-aware metric (being right in position 1 is worth more than position 5)
- `Correlation lift vs. random`: does the model's top-5 have higher average forward correlation than 5 randomly selected stocks?

### Layer 4: FastAPI Production Service

```
GET  /health          → service status + model version
GET  /metrics         → offline evaluation scores
POST /predict         → price prediction from 5 PCA features
POST /recommend       → top-N similar stocks with similarity scores
```

Docker containerized. Pydantic request/response validation. CORS middleware for browser clients.

## Testing

45 tests covering:

```
tests/
├── test_pipeline.py       ← PySpark schema validation, indicator calculation bounds
├── test_timeseries_cv.py  ← fold ordering, gap enforcement, no-leakage assertions
├── test_recommender.py    ← precision@K shape, NDCG monotonicity, similarity bounds
└── test_api.py            ← FastAPI endpoint contracts, validation errors
```

## What Would Be Explored Next

- Replace LinearSVR with a Temporal Fusion Transformer — designed for multi-horizon time-series forecasting with attention-based feature importance
- Add market regime detection (HMM or change-point detection) so recommendations adapt during high-volatility periods
- Replace cosine similarity with a learned similarity metric using contrastive learning — stocks that tend to move together in real portfolios as positive pairs
- Add real-time streaming via Kafka + Flink for live indicator updates during market hours
