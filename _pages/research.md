---
title: ""
permalink: /research/
layout: single
author_profile: false
classes: wide
---

<style>
/* ── Page layout ───────────────────────────────────────────────────────────── */
.research-wrap {
  max-width: 70%;
  margin: 3rem auto 5rem;
  padding: 0;
}

/* ── Section labels ────────────────────────────────────────────────────────── */
.rs-lbl {
  font-family: "IBM Plex Mono", monospace;
  font-size: 0.62rem;
  font-weight: 700;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  color: var(--color-accent);
  display: flex;
  align-items: center;
  gap: 0.85rem;
  margin: 0 0 2rem;
}
.rs-lbl::after {
  content: "";
  flex: 1;
  height: 1px;
  background: linear-gradient(90deg, color-mix(in srgb, var(--color-accent) 18%, transparent) 0%, transparent 100%);
}

/* ── Page intro ─────────────────────────────────────────────────────────────── */
.rs-intro {
  font-size: 0.96rem;
  line-height: 1.82;
  color: var(--color-text-secondary);
  max-width: 640px;
  margin: 0 0 2.75rem;
}

/* ── Research interest 2x2 grid ────────────────────────────────────────────── */
.int-2x2 {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1.25rem;
  margin-bottom: 3.5rem;
}

.ri-card {
  background: var(--color-bg-primary);
  border: 1px solid var(--color-border);
  border-radius: 10px;
  overflow: hidden;
  display: flex;
  flex-direction: column;
  transition: border-color .25s, box-shadow .25s,
              transform .25s cubic-bezier(.34,1.2,.64,1);
}
.ri-card:hover {
  border-color: color-mix(in srgb, var(--color-accent) 25%, transparent);
  box-shadow: 0 6px 24px color-mix(in srgb, var(--color-accent) 8%, transparent);
  transform: translateY(-2px);
}

/* Visualization area */
.ri-viz {
  padding: 1.2rem 1.5rem 0.9rem;
  background: var(--color-bg-secondary);
  border-bottom: 1px solid var(--color-border);
  display: flex;
  justify-content: center;
  align-items: center;
}

/* Body */
.ri-body { padding: 1.3rem 1.45rem 1.4rem; flex: 1; display: flex; flex-direction: column; }

.ri-num {
  font-family: "IBM Plex Mono", monospace;
  font-size: 0.6rem;
  font-weight: 700;
  color: var(--color-accent);
  letter-spacing: 0.06em;
  margin: 0 0 0.38rem;
}
.ri-title {
  font-size: 0.94rem;
  font-weight: 700;
  color: var(--color-text-primary);
  margin: 0 0 0.75rem;
  letter-spacing: -0.01em;
  line-height: 1.25;
}
.ri-desc {
  font-size: 0.81rem;
  color: var(--color-text-secondary);
  line-height: 1.74;
  margin: 0;
  flex: 1;
}
.ri-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.3rem;
  margin-top: 0.9rem;
}
.ri-tag {
  font-family: "IBM Plex Mono", monospace;
  font-size: 0.59rem;
  font-weight: 500;
  color: var(--color-text-muted);
  background: var(--color-border);
  border-radius: 3px;
  padding: 0.18rem 0.5rem;
}

/* ── Research experience timeline ──────────────────────────────────────────── */
.exp-list {
  display: flex;
  flex-direction: column;
  gap: 0;
  margin-bottom: 3.5rem;
}

.exp-row {
  display: grid;
  grid-template-columns: 88px 1fr;
  gap: 0 1.75rem;
  padding-bottom: 2.25rem;
}

.exp-period {
  font-family: "IBM Plex Mono", monospace;
  font-size: 0.67rem;
  color: var(--color-text-muted);
  text-align: right;
  padding-top: 0.12rem;
  white-space: nowrap;
  line-height: 1.5;
}

.exp-lab {
  font-size: 0.95rem;
  font-weight: 700;
  color: var(--color-text-primary);
  margin: 0 0 0.15rem;
  letter-spacing: -0.01em;
}
.exp-lab a {
  color: inherit;
  text-decoration: none;
  border-bottom: 1.5px solid color-mix(in srgb, var(--color-accent) 20%, transparent);
  transition: color 0.15s, border-color 0.15s;
}
.exp-lab a:hover { color: var(--color-accent); border-color: var(--color-accent); }

.exp-meta {
  font-size: 0.77rem;
  color: var(--color-text-muted);
  margin: 0 0 0.95rem;
  line-height: 1.45;
}

.exp-items {
  list-style: none;
  padding: 0; margin: 0;
  display: flex; flex-direction: column; gap: 0.65rem;
}

.exp-item-title {
  font-size: 0.79rem;
  font-weight: 600;
  color: var(--color-text-secondary);
  margin: 0 0 0.18rem;
  line-height: 1.35;
}

.exp-item-desc {
  font-size: 0.79rem;
  color: var(--color-text-muted);
  line-height: 1.62;
  margin: 0;
}

/* ── Publications ──────────────────────────────────────────────────────────── */
.pub-list { display: flex; flex-direction: column; gap: 1rem; }

.pub-card {
  border-left: 2px solid var(--color-accent);
  padding: 0.85rem 1.1rem;
  background: var(--color-bg-primary);
  border-radius: 0 8px 8px 0;
  border-top: 1px solid var(--color-border);
  border-right: 1px solid var(--color-border);
  border-bottom: 1px solid var(--color-border);
}

.pub-title {
  font-size: 0.88rem;
  font-weight: 700;
  color: var(--color-text-primary);
  margin: 0 0 0.22rem;
  line-height: 1.4;
}
.pub-title a {
  color: inherit;
  text-decoration: none;
  border-bottom: 1px solid color-mix(in srgb, var(--color-accent) 20%, transparent);
  transition: color 0.15s;
}
.pub-title a:hover { color: var(--color-accent); }

.pub-authors { font-size: 0.77rem; color: var(--color-text-muted); margin: 0 0 0.2rem; }
.pub-authors strong { color: var(--color-text-secondary); font-weight: 600; }

.pub-venue { font-size: 0.75rem; color: var(--color-text-muted); margin: 0; }
.pub-venue em { font-style: italic; color: var(--color-text-muted); }

/* ── Responsive ────────────────────────────────────────────────────────────── */
@media (max-width: 900px) {
  .research-wrap { max-width: 90%; }
  .int-2x2 { grid-template-columns: 1fr; }
  .exp-row { grid-template-columns: 70px 1fr; gap: 0 1.2rem; }
}
@media (max-width: 560px) {
  .research-wrap { max-width: 95%; margin: 2rem auto 4rem; }
  .exp-row { grid-template-columns: 1fr; gap: 0.3rem 0; }
  .exp-period { text-align: left; }
}
</style>

<div class="research-wrap">

<p class="rs-intro">I work on applied problems where statistical methods and human judgment intersect. The questions I find most useful are the ones that connect a technical choice to whether an organization makes a better or worse decision.</p>

<!-- ── Research Interests ──────────────────────────────────────────────────── -->
<span class="rs-lbl">Research Interests</span>

<div class="int-2x2">

  <!-- 01 Causal Inference -->
  <div class="ri-card">
    <div class="ri-viz">
      <svg width="176" height="88" viewBox="0 0 176 88" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
        <defs>
          <marker id="ci-a1" markerWidth="6" markerHeight="6" refX="5" refY="3" orient="auto">
            <path d="M0,0 L0,6 L6,3z" fill="var(--color-accent)"/>
          </marker>
          <marker id="ci-a2" markerWidth="6" markerHeight="6" refX="5" refY="3" orient="auto">
            <path d="M0,0 L0,6 L6,3z" fill="var(--color-border-strong)"/>
          </marker>
        </defs>
        <!-- Confounder (top center) -->
        <circle cx="88" cy="20" r="15" fill="var(--color-border)" stroke="var(--color-border-strong)" stroke-width="1.5"/>
        <text x="88" y="25" text-anchor="middle" font-size="9" fill="var(--color-text-muted)" font-family="IBM Plex Mono, monospace">Z</text>
        <!-- Treatment (bottom left) -->
        <circle cx="30" cy="72" r="15" fill="var(--color-border)" stroke="var(--color-border-strong)" stroke-width="1.5"/>
        <text x="30" y="77" text-anchor="middle" font-size="9" fill="var(--color-text-muted)" font-family="IBM Plex Mono, monospace">T</text>
        <!-- Outcome (bottom right) -->
        <circle cx="146" cy="72" r="15" fill="color-mix(in srgb, var(--color-accent-light) 10%, transparent)" stroke="color-mix(in srgb, var(--color-accent-light) 30%, transparent)" stroke-width="1.5"/>
        <text x="146" y="77" text-anchor="middle" font-size="9" fill="var(--color-accent-light)" font-family="IBM Plex Mono, monospace">Y</text>
        <!-- Z to T dashed -->
        <line x1="76" y1="31" x2="41" y2="61" stroke="var(--color-border-strong)" stroke-width="1.2" stroke-dasharray="3,2.5" marker-end="url(#ci-a2)"/>
        <!-- Z to Y dashed -->
        <line x1="100" y1="31" x2="135" y2="61" stroke="var(--color-border-strong)" stroke-width="1.2" stroke-dasharray="3,2.5" marker-end="url(#ci-a2)"/>
        <!-- T to Y solid (causal path) -->
        <line x1="46" y1="72" x2="130" y2="72" stroke="var(--color-accent)" stroke-width="1.5" marker-end="url(#ci-a1)"/>
        <!-- causal label -->
        <text x="88" y="85" text-anchor="middle" font-size="7" fill="var(--color-text-muted)" font-family="IBM Plex Mono, monospace">causal effect</text>
      </svg>
    </div>
    <div class="ri-body">
      <p class="ri-num">01</p>
      <p class="ri-title">Causal Inference &amp; Experiment Design</p>
      <p class="ri-desc">Most analytics tells you what happened. Causal inference tells you what caused it, and whether an action would change an outcome.<br><br>Standard correlation analysis cannot answer whether a retention program reduced churn or whether churned customers simply were not the ones enrolled. Without identifying the causal structure, decisions based on correlations fail when tested.<br><br>I work with methods that estimate causal effects when randomized experiments are not possible: difference-in-differences for comparing trends before and after an intervention, regression discontinuity for threshold-based decisions, and matching methods for observational data where treatment assignment was not random. The goal is producing estimates an organization can act on with some confidence they reflect real effects, not confounding.</p>
    </div>
  </div>

  <!-- 02 Human-AI Collaboration -->
  <div class="ri-card">
    <div class="ri-viz">
      <svg width="176" height="88" viewBox="0 0 176 88" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
        <defs>
          <marker id="hai-r" markerWidth="6" markerHeight="6" refX="5" refY="3" orient="auto">
            <path d="M0,0 L0,6 L6,3z" fill="var(--color-text-muted)"/>
          </marker>
        </defs>
        <!-- Human circle -->
        <circle cx="38" cy="36" r="26" fill="var(--color-border)" stroke="var(--color-border-strong)" stroke-width="1.5"/>
        <text x="38" y="41" text-anchor="middle" font-size="12" fill="var(--color-text-secondary)" font-weight="700" font-family="Inter, sans-serif">H</text>
        <!-- AI circle -->
        <circle cx="138" cy="36" r="26" fill="color-mix(in srgb, var(--color-accent-light) 10%, transparent)" stroke="color-mix(in srgb, var(--color-accent-light) 28%, transparent)" stroke-width="1.5"/>
        <text x="138" y="41" text-anchor="middle" font-size="11" fill="var(--color-accent-light)" font-weight="700" font-family="Inter, sans-serif">AI</text>
        <!-- Arrows -->
        <line x1="65" y1="32" x2="111" y2="32" stroke="var(--color-text-muted)" stroke-width="1.2" marker-end="url(#hai-r)"/>
        <line x1="111" y1="40" x2="65" y2="40" stroke="var(--color-text-muted)" stroke-width="1.2" marker-end="url(#hai-r)"/>
        <!-- 4D labels -->
        <text x="8" y="76" font-size="7.5" fill="var(--color-text-muted)" font-family="IBM Plex Mono, monospace">Delegation</text>
        <text x="8" y="87" font-size="7.5" fill="var(--color-text-muted)" font-family="IBM Plex Mono, monospace">Description</text>
        <text x="103" y="76" font-size="7.5" fill="var(--color-text-muted)" font-family="IBM Plex Mono, monospace">Discernment</text>
        <text x="103" y="87" font-size="7.5" fill="var(--color-text-muted)" font-family="IBM Plex Mono, monospace">Diligence</text>
      </svg>
    </div>
    <div class="ri-body">
      <p class="ri-num">02</p>
      <p class="ri-title">Human-AI Collaboration in Analytics</p>
      <p class="ri-desc">AI tools now handle tasks that used to require analyst effort: writing queries, generating charts, flagging anomalies, summarizing data. This changes what analysts need to be good at, not whether they are needed.<br><br>The skills that become more important are not technical. They are about working with AI effectively: knowing what to hand off, writing clear enough instructions that the AI does the right thing, catching errors in output that look correct but are not, and maintaining the same quality standards you would apply if you had done the work yourself.<br><br>I am interested in how these skills develop, how they differ across people, and whether analytics tool design makes them easier or harder to practice.</p>
      <div class="ri-tags">
        <span class="ri-tag">Delegation</span>
        <span class="ri-tag">Description</span>
        <span class="ri-tag">Discernment</span>
        <span class="ri-tag">Diligence</span>
      </div>
    </div>
  </div>

  <!-- 03 Uncertainty Quantification -->
  <div class="ri-card">
    <div class="ri-viz">
      <svg width="176" height="88" viewBox="0 0 176 88" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
        <!-- Bell curve fill -->
        <path d="M18,76 C30,76 44,22 88,16 C132,22 146,76 158,76Z" fill="color-mix(in srgb, var(--color-accent) 7%, transparent)"/>
        <!-- Bell curve stroke -->
        <path d="M18,76 C30,76 44,22 88,16 C132,22 146,76 158,76" stroke="var(--color-accent)" stroke-width="1.5" fill="none"/>
        <!-- Axis -->
        <line x1="18" y1="76" x2="158" y2="76" stroke="var(--color-border)" stroke-width="1"/>
        <!-- Center line -->
        <line x1="88" y1="16" x2="88" y2="76" stroke="var(--color-accent)" stroke-width="1" stroke-dasharray="3,2.5"/>
        <!-- CI ticks -->
        <line x1="56" y1="60" x2="56" y2="76" stroke="var(--color-border-strong)" stroke-width="1.2"/>
        <line x1="120" y1="60" x2="120" y2="76" stroke="var(--color-border-strong)" stroke-width="1.2"/>
        <!-- CI bracket -->
        <line x1="56" y1="82" x2="120" y2="82" stroke="var(--color-accent-light)" stroke-width="1.5"/>
        <line x1="56" y1="79" x2="56" y2="85" stroke="var(--color-accent-light)" stroke-width="1.5"/>
        <line x1="120" y1="79" x2="120" y2="85" stroke="var(--color-accent-light)" stroke-width="1.5"/>
        <text x="88" y="88" text-anchor="middle" font-size="7" fill="var(--color-accent-light)" font-family="IBM Plex Mono, monospace">95% CI</text>
        <text x="88" y="11" text-anchor="middle" font-size="7" fill="var(--color-text-muted)" font-family="IBM Plex Mono, monospace">point estimate</text>
      </svg>
    </div>
    <div class="ri-body">
      <p class="ri-num">03</p>
      <p class="ri-title">Uncertainty Quantification</p>
      <p class="ri-desc">Most analytical models report a point estimate: predicted revenue, expected churn rate, estimated treatment effect. That number comes from a model trained on noisy or incomplete data. The number alone hides how uncertain the estimate actually is.<br><br>When a model reports 80% confidence and is right 60% of the time, decisions based on it are less reliable than they appear. Uncalibrated uncertainty compounds when models feed automated systems or influence resource allocation.<br><br>I focus on making uncertainty quantification practical in production settings. Conformal prediction generates coverage-guaranteed intervals without strong distributional assumptions. Calibration testing identifies whether a model's stated confidence matches its actual accuracy. These are not refinements on the margin. They determine whether a model is trustworthy in a specific operational context.</p>
    </div>
  </div>

  <!-- 04 AI Fairness -->
  <div class="ri-card">
    <div class="ri-viz">
      <svg width="176" height="88" viewBox="0 0 176 88" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
        <!-- Axes -->
        <line x1="28" y1="12" x2="28" y2="76" stroke="var(--color-border)" stroke-width="1"/>
        <line x1="28" y1="76" x2="164" y2="76" stroke="var(--color-border)" stroke-width="1"/>
        <!-- Group A bar -->
        <rect x="44" y="26" width="26" height="50" fill="color-mix(in srgb, var(--color-accent) 14%, transparent)" stroke="color-mix(in srgb, var(--color-accent) 30%, transparent)" stroke-width="1" rx="2"/>
        <!-- Group B bar -->
        <rect x="88" y="42" width="26" height="34" fill="color-mix(in srgb, var(--color-accent-light) 14%, transparent)" stroke="color-mix(in srgb, var(--color-accent-light) 30%, transparent)" stroke-width="1" rx="2"/>
        <!-- Group C bar -->
        <rect x="132" y="54" width="26" height="22" fill="var(--color-border)" stroke="var(--color-border-strong)" stroke-width="1" rx="2"/>
        <!-- Dashed equity line -->
        <line x1="30" y1="42" x2="162" y2="42" stroke="var(--color-accent)" stroke-width="1" stroke-dasharray="4,2.5"/>
        <!-- Labels -->
        <text x="57" y="86" text-anchor="middle" font-size="7.5" fill="var(--color-text-muted)" font-family="IBM Plex Mono, monospace">A</text>
        <text x="101" y="86" text-anchor="middle" font-size="7.5" fill="var(--color-text-muted)" font-family="IBM Plex Mono, monospace">B</text>
        <text x="145" y="86" text-anchor="middle" font-size="7.5" fill="var(--color-text-muted)" font-family="IBM Plex Mono, monospace">C</text>
        <text x="164" y="40" font-size="7" fill="var(--color-accent)" font-family="IBM Plex Mono, monospace">equity</text>
      </svg>
    </div>
    <div class="ri-body">
      <p class="ri-num">04</p>
      <p class="ri-title">AI Fairness &amp; Safety</p>
      <p class="ri-desc">AI systems in hiring, lending, healthcare, and content moderation do not fail uniformly. They tend to fail more for specific groups, often in ways that track race, gender, or socioeconomic status. Most of these failures come from training data that reflects historical disparities, evaluation metrics that average over groups, and deployment conditions that differ from training conditions.<br><br>A model can be accurate on average while performing substantially worse for a minority group. Aggregate metrics hide this until someone specifically looks for it.<br><br>I am interested in rigorous evaluation of AI systems across demographic groups, measurement of failure patterns in production, and what governance structures make AI deployment accountable. Internal audits by the teams that built the system are not sufficient. Accountability requires external standards and transparent reporting.</p>
    </div>
  </div>

</div>

<!-- ── Research Experience ────────────────────────────────────────────────── -->
<span class="rs-lbl">Research Experience</span>

<div class="exp-list">

  <div class="exp-row">
    <div class="exp-period">2022&ndash;2023</div>
    <div class="exp-content">
      <p class="exp-lab"><a href="https://monjegroup.myportfolio.com/" target="_blank">Monje Lab</a></p>
      <p class="exp-meta">Undergraduate Researcher &middot; Dr. Viviana Monje-Galvan &middot; Chemical and Biological Engineering, University at Buffalo</p>
      <ul class="exp-items">
        <li>
          <p class="exp-item-title">Molecular dynamics data analysis</p>
          <p class="exp-item-desc">Processed and analyzed large-scale MD simulation trajectories of lipid bilayer systems, extracting structural and thermodynamic properties to characterize membrane behavior under physiological conditions.</p>
        </li>
        <li>
          <p class="exp-item-title">Simulation modeling</p>
          <p class="exp-item-desc">Contributed to constructing and validating all-atom membrane models using CHARMM force fields, parameterizing lipid compositions to replicate organelle-specific membrane environments.</p>
        </li>
        <li>
          <p class="exp-item-title">Protein membrane modeling with deep learning</p>
          <p class="exp-item-desc">Applied deep learning methods to identify patterns in protein-lipid interaction data from MD simulation outputs, supporting classification of membrane protein insertion mechanisms.</p>
        </li>
      </ul>
    </div>
  </div>

  <div class="exp-row">
    <div class="exp-period">2020&ndash;2022</div>
    <div class="exp-content">
      <p class="exp-lab"><a href="https://www.uh.edu/pharmacy/directory-home/pps-faculty/xinli-liu/" target="_blank">Liu Lab</a></p>
      <p class="exp-meta">Undergraduate Researcher &middot; Dr. Xinli Liu &middot; College of Pharmacy, University of Houston</p>
      <ul class="exp-items">
        <li>
          <p class="exp-item-title">Targeted drug delivery systems</p>
          <p class="exp-item-desc">Supported research on nanoparticle and nanoconjugate design for tumor-specific drug delivery, contributing to data collection and analysis for preclinical evaluations of novel drug combination systems.</p>
        </li>
        <li>
          <p class="exp-item-title">Pharmacometabolomics data pipelines</p>
          <p class="exp-item-desc">Assisted with data processing workflows for Mass Spectrometry Imaging experiments, applying computational methods to spatial pharmacometabolomics datasets to support drug discovery analysis.</p>
        </li>
        <li>
          <p class="exp-item-title">Nanomedicine and drug resistance</p>
          <p class="exp-item-desc">Contributed to investigations of nanomedicine-based approaches to overcome multidrug resistance in cancer and infectious disease models, including quantitative analysis of experimental results.</p>
        </li>
      </ul>
    </div>
  </div>

</div>

<!-- ── Publications ─────────────────────────────────────────────────────────── -->
<span class="rs-lbl">Publications</span>

<div class="pub-list">
  <div class="pub-card">
    <p class="pub-title">
      <a href="https://www.jove.com/t/65712" target="_blank">Realistic Membrane Modeling Using Complex Lipid Mixtures in Simulation Studies</a>
    </p>
    <p class="pub-authors">O. Campbell, <strong>V. Le</strong>, A. Aguirre, V. Monje-Galvan</p>
    <p class="pub-venue"><em>JoVE (Journal of Visualized Experiments)</em>, e65712 &middot; 2023</p>
  </div>
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
