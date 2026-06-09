---
title: ""
permalink: /about/
layout: single
author_profile: false
classes: wide
---

<style>
/* ── About page layout ─────────────────────────────────────────────────────── */
.about-wrap {
  max-width: 70%;
  margin: 3.5rem auto 5rem;
  padding: 0;
}

/* Section chrome */
.about-sec {
  font-family: var(--font-mono);
  font-size: .62rem;
  font-weight: 700;
  letter-spacing: .16em;
  text-transform: uppercase;
  color: var(--color-accent);
  display: flex;
  align-items: center;
  gap: .9rem;
  margin: 0 0 2rem;
}
.about-sec::after {
  content: "";
  flex: 1;
  height: 1px;
  background: linear-gradient(90deg, color-mix(in srgb, var(--color-accent) 18%, transparent) 0%, transparent 100%);
}

/* Intro */
.about-intro { margin-bottom: 3.5rem; }

.about-intro h1 {
  font-family: var(--font-display);
  font-size: clamp(2rem, 4.5vw, 2.8rem);
  font-weight: 800;
  color: var(--color-text-primary);
  letter-spacing: -.01em;
  line-height: 1.1;
  margin: 0 0 1rem;
}

.about-intro p {
  font-size: .97rem;
  line-height: 1.82;
  color: var(--color-text-secondary);
  max-width: 640px;
  margin: 0 0 .85rem;
}

/* 2×2 project grid */
.proj-2x2 {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 1.3rem;
  margin-bottom: 3.5rem;
}

/* Project card */
.pj {
  background: var(--color-bg-primary);
  border: 1px solid var(--color-border);
  border-radius: 10px;
  padding: 1.6rem 1.65rem 1.45rem;
  position: relative;
  overflow: hidden;
  display: flex;
  flex-direction: column;
  transition: border-color .25s, box-shadow .25s,
              transform .25s cubic-bezier(.34,1.2,.64,1);
}

/* Top accent bar */
.pj::before {
  content: "";
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 2px;
  background: linear-gradient(90deg, var(--color-accent), var(--color-accent-light));
  border-radius: 10px 10px 0 0;
  transform: scaleX(0);
  transform-origin: left;
  transition: transform .3s cubic-bezier(.34,1.2,.64,1);
}

.pj:hover {
  border-color: color-mix(in srgb, var(--color-accent) 28%, transparent);
  box-shadow: 0 8px 32px color-mix(in srgb, var(--color-accent) 9%, transparent), 0 2px 8px rgba(0,0,0,.03);
  transform: translateY(-3px);
}
.pj:hover::before { transform: scaleX(1); }

.pj-cat {
  font-family: var(--font-mono);
  font-size: .59rem;
  font-weight: 600;
  letter-spacing: .1em;
  text-transform: uppercase;
  color: var(--color-accent);
  margin: 0 0 .38rem;
}

.pj-name {
  font-size: 1.02rem;
  font-weight: 800;
  color: var(--color-text-primary);
  letter-spacing: -.02em;
  line-height: 1.25;
  margin: 0 0 .42rem;
}

.pj-tagline {
  font-size: .82rem;
  color: var(--color-text-muted);
  line-height: 1.52;
  margin: 0 0 1rem;
}

/* STAR bullets */
.pj-hr {
  height: 1px;
  background: var(--color-border);
  margin: 0 0 1rem;
  border: none;
}

.pj-list {
  list-style: none;
  margin: 0;
  padding: 0;
  display: flex;
  flex-direction: column;
  gap: .5rem;
  flex-grow: 1;
}

.pj-list li {
  font-size: .82rem;
  color: var(--color-text-secondary);
  line-height: 1.58;
  padding-left: 1.05rem;
  position: relative;
}

.pj-list li::before {
  content: "";
  position: absolute;
  left: 0;
  top: .56em;
  width: 4px;
  height: 4px;
  border-radius: 50%;
  background: var(--color-accent);
}

.pj-list li strong {
  color: var(--color-text-primary);
  font-weight: 600;
}

/* Result strip */
.pj-result {
  font-family: var(--font-mono);
  font-size: .69rem;
  font-weight: 600;
  color: var(--color-accent-light);
  background: color-mix(in srgb, var(--color-accent-light) 7%, transparent);
  border-left: 2px solid color-mix(in srgb, var(--color-accent-light) 40%, transparent);
  padding: .28rem .65rem;
  border-radius: 0 5px 5px 0;
  margin-top: .95rem;
  line-height: 1.42;
}

/* GitHub link */
.pj-link {
  font-family: var(--font-mono);
  font-size: .65rem;
  font-weight: 600;
  color: var(--color-accent);
  text-decoration: none;
  display: inline-flex;
  align-items: center;
  gap: .25rem;
  margin-top: .7rem;
  transition: color .15s;
}
.pj-link:hover { color: var(--color-accent-light); text-decoration: none; }

/* Prose sections */
.about-prose { margin-bottom: 2.75rem; }

.about-prose h2 {
  font-family: var(--font-body);
  font-size: .95rem;
  font-weight: 700;
  color: var(--color-text-primary);
  letter-spacing: -.01em;
  margin: 0 0 .8rem;
  padding-bottom: .38rem;
  border-bottom: 1px solid var(--color-border);
}

.about-prose p {
  font-size: .94rem;
  color: var(--color-text-secondary);
  line-height: 1.8;
  margin: 0 0 .8rem;
}

.about-prose ul {
  padding-left: 1.1rem;
  margin: 0;
}

.about-prose ul li {
  font-size: .93rem;
  color: var(--color-text-secondary);
  line-height: 1.72;
  margin-bottom: .28rem;
}

/* Responsive */
@media (max-width: 960px) {
  .about-wrap { max-width: 90%; }
}
@media (max-width: 700px) {
  .about-wrap { max-width: 95%; margin: 2rem auto 4rem; }
  .proj-2x2 { grid-template-columns: 1fr; }
}
</style>

<div class="about-wrap">

<!-- ── Intro ─────────────────────────────────────────────────────────────────── -->
<div class="about-intro">
  <h1>Van (Elizabeth) Le</h1>
  <p>Data Analyst and Scientist based in Houston, TX. At M&amp;T Tax Firm I build reporting pipelines, automate reconciliation workflows, and turn financial records into structured decision support. I am looking for my next role in data analytics, BI engineering, or data science, working on problems at scale where rigor is high and the output connects to a real decision.</p>
</div>

<!-- ── Projects ───────────────────────────────────────────────────────────────── -->
<span class="about-sec">Selected Projects</span>

<div class="proj-2x2">

  <!-- 1 -->
  <div class="pj">
    <p class="pj-cat">Data Pipeline &amp; ML Engineering</p>
    <p class="pj-name">Stock Recommendation System</p>
    <p class="pj-tagline">Recommends NASDAQ stocks by behavioral similarity from a 10M-record PySpark pipeline.</p>
    <hr class="pj-hr">
    <ul class="pj-list">
      <li><strong>Business case:</strong> Investment teams needed to identify correlated equities beyond sector labels, with no lookahead bias in the evaluation.</li>
      <li><strong>Solution:</strong> PySpark on 10M+ OHLCV records → 20+ technical indicators → PCA → deep learning autoencoder → cosine similarity recommendations → LinearSVR price predictor → FastAPI production service.</li>
      <li><strong>Walk-forward CV</strong> replaces random split to eliminate lookahead bias; standard splits on time-series inflate R² toward 1.0 through data leakage.</li>
    </ul>
    <div class="pj-result">R²=0.997 under walk-forward CV &middot; Precision@5 &amp; NDCG@5 &middot; 45 tests</div>
    <a class="pj-link" href="https://github.com/vanle2000/Stock-based-Recommendation-System" target="_blank" rel="noopener">GitHub ↗</a>
  </div>

  <!-- 2 -->
  <div class="pj">
    <p class="pj-cat">Machine Learning &amp; Business Analytics</p>
    <p class="pj-name">Customer Churn Prediction</p>
    <p class="pj-tagline">Identifies the 10% of customers most likely to churn, with per-customer SHAP explanations.</p>
    <hr class="pj-hr">
    <ul class="pj-list">
      <li><strong>Business case:</strong> A Telco needed to direct retention spend at highest-risk accounts. Raw accuracy on imbalanced data fails as the evaluation criterion.</li>
      <li><strong>Solution:</strong> XGBoost + SMOTE, evaluated on Precision@K and a net ROI simulation ($50 outreach / $500 revenue recovered). SHAP waterfall charts per customer for the retention team.</li>
      <li><strong>Precision@K replaces accuracy.</strong> The model is judged on its business intervention, not a classification benchmark with 74% majority-class bias.</li>
    </ul>
    <div class="pj-result">67% precision in top 10% &middot; Positive ROI at $50/outreach &middot; SHAP attribution per customer</div>
    <a class="pj-link" href="https://github.com/vanle2000/Churn-Predictive-Modeling" target="_blank" rel="noopener">GitHub ↗</a>
  </div>

  <!-- 3 -->
  <div class="pj">
    <p class="pj-cat">Public Health &amp; Predictive Modeling</p>
    <p class="pj-name">CDC Chronic Disease Intelligence</p>
    <p class="pj-tagline">Clusters 50 US states by disease burden; predicts mortality risk across 20 years of CDC data.</p>
    <hr class="pj-hr">
    <ul class="pj-list">
      <li><strong>Business case:</strong> 900K CDC surveillance records had no systematic structural analysis. Most published models reported inflated accuracy without addressing class imbalance.</li>
      <li><strong>Solution:</strong> K-Means clustering on row-normalized state profiles, Logistic Regression mortality predictor, Random Forest risk classifier evaluated on macro F1.</li>
      <li><strong>Macro F1=0.85 reported over raw accuracy.</strong> The dominant Low-risk class (238K records vs. 3 Very High records) makes raw accuracy meaningless. Macro F1 weights each class equally.</li>
    </ul>
    <div class="pj-result">Silhouette=0.635 &middot; AUC=0.73 &middot; Macro F1=0.85 &middot; 4 state archetypes</div>
    <a class="pj-link" href="https://github.com/vanle2000/Chronic-disease-risks-in-US" target="_blank" rel="noopener">GitHub ↗</a>
  </div>

  <!-- 4 -->
  <div class="pj">
    <p class="pj-cat">Business Intelligence Engineering</p>
    <p class="pj-name">GitHub Support Operations Analytics</p>
    <p class="pj-tagline">BI platform measuring SLA risk and contributor sentiment across GitHub support operations.</p>
    <hr class="pj-hr">
    <ul class="pj-list">
      <li><strong>Business case:</strong> GitHub-scale support teams had no visibility into which repos were damaging contributor retention through slow or frustrating responses, or which open tickets were about to breach SLA.</li>
      <li><strong>Solution:</strong> SQL Server star schema + SQLAlchemy ETL, VADER NLP sentiment tracking per ticket lifecycle (initial → final → shift delta), 5-tier real-time SLA breach probability model. Power BI dashboard with repo health quadrant.</li>
      <li><strong>Connected support metrics to retention outcomes,</strong> not just SLA compliance. Repeat contributor conversion rates downstream of each interaction.</li>
    </ul>
    <div class="pj-result">12h response predicts 3.5&times; lift in repeat contributors &middot; 12% of repos identified as toxic</div>
    <a class="pj-link" href="https://github.com/vanle2000/GitHub-support-operations-analytics" target="_blank" rel="noopener">GitHub ↗</a>
  </div>

</div>

<!-- ── What I'm working toward ─────────────────────────────────────────────── -->
<div class="about-prose">
  <h2>What I'm Working Toward</h2>
  <p>My longer-term interest is in probabilistic modeling, latent variable methods, LLM applications, and AI agentic systems. The difference between knowing what a model outputs and understanding what it has learned matters when the output drives a real decision. Bayesian inference, deep learning latent representations, and interpretable ML are where I spend time outside of work.</p>
  <p>I'm building toward roles where statistical modeling and large-scale data intersect with rigorous uncertainty quantification.</p>
</div>

<!-- ── Education ──────────────────────────────────────────────────────────────── -->
<div class="about-prose">
  <h2>Education</h2>
  <ul>
    <li>B.A. in Computational and Applied Mathematics, University at Buffalo (2022–2023)</li>
    <li>Biochemistry and Molecular Biology, University of Houston (2020–2022)</li>
    <li>A.S. in Chemistry and A.B. in Finance, North Seattle College (2018–2020)</li>
  </ul>
</div>

<!-- ── CTA ───────────────────────────────────────────────────────────────────── -->
<div class="page-cta">
  <p class="page-cta__title">Let's get in touch!</p>
  <p class="page-cta__desc">Always excited to discuss new opportunities, collaborate on projects, or have a coffee chat.</p>
  <div class="page-cta__links">
    <a class="page-cta__link" href="mailto:vanle.vtl2000@gmail.com">vanle.vtl2000@gmail.com</a>
    <a class="page-cta__link" href="https://www.linkedin.com/in/elizabethvanle/" target="_blank" rel="noopener">LinkedIn</a>
    <a class="page-cta__link" href="https://github.com/vanle2000" target="_blank" rel="noopener">GitHub</a>
  </div>
</div>

</div>
