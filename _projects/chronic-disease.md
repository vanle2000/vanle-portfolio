---
title: "Chronic Disease Risk Intelligence"
category: "ML & Predictive Modeling"
tags: ["Random Forest", "KMeans", "GeoPandas", "Plotly", "Scikit-learn", "CDC Data", "Python"]
result: "Silhouette=0.635 · Mortality AUC=0.73 · Macro F1=0.85 (not 0.9999 raw accuracy)"
github: "https://github.com/vanle2000/Chronic-disease-risks-in-US"
---

## The Problem

Chronic diseases — diabetes, cardiovascular disease, COPD, cancer — drive the majority of US healthcare costs and preventable deaths. The CDC has tracked these conditions across all 50 states for 20 years, but the data is rarely used at a strategic level to answer: **Which states are structurally different in their disease burden, and what interventions would actually move the numbers?**

Off-the-shelf dashboards summarize. This project builds a classification and clustering system that finds structure, predicts outcomes, and — critically — uses honest evaluation metrics rather than ones that look impressive on imbalanced data.

## Dataset

CDC Chronic Disease Indicators (CDI): **900K+ records across all 50 states, 2001–2021.** Each record is a state × disease × year × demographic cell with a reported indicator value (rate per 100K, percentage, etc.).

The scale requires careful memory management and selective column loading — raw ingest would OOM a standard notebook.

## What Was Built

**Clustering: What Kind of State Is This?**

K-Means clustering on row-normalized disease profiles at the state level (normalized to account for population differences). The goal: find groups of states that share disease burden structure, not just geography.

- Optimal K selected via silhouette score sweep
- **Silhouette score = 0.635** (K=4 clusters) — strong, interpretable separation
- Four clusters map to recognizable public health archetypes: rural high-burden, urban mixed, southern chronic, coastal low-burden

Visualized with GeoPandas choropleth — each state colored by cluster assignment.

**Mortality Prediction: Logistic Regression**

Binary target: above/below median mortality rate per state-disease cell. Features: disease indicators, demographic breakdowns, year trend.

- **AUC = 0.73** — better than chance by a meaningful margin on a genuinely hard prediction task
- Reporting AUC rather than accuracy because the target is not perfectly balanced

**Multi-Class Risk Classification: Random Forest**

Five-tier risk labels (derived from indicator percentile ranks): Very Low / Low / Medium / High / Very High.

| Metric | Value |
|--------|-------|
| Raw accuracy | ~99% |
| **Macro F1** | **0.85** |

The raw accuracy is 0.9999 on some runs. That's not interesting — it's an artifact of class imbalance in a 900K-row dataset where most cells fall into the same tier. **Macro F1 = 0.85 is the honest number**: it weights each class equally and penalizes failures on rare tiers.

## Honest Evaluation Stance

Most Kaggle notebooks would report the 0.9999 accuracy and call it done. This project explicitly comments out the raw accuracy in the report and leads with macro F1. The distinction matters: a model that assigns every cell the majority class achieves 90%+ accuracy while being useless for identifying high-risk states.

## Key Findings

- **Southern states (MS, WV, AL, LA)** cluster together with the highest chronic disease burden across all indicators — not just in absolute rates but in the *combination* of conditions (co-morbidity structure)
- **Cardiovascular disease indicators** are the strongest predictors of the high-risk tier across all demographic breakdowns
- **20-year trend**: the nationwide distribution is shifting — medium-risk states are gaining high-risk characteristics faster than interventions are reducing high-risk state counts
- **Demographic breakdowns reveal hidden variance**: states that look average overall often have extreme within-state racial disparities in specific disease rates

## What Would Be Explored Next

- Replace K-Means with Gaussian Mixture Models to get soft cluster assignments (a state is 60% rural-burden, 40% southern-chronic) — more realistic for policy targeting
- Add interrupted time series analysis to evaluate whether specific policy interventions (Medicaid expansion, tobacco taxes) caused measurable slope changes
- Build Tableau Public dashboard: state-level choropleth with 20-year trend lines and demographic breakdowns (currently in progress)
- Extend to causal inference: estimate counterfactual outcomes for high-burden states under different intervention mixes
