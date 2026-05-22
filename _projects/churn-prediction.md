---
title: "Customer Churn Prediction"
category: "ML & Predictive Modeling"
tags: ["XGBoost", "SMOTE", "SHAP", "Scikit-learn", "Precision@K", "Python", "Pandas"]
result: "Precision@10%≈67% · Positive ROI at $50 intervention · SHAP attribution per customer"
github: "https://github.com/vanle2000/Churn-Predictive-Modeling"
---

## The Problem

Customer acquisition costs 5–7× more than retention. Yet most companies only act after a customer is already gone.

Standard churn models optimize for accuracy or AUC on imbalanced datasets  -  that's the wrong objective. A model that achieves 95% accuracy on a dataset where 85% of customers stay has learned to always predict "no churn." It captures no value.

The real business questions are:
- Which customers are in the top decile of churn risk **right now**?
- What is the expected revenue impact of reaching out to them?
- Which product signals are driving their individual risk?

## Dataset

IBM Telco Customer Churn dataset: **7,043 customers, 21 features**. Target imbalance: ~26% churners vs. 74% retained  -  significant enough to invalidate raw accuracy as a metric.

## Pipeline

**Feature Engineering**

Raw features augmented with business-derived signals:
- Tenure buckets (early/mid/mature customer lifecycle)
- Charge volatility (monthly vs. total charges ratio)
- Service adoption breadth (count of active services)
- Billing behavior flags (paperless billing, payment method)

**Model Selection**

Three models compared under identical evaluation protocol:

| Model | ROC-AUC | Precision@10% | Net ROI (top 20%) |
|-------|---------|--------------|-------------------|
| Logistic Regression | ~0.84 | ~0.62 | Positive |
| Random Forest | ~0.86 | ~0.65 | Positive |
| XGBoost + SMOTE | ~0.87 | ~0.67 | Highest |

SMOTE applied to the training fold only within each stratified CV split  -  no data leakage.

**Evaluation Framework**

The evaluation is built around the business intervention, not the model:

```python
# Business ROI simulation
def business_roi(y_true, y_prob, intervention_cost=50, revenue_saved=500, k=0.20):
    top_k = y_prob.argsort()[-int(len(y_prob) * k):]
    tp = y_true.iloc[top_k].sum()
    revenue = tp * revenue_saved
    cost = len(top_k) * intervention_cost
    return revenue - cost
```

At `k=0.10` (top 10% targeted): ~67% true churners captured, ROI positive at $50 per outreach.

**SHAP Explainability**

Every customer in the high-risk segment gets a waterfall SHAP plot explaining exactly which features pushed their score up or down. This is what makes the output actionable for a CRM or retention team  -  not just a ranked list, but a reason.

## Key Insights

- **Tenure is the dominant signal**: customers in months 1–12 churn at 3× the rate of customers past month 24
- **Month-to-month contracts** carry the single highest SHAP value for churn risk
- **Fiber optic users** with high monthly charges and no tech support are the highest-risk segment
- **Adding online security or backup services** is negatively correlated with churn  -  retention programs that bundle these services have an identifiable effect

## Architecture

```
data/raw/          ← telco_churn.csv
data/processed/    ← churn_processed.parquet
src/data/          ← preprocessing.py (clean → encode → engineer_features)
src/models/        ← train.py (CV + evaluation) · evaluate.py (SHAP + ROI curves)
models/            ← best_model.joblib
reports/figures/   ← shap_summary.png · roi_curve.png · calibration.png
```

Run with: `make data && make train`

## What Would Be Explored Next

- Add calibration (isotonic regression / Platt scaling) so predicted probabilities reflect true churn rates  -  enabling revenue forecasting, not just ranking
- Replace static holdout with rolling-window evaluation to detect model drift over time
- Extend SHAP to cluster customers by *reason for churn* (price-sensitive vs. service-quality vs. engagement-driven) to support differentiated retention plays
- Integrate with CRM API to auto-generate retention task queue ranked by expected ROI
