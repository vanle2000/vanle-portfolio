---
title: ""
permalink: /projects/
layout: single
author_profile: false
classes: wide
---

<style>
.projects-page-wrap {
  padding: 3rem clamp(2rem, 8vw, 7rem) 5rem;
  background: #FDFAF5;
}

/* Page header */
.proj-page-header {
  margin-bottom: 2.5rem;
}
.proj-page-header h1 {
  font-family: "Playfair Display", Georgia, serif;
  font-size: clamp(1.6rem, 4vw, 2.1rem);
  font-weight: 800;
  color: #1C1410;
  letter-spacing: -0.01em;
  line-height: 1.15;
  margin: 0 0 0.4rem;
}
.proj-page-header p {
  font-family: "IBM Plex Mono", monospace;
  font-size: 0.7rem;
  font-weight: 500;
  color: #A89888;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  margin: 0;
}
</style>

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

<div class="projects-page-wrap">

<div class="proj-page-header">
  <h1>Projects</h1>
  <p>End-to-end data projects across BI engineering, ML, and data pipelines</p>
</div>

<!-- Filter tabs -->
<div class="cat-filter">
  <button class="cat-btn active" data-cat="all">All Projects</button>
  <button class="cat-btn" data-cat="bi">BI &amp; Analytics</button>
  <button class="cat-btn" data-cat="ml">Machine Learning</button>
  <button class="cat-btn" data-cat="de">Data Engineering</button>
  <button class="cat-btn" data-cat="exp">Experimentation</button>
  <button class="cat-btn" data-cat="viz">Visualization</button>
</div>

<!-- Business Intelligence -->
<div class="cat-section" data-cat="bi">
  <div class="cat-header">
    <span class="cat-label">Business Intelligence &amp; Analytics</span>
    <span class="cat-line"></span>
    <span class="cat-count">1 project</span>
  </div>
  <div class="proj-grid">

    <div class="proj-card">
      <div class="proj-card__accent"></div>
      <p class="proj-card__type">Business Intelligence Engineering</p>
      <h3 class="proj-card__title">
        <a href="https://github.com/vanle2000/GitHub-support-operations-analytics" target="_blank">GitHub Support Operations Analytics</a>
      </h3>
      <p class="proj-card__desc">
        End-to-end BI platform on a SQL Server star schema with ETL via SQLAlchemy.
        VADER NLP tracks sentiment change across issue lifecycles to flag frustrated contributors.
        A statistical SLA breach model scores open tickets in real time across five risk tiers.
        Power BI dashboard with quadrant analysis of repository health versus contributor retention.
      </p>
      <div class="proj-card__result">12h response threshold predicts 3.5x lift in repeat contributor rate &middot; 12% of repos identified as SLA-toxic</div>
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
        <a class="proj-link proj-link--gh" href="https://github.com/vanle2000/GitHub-support-operations-analytics" target="_blank">GitHub &#8594;</a>
      </div>
    </div>

  </div>
</div>

<!-- Machine Learning -->
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
        <a href="https://github.com/vanle2000/Chronic-disease-risks-in-US" target="_blank">Chronic Disease Risk Intelligence</a>
      </h3>
      <p class="proj-card__desc">
        20-year CDC surveillance pipeline across 900K records and 50 states.
        State-level K-Means clustering on row-normalized disease profiles.
        Logistic Regression mortality predictor and Random Forest risk classifier
        evaluated on macro F1, not raw accuracy, to avoid misleading results on imbalanced data.
      </p>
      <div class="proj-card__result">Silhouette=0.635 &middot; Mortality AUC=0.73 &middot; Macro F1=0.85</div>
      <div class="proj-card__tags">
        <span class="ptag">Random Forest</span>
        <span class="ptag">KMeans</span>
        <span class="ptag">GeoPandas</span>
        <span class="ptag">Plotly</span>
        <span class="ptag">Scikit-learn</span>
      </div>
      <div class="proj-card__footer">
        <a class="proj-link proj-link--gh" href="https://github.com/vanle2000/Chronic-disease-risks-in-US" target="_blank">GitHub &#8594;</a>
      </div>
    </div>

    <div class="proj-card">
      <div class="proj-card__accent"></div>
      <p class="proj-card__type">Statistical ML &amp; Sports Analytics</p>
      <h3 class="proj-card__title">
        <a href="https://github.com/vanle2000/Analysis-marathon-result-and-predict-performance-of-runners" target="_blank">Marathon Performance Analysis</a>
      </h3>
      <p class="proj-card__desc">
        26,000 Boston Marathon runners. Custom KDEBayesClassifier using Gaussian KDE and Bayes theorem
        for gender classification. 2-D KDE on finish time and age outperforms 1-D by 12 percentage points.
        Linear regression from the 5K split achieves R&#178;=0.85; adding age and gender barely moves it,
        which is the main finding.
      </p>
      <div class="proj-card__result">2-D KDE accuracy 77.5% &middot; Linear regression R&#178;=0.85 &middot; 26 unit tests</div>
      <div class="proj-card__tags">
        <span class="ptag">SciPy KDE</span>
        <span class="ptag">Bayes Theorem</span>
        <span class="ptag">KNN</span>
        <span class="ptag">Linear Regression</span>
        <span class="ptag">SGD</span>
      </div>
      <div class="proj-card__footer">
        <a class="proj-link proj-link--gh" href="https://github.com/vanle2000/Analysis-marathon-result-and-predict-performance-of-runners" target="_blank">GitHub &#8594;</a>
      </div>
    </div>

    <div class="proj-card">
      <div class="proj-card__accent"></div>
      <p class="proj-card__type">Deep Learning &amp; Recommendation</p>
      <h3 class="proj-card__title">
        <a href="https://github.com/vanle2000/Stock-based-Recommendation-System" target="_blank">Stock Recommendation System</a>
      </h3>
      <p class="proj-card__desc">
        LinearSVR price predictor on PCA-compressed technical indicators with walk-forward cross-validation.
        Deep learning autoencoder encodes stock behavioral profiles into latent space; cosine similarity
        drives content-based recommendations. FastAPI REST service with Precision@5 and NDCG@5
        offline evaluation.
      </p>
      <div class="proj-card__result">LinearSVR R&#178;=0.997 under walk-forward CV &middot; FastAPI production service &middot; 45 tests</div>
      <div class="proj-card__tags">
        <span class="ptag">LinearSVR</span>
        <span class="ptag">Autoencoder</span>
        <span class="ptag">TensorFlow</span>
        <span class="ptag">FastAPI</span>
        <span class="ptag">Walk-forward CV</span>
      </div>
      <div class="proj-card__footer">
        <a class="proj-link proj-link--gh" href="https://github.com/vanle2000/Stock-based-Recommendation-System" target="_blank">GitHub &#8594;</a>
      </div>
    </div>

  </div>
</div>

<!-- Data Engineering -->
<div class="cat-section" data-cat="de">
  <div class="cat-header">
    <span class="cat-label">Data Engineering &amp; ETL</span>
    <span class="cat-line"></span>
    <span class="cat-count">1 project</span>
  </div>
  <div class="proj-grid">

    <div class="proj-card">
      <div class="proj-card__accent"></div>
      <p class="proj-card__type">Large-scale Data Pipeline</p>
      <h3 class="proj-card__title">
        <a href="https://github.com/vanle2000/Stock-based-Recommendation-System" target="_blank">Stock Market Data Pipeline</a>
      </h3>
      <p class="proj-card__desc">
        PySpark ingestion of 10M+ OHLCV records across 3,600+ NASDAQ tickers.
        Merged historical price data with ticker metadata including sector, industry, and market cap.
        Engineered 20+ technical indicators including SMA, EMA, RSI, MACD, Bollinger Bands, and ATR.
        PCA compression of 20+ features to 5 principal components for downstream modeling.
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
        <a class="proj-link proj-link--gh" href="https://github.com/vanle2000/Stock-based-Recommendation-System" target="_blank">GitHub &#8594;</a>
      </div>
    </div>

  </div>
</div>

<!-- Experimentation -->
<div class="cat-section" data-cat="exp">
  <div class="cat-header">
    <span class="cat-label">Experimentation &amp; Statistical Inference</span>
    <span class="cat-line"></span>
    <span class="cat-count">in progress</span>
  </div>
  <div class="proj-grid">

    <div class="proj-card in-progress">
      <p class="proj-card__type">Causal Inference &amp; A/B Testing</p>
      <h3 class="proj-card__title">Experimentation Framework</h3>
      <p class="proj-card__desc">
        An end-to-end experiment design and analysis system for business settings.
        Covers power analysis, randomization strategies, difference-in-differences,
        regression discontinuity, and sequential testing.
        Built for settings where randomization is constrained and decisions carry real costs.
      </p>
      <div class="proj-card__result">In progress &middot; Causal inference &middot; A/B testing &middot; Applied statistics</div>
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

<!-- Visualization -->
<div class="cat-section" data-cat="viz">
  <div class="cat-header">
    <span class="cat-label">Data Visualization</span>
    <span class="cat-line"></span>
    <span class="cat-count">in progress</span>
  </div>
  <div class="proj-grid">

    <div class="proj-card in-progress">
      <p class="proj-card__type">Interactive Dashboard</p>
      <h3 class="proj-card__title">Tableau Public Health Dashboard</h3>
      <p class="proj-card__desc">
        Interactive Tableau dashboard for the CDC Chronic Disease Indicators dataset.
        State-level choropleth maps, 20-year disease trend lines, demographic breakdowns by race and gender,
        and risk tier distribution across all 50 states.
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

<!-- CTA -->
<div class="page-cta" style="margin:3rem 0 0;">
  <p class="page-cta__title">Let's get in touch!</p>
  <p class="page-cta__desc">Always excited to discuss new opportunities, collaborate on projects, or have a coffee chat.</p>
  <div class="page-cta__links">
    <a class="page-cta__link" href="mailto:vanle.vtl2000@gmail.com">vanle.vtl2000@gmail.com</a>
    <a class="page-cta__link" href="https://www.linkedin.com/in/elizabethvanle/" target="_blank" rel="noopener">LinkedIn</a>
    <a class="page-cta__link" href="https://github.com/vanle2000" target="_blank" rel="noopener">GitHub</a>
  </div>
</div>

</div>
