---
title: "About"
permalink: /about/
layout: single
author_profile: true
toc: false
---

I'm Van Le, a data analyst and scientist based in Houston, TX.

At M&T Tax Firm, I work as a Tax Data Analyst and Business Analyst. Over 1.5 years, I've built reporting pipelines, automated reconciliation workflows, and translated financial records into structured decision support for the tax advisory team. This work sharpened my understanding of when data is reliable, when modeling assumptions fail in production, and what the distance is between a working prototype and something a team depends on daily.

I'm actively looking for my next role in data analytics, business intelligence engineering, or data science. I want to work on problems at scale where the standards for rigor are high and where the output connects to a real decision.

---

## Projects

My independent projects reflect what I find technically interesting: problems with enough structure to model properly and enough scale to make engineering choices matter.

**Stock Recommendation System** processes 10 million OHLCV records across 3,600+ NASDAQ equities using PySpark, 20+ technical indicators (SMA, EMA, RSI, Bollinger Bands, Ichimoku Cloud, ADX, MACD, OBV, ATR), and PCA compression. A deep learning autoencoder encodes each stock's behavioral profile into a latent representation; cosine similarity in this latent space drives content-based recommendations. The price prediction model, LinearSVR, reaches R²=0.997 under walk-forward cross-validation, the correct methodology for sequential data. A standard train-test split on time-series data inflates R² toward 1.0 through lookahead bias; walk-forward validation removes this. The system is deployed as a FastAPI REST service with offline evaluation: Precision@5, NDCG@5, and correlation lift over a Monte Carlo random baseline. A recommendation system with no quality metric is not a recommendation system.

**Customer Churn Prediction** on Telco data (7,043 customers) uses XGBoost with SMOTE augmentation, evaluated through Precision@K and a net ROI simulation rather than raw accuracy. The top 10% of model-scored customers contains approximately 67% true churners. At $50 per customer outreach and $500 revenue recovered per retained churner, this precision produces a measurable positive return. SHAP values attribute risk to specific features per customer, which gives the retention team something actionable beyond a score.

**CDC Chronic Disease Intelligence** analyzes 900,000 surveillance records across 20 years and 50 states. K-Means clustering on row-normalized state disease profiles achieves Silhouette=0.635. A Logistic Regression mortality predictor reaches AUC=0.73. A Random Forest risk classifier achieves macro F1=0.85. The headline metric is macro F1, not the 0.9999 raw accuracy. The raw accuracy is dominated by the Low-risk class (238,000 records versus 3 Very High records); reporting it as the result would misrepresent the model entirely.

**GitHub Support Operations Analytics** is a SQL Server star schema pipeline (ETL via SQLAlchemy) with NLTK/VADER sentiment volatility analysis to flag tickets where user sentiment shifted negative during resolution. A statistical SLA breach probability model scores open tickets in real time across five risk tiers. The analysis identified that first response within 12 hours predicts a 3.5x lift in repeat contributor rate.

**Marathon Performance Analysis** builds a custom `KDEBayesClassifier` using Gaussian KDE fitted separately on male and female finish time distributions, combined with Bayes theorem to estimate P(Female given finish time and age). The 2-D KDE (finish time + age joint distribution) reaches 77.5% gender classification accuracy versus 65.3% for 1-D alone. Linear regression from 5K split achieves R²=0.85; adding age and gender barely moves the number, which is itself a finding: the first 5 kilometers contain most of the predictive signal for marathon finish time.

---

## What I'm working toward

My longer-term interest is in probabilistic modeling, latent variable methods, LLM applications, and AI agentic systems.

I'm not satisfied with black-box accuracy alone. The difference between knowing what a model outputs and understanding what a model has learned matters when the output drives a real decision. Bayesian inference, deep learning latent representations, and interpretable ML are where I spend time outside of work. I want to be in the space where statistical modeling and large-scale data intersect with rigorous uncertainty quantification.

The AI agentic and LLM field is moving fast enough to require consistent foundational investment. I'm building in this direction with purpose, not urgency.

---

## Education

B.A. in Computational and Applied Mathematics, University at Buffalo (2022 to 2023)

Biochemistry and Molecular Biology, University of Houston (2020 to 2022)

A.S. in Chemistry, A.B. in Finance, North Seattle College (2018 to 2020)
