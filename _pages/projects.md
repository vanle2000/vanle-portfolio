---
title: "Projects"
permalink: /projects/
layout: single
author_profile: true
classes: wide
---

<style>
.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
  gap: 1.5rem;
  margin-top: 1.5rem;
}
.project-card {
  border: 1px solid #e0e0e0;
  border-radius: 8px;
  padding: 1.4rem 1.4rem 1.1rem;
  display: flex;
  flex-direction: column;
  background: #fff;
  box-shadow: 0 1px 4px rgba(0,0,0,0.06);
  transition: box-shadow 0.2s ease;
}
.project-card:hover {
  box-shadow: 0 4px 16px rgba(0,0,0,0.12);
}
.project-card h3 {
  margin: 0 0 0.4rem;
  font-size: 1.05rem;
  font-weight: 700;
}
.project-card h3 a {
  text-decoration: none;
  color: inherit;
}
.project-card h3 a:hover { text-decoration: underline; }
.project-problem {
  font-size: 0.82rem;
  color: #666;
  margin: 0 0 0.6rem;
  font-style: italic;
}
.project-desc {
  font-size: 0.88rem;
  color: #333;
  line-height: 1.55;
  flex-grow: 1;
  margin: 0 0 0.8rem;
}
.project-result {
  font-size: 0.82rem;
  font-weight: 600;
  color: #2e7d32;
  background: #f1f8f1;
  border-left: 3px solid #4caf50;
  padding: 0.3rem 0.6rem;
  border-radius: 0 4px 4px 0;
  margin: 0 0 0.9rem;
}
.project-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.3rem;
  margin-bottom: 0.9rem;
}
.tag {
  font-size: 0.72rem;
  padding: 0.15rem 0.55rem;
  border-radius: 12px;
  font-weight: 600;
  letter-spacing: 0.01em;
}
.tag-python  { background: #fff3e0; color: #e65100; }
.tag-ml      { background: #e8f5e9; color: #2e7d32; }
.tag-sql     { background: #e3f2fd; color: #1565c0; }
.tag-nlp     { background: #f3e5f5; color: #6a1b9a; }
.tag-dl      { background: #fce4ec; color: #880e4f; }
.tag-viz     { background: #e0f7fa; color: #006064; }
.tag-api     { background: #fff8e1; color: #f57f17; }
.tag-spark   { background: #efebe9; color: #4e342e; }
.btn-github {
  display: inline-flex;
  align-items: center;
  gap: 0.35rem;
  font-size: 0.8rem;
  font-weight: 600;
  padding: 0.35rem 0.9rem;
  border: 1.5px solid #333;
  border-radius: 5px;
  color: #333;
  text-decoration: none;
  margin-top: auto;
  width: fit-content;
  transition: background 0.15s;
}
.btn-github:hover {
  background: #333;
  color: #fff;
  text-decoration: none;
}
.section-label {
  font-size: 0.75rem;
  font-weight: 700;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  color: #888;
  margin: 2.5rem 0 0;
  padding-bottom: 0.4rem;
  border-bottom: 1px solid #e0e0e0;
}
</style>

Data Science and analytics projects built end-to-end — from raw data to production-ready pipelines, models, and APIs.

<p class="section-label">Machine Learning & Data Science</p>

<div class="projects-grid">

<div class="project-card">
  <h3><a href="https://github.com/vanle2000/Stock-based-Recommendation-System" target="_blank">Stock Recommendation System</a></h3>
  <p class="project-problem">How do you find structurally similar stocks across 3,600+ equities at scale?</p>
  <p class="project-desc">End-to-end equity discovery platform: PySpark pipeline over 10M OHLCV records, 20+ technical indicators, PCA compression, LSTM price prediction, and a deep learning autoencoder for content-based stock similarity search. Deployed as a production FastAPI service with offline evaluation (Precision@5, NDCG@5, correlation lift vs random).</p>
  <div class="project-result">LinearSVR R²=0.997 · MAPE=13.1% · Walk-forward validated</div>
  <div class="project-tags">
    <span class="tag tag-python">Python</span>
    <span class="tag tag-spark">PySpark</span>
    <span class="tag tag-ml">Scikit-learn</span>
    <span class="tag tag-dl">TensorFlow</span>
    <span class="tag tag-nlp">DistilRoBERTa</span>
    <span class="tag tag-api">FastAPI</span>
  </div>
  <a class="btn-github" href="https://github.com/vanle2000/Stock-based-Recommendation-System" target="_blank">
    <svg height="14" width="14" viewBox="0 0 16 16" fill="currentColor"><path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z"/></svg>
    View on GitHub
  </a>
</div>

<div class="project-card">
  <h3><a href="https://github.com/vanle2000/Churn-Predictive-Modeling" target="_blank">Customer Churn Prediction</a></h3>
  <p class="project-problem">Which customers will leave — and is it worth the cost to intervene?</p>
  <p class="project-desc">Retention ROI optimization pipeline on Telco data (7,043 customers). Stratified 5-fold CV across Logistic Regression, Random Forest, and XGBoost + SMOTE. Evaluated with Precision@K and a net ROI simulation ($50/contact, $500/churner retained) rather than raw accuracy. SHAP explanations for per-customer risk drivers.</p>
  <div class="project-result">P@10%≈67% · ROI curve across targeting thresholds · SHAP feature attribution</div>
  <div class="project-tags">
    <span class="tag tag-python">Python</span>
    <span class="tag tag-ml">XGBoost</span>
    <span class="tag tag-ml">SMOTE</span>
    <span class="tag tag-viz">SHAP</span>
    <span class="tag tag-ml">Scikit-learn</span>
  </div>
  <a class="btn-github" href="https://github.com/vanle2000/Churn-Predictive-Modeling" target="_blank">
    <svg height="14" width="14" viewBox="0 0 16 16" fill="currentColor"><path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z"/></svg>
    View on GitHub
  </a>
</div>

<div class="project-card">
  <h3><a href="https://github.com/vanle2000/Chronic-disease-risks-in-US" target="_blank">Chronic Disease Risk Intelligence</a></h3>
  <p class="project-problem">Where should limited public health budgets be deployed first?</p>
  <p class="project-desc">20-year CDC surveillance pipeline (900K+ records, 50 states, 17 disease categories). State-level K-Means clustering on row-normalized disease profiles, logistic regression mortality prediction (AUC=0.73), and Random Forest risk classification with honest imbalance-aware evaluation — macro F1=0.85, not the misleading 0.9999 raw accuracy.</p>
  <div class="project-result">Silhouette=0.635 · Mortality AUC=0.73 · Macro F1=0.85</div>
  <div class="project-tags">
    <span class="tag tag-python">Python</span>
    <span class="tag tag-ml">Scikit-learn</span>
    <span class="tag tag-viz">GeoPandas</span>
    <span class="tag tag-viz">Plotly</span>
    <span class="tag tag-ml">Random Forest</span>
  </div>
  <a class="btn-github" href="https://github.com/vanle2000/Chronic-disease-risks-in-US" target="_blank">
    <svg height="14" width="14" viewBox="0 0 16 16" fill="currentColor"><path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z"/></svg>
    View on GitHub
  </a>
</div>

<div class="project-card">
  <h3><a href="https://github.com/vanle2000/Analysis-marathon-result-and-predict-performance-of-runners" target="_blank">Marathon Performance Analysis</a></h3>
  <p class="project-problem">Can you predict a runner's finish time from their 5K split — and classify gender from pace alone?</p>
  <p class="project-desc">Statistical modeling on 26,000 Boston Marathon runners. Custom KDEBayesClassifier (sklearn-compatible) using Gaussian KDE + Bayes theorem for gender prediction. 1-D vs 2-D KDE benchmark against KNN. Linear regression on 5K splits with SGD regularization and learning curve analysis. Pacing strategy segmentation (negative/even/positive split).</p>
  <div class="project-result">2-D KDE accuracy=77.5% · Linear regression R²=0.85 · 26 unit tests</div>
  <div class="project-tags">
    <span class="tag tag-python">Python</span>
    <span class="tag tag-ml">SciPy KDE</span>
    <span class="tag tag-ml">Scikit-learn</span>
    <span class="tag tag-viz">Matplotlib</span>
  </div>
  <a class="btn-github" href="https://github.com/vanle2000/Analysis-marathon-result-and-predict-performance-of-runners" target="_blank">
    <svg height="14" width="14" viewBox="0 0 16 16" fill="currentColor"><path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z"/></svg>
    View on GitHub
  </a>
</div>

</div>

<p class="section-label">Analytics Engineering & Business Intelligence</p>

<div class="projects-grid">

<div class="project-card">
  <h3><a href="https://github.com/vanle2000/GitHub-support-operations-analytics" target="_blank">GitHub Support Operations Analytics</a></h3>
  <p class="project-problem">Which repositories are silently destroying developer loyalty — and can we predict SLA breaches before they happen?</p>
  <p class="project-desc">Developer experience intelligence platform built on a SQL Server star schema (ETL via SQLAlchemy). NLTK/VADER sentiment volatility analysis to flag "frustrated users" — tickets where sentiment shifted negative during resolution. Statistical SLA risk scoring with 5-tier breach probability model. Power BI dashboard with quadrant analysis of "toxic" repos.</p>
  <div class="project-result">12-hour Golden Hour → 3.5x contributor retention lift · 12% repos identified as toxic</div>
  <div class="project-tags">
    <span class="tag tag-sql">SQL Server</span>
    <span class="tag tag-python">Python</span>
    <span class="tag tag-nlp">VADER NLP</span>
    <span class="tag tag-viz">Power BI</span>
    <span class="tag tag-sql">SQLAlchemy</span>
  </div>
  <a class="btn-github" href="https://github.com/vanle2000/GitHub-support-operations-analytics" target="_blank">
    <svg height="14" width="14" viewBox="0 0 16 16" fill="currentColor"><path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z"/></svg>
    View on GitHub
  </a>
</div>

<div class="project-card">
  <h3><a href="https://github.com/vanle2000/Financial-Reconciliation-Analytics" target="_blank">Financial Reconciliation Analytics</a></h3>
  <p class="project-problem">How do you automate financial data reconciliation and surface discrepancies at scale?</p>
  <p class="project-desc">Analytics pipeline for financial data reconciliation, variance detection, and automated reporting. Built to identify mismatches between source systems and produce audit-ready outputs.</p>
  <div class="project-result">Automated reconciliation pipeline · Variance detection & flagging</div>
  <div class="project-tags">
    <span class="tag tag-python">Python</span>
    <span class="tag tag-sql">SQL</span>
    <span class="tag tag-viz">Pandas</span>
  </div>
  <a class="btn-github" href="https://github.com/vanle2000/Financial-Reconciliation-Analytics" target="_blank">
    <svg height="14" width="14" viewBox="0 0 16 16" fill="currentColor"><path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z"/></svg>
    View on GitHub
  </a>
</div>

</div>
