---
title: "Marathon Performance Analysis"
category: "Statistical ML & Sports Analytics"
tags: ["SciPy KDE", "Bayes Theorem", "KNN", "Linear Regression", "SGD", "Python", "NumPy"]
result: "2-D KDE accuracy=77.5% · Linear regression R²=0.85 · 26 unit tests"
github: "https://github.com/vanle2000/Analysis-marathon-result-and-predict-performance-of-runners"
---

## The Problem

Boston Marathon data contains 26,000 runners with split times, finish times, gender, and age. The intuitive assumption  -  that age and gender significantly improve finish time prediction  -  turns out to be empirically weak once early split performance is known.

This project addresses two questions with different modeling approaches:

1. **Classification**: Can we predict a runner's gender from their performance profile? How much does adding the time dimension (2-D KDE vs. 1-D KDE) matter?
2. **Regression**: What is the minimum set of features needed to accurately predict finish time? Does adding demographic information actually help?

## Custom KDEBayesClassifier

The gender classifier is built from scratch  -  no scikit-learn classifier. It implements Bayes' theorem using **Gaussian Kernel Density Estimation** as the likelihood function:

```python
P(Gender | FinishTime, Age) ∝ P(FinishTime, Age | Gender) × P(Gender)
```

Where `P(FinishTime, Age | Gender)` is estimated via 2-D KDE over the training population for each gender class. This is a probabilistic, non-parametric approach  -  it doesn't assume any distribution shape and naturally handles the multi-modal finish time distributions that appear in marathon data.

**Custom sklearn-compatible implementation**: `KDEBayesClassifier` follows the `fit(X, y)` / `predict(X)` / `predict_proba(X)` interface. This means it works inside `cross_val_score`, `GridSearchCV`, and pipelines.

## 1-D vs. 2-D KDE: Why Dimensionality Matters

| Classifier | Accuracy |
|------------|----------|
| 1-D KDE (finish time only) | ~65.5% |
| **2-D KDE (finish time + age)** | **77.5%** |
| KNN baseline | ~71% |

Adding age lifts accuracy by **12 percentage points**. The intuition: men and women have statistically different age-performance curves. A 25-year-old woman with a 3:45 finish is in a different part of the distribution than a 55-year-old woman with the same finish time. 1-D KDE treats them identically; 2-D KDE separates them.

## Finish Time Prediction

Linear regression from the **5K split time** alone:

- **R² = 0.85** with a single feature
- Adding age and gender: R² improves by only 0.02–0.03

This is itself the key finding: **early pacing is almost entirely determinative**. A runner's 5K split captures their fitness level, their chosen pace strategy, and their environmental conditions  -  adding demographic variables adds almost no information once you know how they ran the first 5 kilometers.

The regression was fit with both ordinary least squares and **SGD (stochastic gradient descent)** to validate convergence  -  results are identical, confirming the OLS solution is correct.

## Testing

**26 unit tests** covering:

```
tests/
├── test_preprocessing.py    ← dtype checks, missing value handling, outlier bounds
├── test_classifier.py       ← KDE fitting, prediction shape, bandwidth sensitivity
└── test_regression.py       ← R² threshold assertions, coefficient sign checks
```

Testing a custom ML implementation is non-trivial  -  the tests validate that the KDE integrates to approximately 1.0 across the feature space (probabilistic consistency check) and that predicted probabilities sum to 1 per sample.

## Key Insights

- **Pacing discipline, not demographics, determines finish time**  -  a runner who goes out too fast in the first 5K sees compounding degradation that demographics cannot predict away
- **Boston's qualifying standard** creates a selection effect: the age-performance curves are compressed compared to a general marathon because slow runners aren't present
- **Men's and women's distributions overlap significantly** in the 3:30–4:30 range  -  any single-feature classifier will have high error in this region regardless of sophistication

## What Would Be Explored Next

- Model the time series of splits (5K, 10K, 15K...) with a sequence model to detect "blow-up" events earlier in the race
- Apply the KDEBayes approach to multi-class classification (age group) rather than binary gender  -  requires extending to joint 3-D KDE
- Investigate whether the 5K→finish R²=0.85 holds at the elite tier (sub-3:00) or whether elite performance is qualitatively different
