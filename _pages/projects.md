---
title: "Projects"
permalink: /projects/
layout: single
author_profile: false
classes: wide
---

<script>
document.addEventListener("DOMContentLoaded", function () {
  var btns = document.querySelectorAll(".cat-btn");
  var sections = document.querySelectorAll(".cat-section");

  btns.forEach(function (btn) {
    btn.addEventListener("click", function () {
      var cat = btn.getAttribute("data-cat");
      btns.forEach(function (b) { b.classList.remove("active"); });
      btn.classList.add("active");

      sections.forEach(function (sec) {
        if (cat === "all" || sec.getAttribute("data-cat") === cat) {
          sec.style.display = "";
          sec.style.animation = "fadeSlideUp 0.35s ease both";
        } else {
          sec.style.display = "none";
        }
      });
    });
  });

  var cards = document.querySelectorAll(".proj-card");
  if ("IntersectionObserver" in window) {
    var io = new IntersectionObserver(function (entries) {
      entries.forEach(function (entry, i) {
        if (entry.isIntersecting) {
          setTimeout(function () { entry.target.classList.add("visible"); }, i * 60);
          io.unobserve(entry.target);
        }
      });
    }, { threshold: 0.08 });
    cards.forEach(function (card) { card.classList.add("reveal"); io.observe(card); });
  }
});
</script>

<!-- Category filter tabs -->
<div class="cat-filter">
  <button class="cat-btn active" data-cat="all">All Projects</button>
  <button class="cat-btn" data-cat="bi">BI &amp; Product Analytics</button>
  <button class="cat-btn" data-cat="ml">ML &amp; Predictive Modeling</button>
  <button class="cat-btn" data-cat="de">Data Engineering</button>
  <button class="cat-btn" data-cat="exp">Experimentation &amp; Statistics</button>
  <button class="cat-btn" data-cat="viz">Data Visualization</button>
</div>

<!-- ── Business Intelligence & Product Analytics ──────────────────────────── -->
<div class="cat-section" data-cat="bi">
  <div class="cat-header">
    <span class="cat-label">Business Intelligence &amp; Product Analytics</span>
    <span class="cat-line"></span>
    <span class="cat-count">1 project</span>
  </div>
  <div class="proj-grid">

    <div class="proj-card">
      <div class="proj-card__accent"></div>
      <p class="proj-card__type">Business Intelligence Engineering</p>
      <h3 class="proj-card__title">
        <a href="/vanle-portfolio/projects/github-analytics/">
          GitHub Support Operations Analytics
        </a>
      </h3>
      <p class="proj-card__desc">
        End-to-end BI platform on a SQL Server star schema with ETL via SQLAlchemy.
        VADER NLP tracks sentiment shift across issue lifecycles to flag frustrated contributors.
        A statistical SLA breach probability model scores all open tickets in real time across five risk tiers.
        Power BI dashboard with quadrant scatter analysis of repository health versus contributor retention.
      </p>
      <div class="proj-card__result">12-hour response threshold predicts 3.5x lift in repeat contributor rate &middot; 12% of repos identified as toxic</div>
      <div class="proj-card__tags">
        <span class="ptag">SQL Server</span>
        <span class="ptag">SQLAlchemy</span>
        <span class="ptag">VADER NLP</span>
        <span class="ptag">Power BI</span>
        <span class="ptag">Star Schema</span>
        <span class="ptag">ETL</span>
        <span class="ptag">Python</span>
      </div>
      <div class="proj-card__footer">
        <a class="proj-link proj-link--gh" href="https://github.com/vanle2000/GitHub-support-operations-analytics" target="_blank">
          GitHub &#8594;
        </a>
      </div>
    </div>

  </div>
</div>

<!-- ── Machine Learning & Predictive Modeling ─────────────────────────────── -->
<div class="cat-section" data-cat="ml">
  <div class="cat-header">
    <span class="cat-label">Machine Learning &amp; Predictive Modeling</span>
    <span class="cat-line"></span>
    <span class="cat-count">3 projects</span>
  </div>
  <div class="proj-grid">

    <div class="proj-card">
      <div class="proj-card__accent"></div>
      <p class="proj-card__type">Public Health &amp; Risk Classification</p>
      <h3 class="proj-card__title">
        <a href="/vanle-portfolio/projects/chronic-disease/">
          Chronic Disease Risk Intelligence
        </a>
      </h3>
      <p class="proj-card__desc">
        20-year CDC surveillance pipeline across 900K records and 50 states. State-level K-Means clustering
        on row-normalized disease profiles. Logistic Regression mortality predictor and Random Forest
        risk classifier with honest imbalance-aware evaluation, macro F1, not misleading raw accuracy.
      </p>
      <div class="proj-card__result">Silhouette=0.635 &middot; Mortality AUC=0.73 &middot; Macro F1=0.85 (not 0.9999 raw accuracy)</div>
      <div class="proj-card__tags">
        <span class="ptag">Random Forest</span>
        <span class="ptag">KMeans</span>
        <span class="ptag">GeoPandas</span>
        <span class="ptag">Plotly</span>
        <span class="ptag">Scikit-learn</span>
      </div>
      <div class="proj-card__footer">
        <a class="proj-link proj-link--gh" href="https://github.com/vanle2000/Chronic-disease-risks-in-US" target="_blank">
          GitHub &#8594;
        </a>
      </div>
    </div>

    <div class="proj-card">
      <div class="proj-card__accent"></div>
      <p class="proj-card__type">Statistical ML &amp; Sports Analytics</p>
      <h3 class="proj-card__title">
        <a href="/vanle-portfolio/projects/marathon-performance/">
          Marathon Performance Analysis
        </a>
      </h3>
      <p class="proj-card__desc">
        26,000 Boston Marathon runners. Custom KDEBayesClassifier using Gaussian KDE and Bayes theorem
        for gender classification. 2-D KDE (finish time and age) outperforms 1-D by 12pp.
        Linear regression from 5K split achieves R&#178;=0.85, adding age and gender barely moves the number,
        which is itself the key finding.
      </p>
      <div class="proj-card__result">2-D KDE accuracy=77.5% &middot; Linear regression R&#178;=0.85 &middot; 26 unit tests</div>
      <div class="proj-card__tags">
        <span class="ptag">SciPy KDE</span>
        <span class="ptag">Bayes Theorem</span>
        <span class="ptag">KNN</span>
        <span class="ptag">Linear Regression</span>
        <span class="ptag">SGD</span>
      </div>
      <div class="proj-card__footer">
        <a class="proj-link proj-link--gh" href="https://github.com/vanle2000/Analysis-marathon-result-and-predict-performance-of-runners" target="_blank">
          GitHub &#8594;
        </a>
      </div>
    </div>

    <div class="proj-card">
      <div class="proj-card__accent"></div>
      <p class="proj-card__type">Deep Learning &amp; Recommendation</p>
      <h3 class="proj-card__title">
        <a href="/vanle-portfolio/projects/stock-recommendation/">
          Stock Recommendation System
        </a>
      </h3>
      <p class="proj-card__desc">
        LinearSVR price predictor on PCA-compressed technical indicators with walk-forward cross-validation.
        Deep learning autoencoder encodes stock behavioral profiles into latent space; cosine similarity
        drives content-based recommendations. Deployed as a FastAPI REST service with Precision@5 and
        NDCG@5 offline evaluation metrics.
      </p>
      <div class="proj-card__result">LinearSVR R&#178;=0.997 under walk-forward CV &middot; FastAPI production &middot; 45 tests</div>
      <div class="proj-card__tags">
        <span class="ptag">LinearSVR</span>
        <span class="ptag">Autoencoder</span>
        <span class="ptag">TensorFlow</span>
        <span class="ptag">FastAPI</span>
        <span class="ptag">Walk-forward CV</span>
      </div>
      <div class="proj-card__footer">
        <a class="proj-link proj-link--gh" href="https://github.com/vanle2000/Stock-based-Recommendation-System" target="_blank">
          GitHub &#8594;
        </a>
      </div>
    </div>

  </div>
</div>

<!-- ── Data Engineering & ETL Pipeline ───────────────────────────────────── -->
<div class="cat-section" data-cat="de">
  <div class="cat-header">
    <span class="cat-label">Data Engineering &amp; ETL Pipeline</span>
    <span class="cat-line"></span>
    <span class="cat-count">1 project</span>
  </div>
  <div class="proj-grid">

    <div class="proj-card">
      <div class="proj-card__accent"></div>
      <p class="proj-card__type">Large-scale Data Pipeline</p>
      <h3 class="proj-card__title">
        <a href="/vanle-portfolio/projects/stock-recommendation/">
          Stock Market Data Pipeline
        </a>
      </h3>
      <p class="proj-card__desc">
        PySpark distributed ingestion of 10M+ OHLCV records across 3,600+ NASDAQ tickers.
        Merged historical price data with NASDAQ ticker metadata (sector, industry, market cap).
        Engineered 20+ technical indicators (SMA, EMA, RSI, MACD, Bollinger Bands, Ichimoku, ATR, OBV).
        PCA compression of 20+ features to 5 principal components for downstream modeling.
        Deployed as a FastAPI REST service with Docker containerization.
      </p>
      <div class="proj-card__result">10M+ records &middot; PySpark distributed processing &middot; 20+ indicators &middot; Docker deployment</div>
      <div class="proj-card__tags">
        <span class="ptag">PySpark</span>
        <span class="ptag">Pandas</span>
        <span class="ptag">PCA</span>
        <span class="ptag">Docker</span>
        <span class="ptag">FastAPI</span>
        <span class="ptag">NASDAQ API</span>
      </div>
      <div class="proj-card__footer">
        <a class="proj-link proj-link--gh" href="https://github.com/vanle2000/Stock-based-Recommendation-System" target="_blank">
          GitHub &#8594;
        </a>
      </div>
    </div>

  </div>
</div>

<!-- ── Experimentation & Statistical Inference ───────────────────────────── -->
<div class="cat-section" data-cat="exp">
  <div class="cat-header">
    <span class="cat-label">Experimentation &amp; Statistical Inference</span>
    <span class="cat-line"></span>
    <span class="cat-count">in progress</span>
  </div>
  <div class="proj-grid">

    <div class="proj-card in-progress">
      <div class="proj-card__type">Causal Inference &amp; A/B Testing</div>
      <h3 class="proj-card__title">Experimentation Framework</h3>
      <p class="proj-card__desc">
        An end-to-end experiment design and analysis system for business and operational settings.
        Covers power analysis, randomization strategies, difference-in-differences, regression discontinuity,
        and sequential testing. Designed for settings where randomization is constrained and decisions carry real costs.
      </p>
      <div class="proj-card__result">In progress &middot; Causal inference &middot; A/B testing &middot; Statistical rigor in applied settings</div>
      <div class="proj-card__tags">
        <span class="ptag">Python</span>
        <span class="ptag">Statsmodels</span>
        <span class="ptag">Causal Inference</span>
        <span class="ptag">Power Analysis</span>
      </div>
      <div class="proj-card__footer">
        <span class="ip-badge">In Progress</span>
      </div>
    </div>

  </div>
</div>

<!-- ── Data Visualization ────────────────────────────────────────────────── -->
<div class="cat-section" data-cat="viz">
  <div class="cat-header">
    <span class="cat-label">Data Visualization</span>
    <span class="cat-line"></span>
    <span class="cat-count">in progress</span>
  </div>
  <div class="proj-grid">

    <div class="proj-card in-progress">
      <div class="proj-card__type">Interactive Dashboard</div>
      <h3 class="proj-card__title">Tableau Public Health Dashboard</h3>
      <p class="proj-card__desc">
        Interactive Tableau dashboard for the CDC Chronic Disease Indicators dataset.
        State-level choropleth maps, 20-year disease trend lines, demographic breakdowns by
        race and gender, and risk tier distribution across all 50 states.
        Designed for public health analysts to identify high-priority intervention targets.
      </p>
      <div class="proj-card__result">In progress &middot; CDC CDI &middot; 900K records &middot; 50 states &middot; 2001&#8211;2021</div>
      <div class="proj-card__tags">
        <span class="ptag">Tableau Public</span>
        <span class="ptag">CDC Open Data</span>
        <span class="ptag">Choropleth</span>
        <span class="ptag">Public Health</span>
      </div>
      <div class="proj-card__footer">
        <span class="ip-badge">In Progress</span>
      </div>
    </div>

  </div>
</div>
