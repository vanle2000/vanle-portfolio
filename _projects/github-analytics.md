---
title: "GitHub Support Operations Analytics"
category: "Business Intelligence Engineering"
tags: ["SQL Server", "SQLAlchemy", "VADER NLP", "Power BI", "Star Schema", "ETL", "Python", "Azure Data Studio"]
result: "12-hour response threshold predicts 3.5x lift in repeat contributor rate · 12% of repos identified as toxic"
github: "https://github.com/vanle2000/GitHub-support-operations-analytics"
---

## The Problem

GitHub hosts 100M+ repositories and processes millions of developer support interactions every year. When a developer files an issue, how quickly it gets addressed determines whether they contribute again — or quietly disappear.

Support teams had no systematic way to:
- Identify which repositories were consistently breaching SLA thresholds (>24h first response)
- Measure whether a ticket resolution left the developer more or less frustrated than when they started
- Predict which currently-open tickets were at highest risk before it happened
- Connect support performance metrics to contributor retention outcomes

Without this visibility, high-traffic repositories were experiencing unmeasured developer churn — contributors who filed one issue, got a slow or frustrating response, and never came back.

## Architecture

The platform integrates three layers: a star schema data warehouse, VADER NLP sentiment tracking, and a real-time SLA risk scoring model.

**Star Schema Data Warehouse**

Designed in SQL Server / Azure Data Studio with five core tables:

| Table | Description |
|-------|-------------|
| `Fact_Tickets` | One row per issue — timestamps, resolution status, TTFR |
| `Dim_Repositories` | Repo metadata, health score, contributor tier |
| `Dim_Authors` | Contributor history, retention label |
| `Fact_Sentiment` | Initial + final sentiment per ticket, shift delta |
| `Risk_Scores` | Hourly breach probability scores with timestamp |

The ETL pipeline (Python + SQLAlchemy + pyodbc) ingests raw GitHub issue metadata, normalizes 50+ raw label tags into 4 business categories, and loads into the warehouse with full referential integrity.

**VADER Sentiment Tracking**

VADER was selected over transformer-based models for its high performance on technical shorthand and short-form text — at a fraction of the compute cost.

- `Initial_Sentiment`: scored from first issue body text
- `Final_Sentiment`: scored from last comment before close
- `Sentiment_Shift` = Final − Initial: measures emotional trajectory across the ticket lifecycle
- "Frustrated user" flag: tickets where initial ≥ 0 and final < −0.5

This allows the dashboard to surface which repositories are *worsening* user sentiment even when issues technically get resolved.

**Real-Time SLA Risk Model**

All open tickets scored every hour:

```
Breach_Probability = (Time_Risk × 0.5) + (Comment_Risk × 0.3) + (Label_Weight × 0.2)
```

- **Time_Risk**: hours elapsed ÷ 24h SLA threshold
- **Comment_Risk**: each additional comment adds 5% complexity risk (capped at 40%)
- **Label_Weight**: security/vulnerability = 1.5×, critical-bug = 1.4×, enhancement = 0.3×

Five tiers: CRITICAL / HIGH / MEDIUM / LOW / MINIMAL — stored with timestamp for trend analysis.

## Power BI Dashboard

Three report pages, each designed for a different audience:

- **Executive Pulse** — real-time SLA achievement rate and retention trends (C-suite)
- **Toxic Repo Health Map** — quadrant scatter: response time vs. retention rate per repository
- **Contributor Funnel** — conversion from first-time author → repeat contributor → maintainer

The Health Score formula driving the quadrant:

```
Score = (Retention × 0.5) + (SLAMet × 0.3) − (ResolutionTime × 0.2)
```

## Results

| Finding | Metric |
|---------|--------|
| Toxic repositories identified | 12% of high-traffic repos failing SLA and causing measurable churn |
| Golden Hour threshold | Tickets responded within 12h yield **3.5x** more repeat contributors |
| Sentiment volatility trigger | Tickets with >3 comment rounds show **40% increase** in negative sentiment shift |

## What Would Be Explored Next

- Replace the statistical SLA model with an XGBoost classifier trained on historical breach outcomes
- Integrate GitHub REST API live data via Airflow DAG for fully automated ETL
- Add contributor cohort analysis to track retention curves over 30/60/90-day windows
- Deploy dashboard to Power BI Service with row-level security per repository owner
