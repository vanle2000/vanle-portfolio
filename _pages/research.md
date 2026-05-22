---
title: "Research"
permalink: /research/
layout: single
author_profile: false
classes: wide
---

<style>
.research-wrap { max-width: 860px; margin: 0 auto; padding: 0 1.5rem; }

/* Section labels */
.rs-label {
  font-size: 0.68rem;
  font-weight: 700;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: #94a3b8;
  padding-bottom: 0.5rem;
  border-bottom: 1px solid #f1f5f9;
  margin: 0 0 1.75rem;
}

/* Interest cards */
.interest-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(190px, 1fr));
  gap: 0.85rem;
  margin-bottom: 3rem;
}

.int-card {
  background: #f8fafc;
  border: 1px solid #e2e8f0;
  border-radius: 8px;
  padding: 1rem 1.1rem;
  transition: border-color 0.15s;
}

.int-card:hover { border-color: #bae6fd; }
.int-card__icon { font-size: 1.2rem; margin-bottom: 0.4rem; }
.int-card__title { font-size: 0.82rem; font-weight: 700; color: #1e293b; margin-bottom: 0.2rem; }
.int-card__desc { font-size: 0.74rem; color: #64748b; line-height: 1.45; margin: 0; }

/* Lab cards */
.lab-card {
  border: 1px solid #e2e8f0;
  border-radius: 10px;
  padding: 1.6rem 1.75rem;
  margin-bottom: 1.25rem;
  background: #fff;
}

.lab-card__header {
  display: flex;
  align-items: flex-start;
  justify-content: space-between;
  gap: 1rem;
  margin-bottom: 0.85rem;
  flex-wrap: wrap;
}

.lab-card__left {}

.lab-card__name {
  font-size: 1rem;
  font-weight: 700;
  color: #0f172a;
  margin: 0 0 0.2rem;
  letter-spacing: -0.01em;
}

.lab-card__name a {
  color: inherit;
  text-decoration: none;
  border-bottom: 1.5px solid #bae6fd;
  transition: color 0.15s, border-color 0.15s;
}

.lab-card__name a:hover { color: #0284c7; border-color: #0284c7; }

.lab-card__pi {
  font-size: 0.8rem;
  color: #64748b;
  margin: 0;
}

.lab-card__pi a { color: #0284c7; text-decoration: none; }
.lab-card__pi a:hover { text-decoration: underline; }

.lab-card__meta {
  text-align: right;
  flex-shrink: 0;
}

.lab-card__period {
  font-size: 0.75rem;
  font-weight: 600;
  color: #94a3b8;
  background: #f8fafc;
  border: 1px solid #e2e8f0;
  border-radius: 5px;
  padding: 0.2rem 0.6rem;
  white-space: nowrap;
}

.lab-card__role {
  font-size: 0.73rem;
  color: #64748b;
  margin-top: 0.3rem;
  text-align: right;
}

/* Research statement list */
.research-list {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  flex-direction: column;
  gap: 0.65rem;
}

.research-list li {
  display: flex;
  gap: 0.75rem;
  font-size: 0.86rem;
  color: #334155;
  line-height: 1.65;
}

.research-list li::before {
  content: "";
  width: 5px;
  height: 5px;
  border-radius: 50%;
  background: #0284c7;
  flex-shrink: 0;
  margin-top: 0.6rem;
}

.research-list li strong {
  color: #1e293b;
  font-weight: 600;
}

/* Publications */
.pub-list {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  margin-bottom: 3rem;
}

.pub-card {
  border-left: 3px solid #0284c7;
  padding: 0.9rem 1.1rem;
  background: #fafafa;
  border-radius: 0 8px 8px 0;
  border-top: 1px solid #f1f5f9;
  border-right: 1px solid #f1f5f9;
  border-bottom: 1px solid #f1f5f9;
}

.pub-card.pending { border-left-color: #f59e0b; }

.pub-card__title {
  font-size: 0.88rem;
  font-weight: 700;
  color: #0f172a;
  margin: 0 0 0.25rem;
  line-height: 1.4;
}

.pub-card__title a { color: inherit; text-decoration: none; border-bottom: 1px solid #bae6fd; }
.pub-card__title a:hover { color: #0284c7; }

.pub-card__authors {
  font-size: 0.78rem;
  color: #64748b;
  margin: 0 0 0.25rem;
  line-height: 1.5;
}

.pub-card__authors strong { color: #334155; font-weight: 600; }

.pub-card__venue {
  font-size: 0.76rem;
  color: #94a3b8;
  margin: 0;
}

.pub-card__venue em { font-style: italic; color: #64748b; }

.pub-badge {
  display: inline-block;
  font-size: 0.65rem;
  font-weight: 700;
  letter-spacing: 0.05em;
  text-transform: uppercase;
  padding: 0.15rem 0.5rem;
  border-radius: 4px;
  margin-left: 0.4rem;
  vertical-align: middle;
}

.pub-badge.under-review { background: #fffbeb; color: #92400e; border: 1px solid #fde68a; }
.pub-badge.published { background: #f0fdf4; color: #166534; border: 1px solid #bbf7d0; }

/* Research interest narrative */
.interest-statement {
  margin-bottom: 3rem;
}

.interest-statement__lead {
  font-size: 0.97rem;
  line-height: 1.8;
  color: #334155;
  max-width: 720px;
  margin: 0 0 1.5rem;
}

.interest-statement__sub {
  font-size: 0.72rem;
  font-weight: 700;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  color: #94a3b8;
  margin: 0 0 1.1rem;
}

.focus-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1rem;
}

.focus-item {
  display: flex;
  gap: 1rem;
  padding: 1.1rem 1.2rem;
  border: 1px solid #e2e8f0;
  border-radius: 8px;
  background: #f8fafc;
  transition: border-color 0.15s;
}

.focus-item:hover { border-color: #bae6fd; }

.focus-num {
  font-size: 0.68rem;
  font-weight: 800;
  color: #0284c7;
  letter-spacing: 0.05em;
  flex-shrink: 0;
  padding-top: 0.1rem;
}

.focus-body {}

.focus-title {
  font-size: 0.85rem;
  font-weight: 700;
  color: #1e293b;
  margin: 0 0 0.35rem;
  letter-spacing: -0.01em;
  line-height: 1.3;
}

.focus-desc {
  font-size: 0.78rem;
  color: #64748b;
  line-height: 1.6;
  margin: 0;
}

@media (max-width: 640px) { .focus-grid { grid-template-columns: 1fr; } }

@media (max-width: 640px) {
  .lab-card__header { flex-direction: column; }
  .lab-card__meta { text-align: left; }
  .lab-card__role { text-align: left; }
  .interest-grid { grid-template-columns: 1fr 1fr; }
}
</style>

<div class="research-wrap">

<!-- ── Research Interests ──────────────────────────────────────────────────── -->
<p class="rs-label">Research Interests</p>

<div class="interest-statement">
  <p class="interest-statement__lead">
    My current work is primarily applied. I am building a research direction around how data, analytics systems, and AI tools shape the quality of decisions made by people and organizations.
  </p>
  <p class="interest-statement__sub">Current areas of focus:</p>
  <div class="focus-grid">

    <div class="focus-item">
      <span class="focus-num">01</span>
      <div class="focus-body">
        <p class="focus-title">Causal Inference &amp; Experiment Design</p>
        <p class="focus-desc">
          Designing and analyzing experiments in business and operational settings where randomization is constrained, data is observational, and decisions have real costs. Interested in difference-in-differences, regression discontinuity, and matched observational designs applied outside academic contexts.
        </p>
      </div>
    </div>

    <div class="focus-item">
      <span class="focus-num">02</span>
      <div class="focus-body">
        <p class="focus-title">Human-AI Collaboration in Analytics Workflows</p>
        <p class="focus-desc">
          How analysts and AI tools interact in practice: where automation improves decisions, where it introduces new failure modes, and how to design workflows that keep humans in the right position in the loop. Interested in agentic systems applied to structured data tasks.
        </p>
      </div>
    </div>

    <div class="focus-item">
      <span class="focus-num">03</span>
      <div class="focus-body">
        <p class="focus-title">Quantifying Uncertainty Under Chaotic Data</p>
        <p class="focus-desc">
          Standardizing how uncertainty is measured, communicated, and propagated in pipelines built on noisy, incomplete, or shifting data distributions. Interested in calibration, conformal prediction, and Bayesian methods as alternatives to point-estimate reporting.
        </p>
      </div>
    </div>

    <div class="focus-item">
      <span class="focus-num">04</span>
      <div class="focus-body">
        <p class="focus-title">AI Fairness, Safety, and Responsible Use</p>
        <p class="focus-desc">
          How generative AI systems fail, who they fail for, and what structural measures actually reduce harm in practice. Interested in bias measurement and mitigation in production ML, misuse prevention in Gen AI applications, and the standards and governance frameworks needed to make AI deployment accountable rather than aspirational.
        </p>
      </div>
    </div>

  </div>
</div>

<!-- ── Research Experience ────────────────────────────────────────────────── -->
<p class="rs-label">Research Experience</p>

<!-- Monje Lab -->
<div class="lab-card">
  <div class="lab-card__header">
    <div class="lab-card__left">
      <p class="lab-card__name">
        <a href="https://monjegroup.myportfolio.com/" target="_blank">Monje Lab</a>
      </p>
      <p class="lab-card__pi">
        Principal Investigator: <a href="https://engineering.buffalo.edu/chemical-biological/people/faculty-directory.host.html/content/shared/engineering/chemical-biological/profiles/faculty/monje-viviana.detail.html" target="_blank">Dr. Viviana Monje-Galvan</a>
        &middot; Department of Chemical and Biological Engineering, University at Buffalo
      </p>
    </div>
    <div class="lab-card__meta">
      <span class="lab-card__period">2022 &ndash; 2023</span>
      <p class="lab-card__role">Undergraduate Researcher</p>
    </div>
  </div>
  <ul class="research-list">
    <li>
      <strong>Molecular Dynamics Data Analysis.</strong>
      Processed and analyzed large-scale MD simulation trajectories of lipid bilayer systems, extracting structural and thermodynamic properties to characterize membrane behavior under physiologically relevant conditions.
    </li>
    <li>
      <strong>Simulation Modeling.</strong>
      Contributed to constructing and validating all-atom membrane models using CHARMM force fields, parameterizing lipid compositions to replicate organelle-specific membrane environments for computational biophysics studies.
    </li>
    <li>
      <strong>Protein Membrane Modeling with Deep Learning.</strong>
      Applied deep learning methods to identify patterns in protein-lipid interaction data from MD simulation outputs, supporting classification of membrane protein insertion mechanisms and lipid binding site characterization.
    </li>
  </ul>
</div>

<!-- Liu Lab -->
<div class="lab-card">
  <div class="lab-card__header">
    <div class="lab-card__left">
      <p class="lab-card__name">
        <a href="https://www.uh.edu/pharmacy/directory-home/pps-faculty/xinli-liu/" target="_blank">Liu Lab</a>
      </p>
      <p class="lab-card__pi">
        Principal Investigator: <a href="https://www.uh.edu/pharmacy/about-us/directory-home/pps-faculty/xinli-liu/" target="_blank">Dr. Xinli Liu</a>
        &middot; The Institute for Drug Education and Research, College of Pharmacy, University of Houston
      </p>
    </div>
    <div class="lab-card__meta">
      <span class="lab-card__period">2020 &ndash; 2022</span>
      <p class="lab-card__role">Undergraduate Researcher</p>
    </div>
  </div>
  <ul class="research-list">
    <li>
      <strong>Targeted Drug Delivery Systems.</strong>
      Supported research on nanoparticle and nanoconjugate design for tumor-specific drug delivery, contributing to data collection and analysis for preclinical evaluations of novel drug combination systems.
    </li>
    <li>
      <strong>Pharmacometabolomics Data Pipelines.</strong>
      Assisted with data processing workflows for Mass Spectrometry Imaging (MSI) experiments, applying computational methods to spatial pharmacometabolomics datasets to support drug discovery and development analysis.
    </li>
    <li>
      <strong>Nanomedicine and Drug Resistance.</strong>
      Contributed to investigations of nanomedicine-based approaches to overcome multidrug resistance in cancer and infectious disease models, including data organization and quantitative analysis of experimental results.
    </li>
  </ul>
</div>

<!-- ── Publications ───────────────────────────────────────────────────────── -->
<p class="rs-label" style="margin-top: 3rem;">Publications</p>

<div class="pub-list">

  <div class="pub-card">
    <p class="pub-card__title">
      <a href="https://www.jove.com/t/65712" target="_blank">
        Realistic Membrane Modeling Using Complex Lipid Mixtures in Simulation Studies
      </a>
    </p>
    <p class="pub-card__authors">
      O. Campbell, <strong>V. Le</strong>, A. Aguirre, V. Monje-Galvan
    </p>
    <p class="pub-card__venue">
      <em>JoVE (Journal of Visualized Experiments)</em>, e65712 &middot; 2023
    </p>
  </div>

</div>

</div>
