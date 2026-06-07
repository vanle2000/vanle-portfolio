---
title: "Research"
permalink: /research/
layout: single
author_profile: false
classes: wide
---

<style>
/* ── Page container ────────────────────────────────────────────────────────── */
.research-wrap {
  max-width: 860px;
  margin: 0 auto;
  padding: 3.5rem clamp(2rem, 6vw, 4rem) 5rem;
}

/* ── Section labels ────────────────────────────────────────────────────────── */
.rs-label {
  font-family: "IBM Plex Mono", monospace;
  font-size: 0.63rem;
  font-weight: 700;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  color: #7A2838;
  padding-bottom: 0.5rem;
  border-bottom: 1px solid #EAE0CE;
  margin: 0 0 2rem;
  display: flex;
  align-items: center;
  gap: 0.8rem;
}
.rs-label::after {
  content: "";
  flex: 1;
  height: 1px;
  background: linear-gradient(90deg, rgba(122,40,56,.18) 0%, transparent 100%);
  border: none;
  padding: 0;
}

/* ── Research statement ────────────────────────────────────────────────────── */
.interest-statement { margin-bottom: 3rem; }

.interest-statement__lead {
  font-size: 0.97rem;
  line-height: 1.82;
  color: #4A3C34;
  max-width: 720px;
  margin: 0 0 1.5rem;
}

/* ── Focus grid (other interests) ─────────────────────────────────────────── */
.focus-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1rem;
  margin-bottom: 1rem;
}

.focus-item {
  display: flex;
  gap: 1rem;
  padding: 1.1rem 1.2rem;
  border: 1px solid #EAE0CE;
  border-radius: 8px;
  background: #FDFAF5;
  transition: border-color 0.2s, box-shadow 0.2s;
}

.focus-item:hover {
  border-color: rgba(122,40,56,.25);
  box-shadow: 0 4px 16px rgba(122,40,56,.07);
}

.focus-num {
  font-family: "IBM Plex Mono", monospace;
  font-size: 0.67rem;
  font-weight: 700;
  color: #7A2838;
  letter-spacing: 0.05em;
  flex-shrink: 0;
  padding-top: 0.1rem;
}

.focus-title {
  font-size: 0.86rem;
  font-weight: 700;
  color: #1C1410;
  margin: 0 0 0.35rem;
  letter-spacing: -0.01em;
  line-height: 1.3;
}

.focus-desc {
  font-size: 0.78rem;
  color: #7A6A5A;
  line-height: 1.62;
  margin: 0;
}

/* ── Human-AI Collaboration featured section ───────────────────────────────── */
.hai-section {
  border: 1px solid rgba(122,40,56,.18);
  border-radius: 12px;
  padding: 2rem 2.25rem;
  background: #FDFAF5;
  margin-bottom: 3rem;
  position: relative;
  overflow: hidden;
}

.hai-section::before {
  content: "";
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 2px;
  background: linear-gradient(90deg, #7A2838, #2C4A3E);
  border-radius: 12px 12px 0 0;
}

.hai-eyebrow {
  font-family: "IBM Plex Mono", monospace;
  font-size: 0.6rem;
  font-weight: 700;
  letter-spacing: 0.14em;
  text-transform: uppercase;
  color: #7A2838;
  margin: 0 0 0.5rem;
}

.hai-title {
  font-family: "Playfair Display", Georgia, serif;
  font-size: 1.35rem;
  font-weight: 800;
  color: #1C1410;
  letter-spacing: -0.01em;
  line-height: 1.2;
  margin: 0 0 1.4rem;
}

.hai-lead {
  font-size: 0.94rem;
  line-height: 1.82;
  color: #4A3C34;
  margin: 0 0 0.85rem;
  max-width: 700px;
}

.hai-lead strong { color: #1C1410; font-weight: 600; }

/* ── Why it matters callout ────────────────────────────────────────────────── */
.hai-why {
  background: #F4EDE0;
  border-left: 2px solid #7A2838;
  border-radius: 0 6px 6px 0;
  padding: 0.9rem 1.15rem;
  margin: 1.25rem 0 1.5rem;
}

.hai-why p {
  font-size: 0.85rem;
  color: #4A3C34;
  line-height: 1.72;
  margin: 0;
}

.hai-why strong { color: #7A2838; font-weight: 600; }

/* ── 4D Framework grid ─────────────────────────────────────────────────────── */
.hai-sub {
  font-family: "IBM Plex Mono", monospace;
  font-size: 0.62rem;
  font-weight: 700;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  color: #A89888;
  margin: 0 0 1rem;
}

.four-d {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 0.85rem;
  margin-bottom: 1.5rem;
}

.d-card {
  padding: 1.05rem 1.15rem;
  border: 1px solid #EAE0CE;
  border-radius: 8px;
  background: #ffffff;
  transition: border-color 0.2s, transform 0.2s;
}

.d-card:hover {
  border-color: rgba(44,74,62,.3);
  transform: translateY(-2px);
}

.d-header {
  display: flex;
  align-items: baseline;
  gap: 0.5rem;
  margin-bottom: 0.45rem;
}

.d-letter {
  font-family: "Playfair Display", Georgia, serif;
  font-size: 1.35rem;
  font-weight: 800;
  color: #2C4A3E;
  line-height: 1;
  flex-shrink: 0;
}

.d-name {
  font-size: 0.85rem;
  font-weight: 700;
  color: #1C1410;
  letter-spacing: -0.01em;
}

.d-desc {
  font-size: 0.77rem;
  color: #7A6A5A;
  line-height: 1.6;
  margin: 0;
}

/* ── Research directions ───────────────────────────────────────────────────── */
.hai-directions {
  border-top: 1px solid #EAE0CE;
  padding-top: 1.25rem;
  margin-top: 0;
}

.hai-directions-title {
  font-family: "IBM Plex Mono", monospace;
  font-size: 0.62rem;
  font-weight: 700;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  color: #A89888;
  margin: 0 0 1rem;
}

.direction-list {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  flex-direction: column;
  gap: 0.55rem;
}

.direction-list li {
  display: flex;
  gap: 0.7rem;
  font-size: 0.83rem;
  color: #4A3C34;
  line-height: 1.62;
}

.direction-list li::before {
  content: "";
  width: 5px;
  height: 5px;
  border-radius: 50%;
  background: #7A2838;
  flex-shrink: 0;
  margin-top: 0.6em;
}

.direction-list li strong { color: #1C1410; font-weight: 600; }

/* ── Lab cards ─────────────────────────────────────────────────────────────── */
.lab-card {
  border: 1px solid #EAE0CE;
  border-radius: 10px;
  padding: 1.6rem 1.75rem;
  margin-bottom: 1.25rem;
  background: #FDFAF5;
}

.lab-card__header {
  display: flex;
  align-items: flex-start;
  justify-content: space-between;
  gap: 1rem;
  margin-bottom: 0.85rem;
  flex-wrap: wrap;
}

.lab-card__name {
  font-size: 1rem;
  font-weight: 700;
  color: #1C1410;
  margin: 0 0 0.2rem;
  letter-spacing: -0.01em;
}

.lab-card__name a {
  color: inherit;
  text-decoration: none;
  border-bottom: 1.5px solid rgba(122,40,56,.25);
  transition: color 0.15s, border-color 0.15s;
}

.lab-card__name a:hover { color: #7A2838; border-color: #7A2838; }

.lab-card__pi { font-size: 0.8rem; color: #7A6A5A; margin: 0; }
.lab-card__pi a { color: #7A2838; text-decoration: none; }
.lab-card__pi a:hover { text-decoration: underline; }

.lab-card__meta { text-align: right; flex-shrink: 0; }

.lab-card__period {
  font-family: "IBM Plex Mono", monospace;
  font-size: 0.72rem;
  font-weight: 600;
  color: #A89888;
  background: #F4EDE0;
  border: 1px solid #EAE0CE;
  border-radius: 4px;
  padding: 0.2rem 0.6rem;
  white-space: nowrap;
}

.lab-card__role { font-size: 0.73rem; color: #7A6A5A; margin-top: 0.3rem; text-align: right; }

/* ── Research list ─────────────────────────────────────────────────────────── */
.research-list {
  list-style: none;
  padding: 0; margin: 0;
  display: flex; flex-direction: column; gap: 0.65rem;
}

.research-list li {
  display: flex;
  gap: 0.75rem;
  font-size: 0.86rem;
  color: #4A3C34;
  line-height: 1.65;
}

.research-list li::before {
  content: "";
  width: 5px; height: 5px; border-radius: 50%;
  background: #7A2838;
  flex-shrink: 0; margin-top: 0.6rem;
}

.research-list li strong { color: #1C1410; font-weight: 600; }

/* ── Publications ──────────────────────────────────────────────────────────── */
.pub-list { display: flex; flex-direction: column; gap: 1rem; margin-bottom: 3rem; }

.pub-card {
  border-left: 2px solid #7A2838;
  padding: 0.9rem 1.1rem;
  background: #FDFAF5;
  border-radius: 0 8px 8px 0;
  border-top: 1px solid #EAE0CE;
  border-right: 1px solid #EAE0CE;
  border-bottom: 1px solid #EAE0CE;
}

.pub-card.pending { border-left-color: #C4784A; }

.pub-card__title { font-size: 0.88rem; font-weight: 700; color: #1C1410; margin: 0 0 0.25rem; line-height: 1.4; }
.pub-card__title a { color: inherit; text-decoration: none; border-bottom: 1px solid rgba(122,40,56,.22); transition: color 0.15s; }
.pub-card__title a:hover { color: #7A2838; }

.pub-card__authors { font-size: 0.78rem; color: #7A6A5A; margin: 0 0 0.25rem; line-height: 1.5; }
.pub-card__authors strong { color: #4A3C34; font-weight: 600; }

.pub-card__venue { font-size: 0.76rem; color: #A89888; margin: 0; }
.pub-card__venue em { font-style: italic; color: #7A6A5A; }

.pub-badge {
  display: inline-block;
  font-family: "IBM Plex Mono", monospace;
  font-size: 0.62rem; font-weight: 700;
  letter-spacing: 0.05em; text-transform: uppercase;
  padding: 0.15rem 0.5rem; border-radius: 4px;
  margin-left: 0.4rem; vertical-align: middle;
}

.pub-badge.under-review { background: rgba(196,120,74,.08); color: #7A2838; border: 1px solid rgba(196,120,74,.25); }
.pub-badge.published { background: rgba(44,74,62,.07); color: #2C4A3E; border: 1px solid rgba(44,74,62,.25); }

/* ── Responsive ────────────────────────────────────────────────────────────── */
@media (max-width: 700px) {
  .focus-grid { grid-template-columns: 1fr; }
  .four-d { grid-template-columns: 1fr; }
  .lab-card__header { flex-direction: column; }
  .lab-card__meta { text-align: left; }
  .lab-card__role { text-align: left; }
  .hai-section { padding: 1.5rem; }
}
</style>

<div class="research-wrap">

<!-- ── Research Interests ──────────────────────────────────────────────────── -->
<p class="rs-label">Research Interests</p>

<div class="interest-statement">
  <p class="interest-statement__lead">
    My research direction centers on how data systems, AI tools, and the people who use them jointly produce — or fail to produce — reliable, actionable decisions. The problems I find most tractable sit at the boundary between statistical methodology and the organizational and cognitive realities of applied analytics.
  </p>
</div>

<!-- ── Human-AI Collaboration — Featured ───────────────────────────────────── -->
<div class="hai-section">

  <p class="hai-eyebrow">Primary Research Interest</p>
  <h2 class="hai-title">Human-AI Collaboration in Analytics Workflows</h2>

  <p class="hai-lead">
    The hypothesis driving this line of work is that <strong>effective human-AI collaboration in analytics is not primarily a technical problem — it is a competency problem.</strong> As AI automates an expanding share of the execution layer in data workflows — feature engineering, model selection, code generation, narrative summarization — the bottleneck shifts from whether analysts can perform these tasks to whether they can <em>direct, evaluate, and govern</em> AI-assisted performance of them. That shift is under-studied and under-prepared for at both the individual and organizational level.
  </p>

  <p class="hai-lead">
    Most organizations are deploying AI in analytics workflows without frameworks for assessing whether their teams can effectively use them. Capability evaluations focus on tool familiarity, not on the underlying skills that determine whether tool use produces reliable outputs. The result is a predictable failure mode: pipelines that look AI-enabled but whose outputs have quietly degraded because no one maintained the critical human contributions at scale.
  </p>

  <div class="hai-why">
    <p>
      <strong>Why this matters in HCI:</strong> Prior work in human-automation interaction (Parasuraman &amp; Riley, 1997; Bainbridge, 1983) established that removing humans from routine tasks does not eliminate their cognitive role — it changes it. In analytics, this manifests as a shift from execution to oversight. But oversight is not a passive or automatic skill. It requires the analyst to maintain an accurate model of what the AI is doing, when to trust its outputs, and when to intervene. HCI research has a structural role to play in understanding how that oversight capability can be measured, developed, and supported through interface design.
    </p>
  </div>

  <p class="hai-sub">The 4D Framework: Core Competencies for Effective AI Collaboration</p>

  <div class="four-d">

    <div class="d-card">
      <div class="d-header">
        <span class="d-letter">D</span>
        <span class="d-name">Delegation</span>
      </div>
      <p class="d-desc">
        The capacity to allocate tasks appropriately between human judgment and AI execution — informed by an accurate mental model of what AI does well, where it fails silently, and what the downstream cost of errors is per task type. Miscalibrated delegation is a root failure: over-delegation transfers judgment to a system that cannot reliably exercise it; under-delegation leaves value on the table and creates bottlenecks.
      </p>
    </div>

    <div class="d-card">
      <div class="d-header">
        <span class="d-letter">D</span>
        <span class="d-name">Description</span>
      </div>
      <p class="d-desc">
        The ability to formulate analytical intent as a precise, unambiguous specification — defining the question, the data context, the acceptance criteria, and anticipated edge cases. This is not "prompt engineering" in a shallow sense; it is an epistemic skill about how to communicate intent across a representation gap. Poor description means garbage-in at the task allocation level, independent of the AI's capabilities.
      </p>
    </div>

    <div class="d-card">
      <div class="d-header">
        <span class="d-letter">D</span>
        <span class="d-name">Discernment</span>
      </div>
      <p class="d-desc">
        Critical evaluation of AI-generated outputs — detecting when outputs are plausible but incorrect, contextually inappropriate, or missing important nuance. Discernment requires domain knowledge (to recognize violations of business logic or statistical assumptions) and epistemic calibration (to resist the seductiveness of confident, well-formatted AI outputs). It is the competency most eroded by automation complacency.
      </p>
    </div>

    <div class="d-card">
      <div class="d-header">
        <span class="d-letter">D</span>
        <span class="d-name">Diligence</span>
      </div>
      <p class="d-desc">
        Sustained quality maintenance in a high-automation environment. Automation complacency — the gradual erosion of vigilance as AI handles routine work — is a documented failure mode in aviation, medical imaging, and process control (Parasuraman et al., 2010). The question is whether analytics is structurally vulnerable to the same dynamic, and what practices, interfaces, and team norms prevent quality degradation as workflows become more AI-mediated.
      </p>
    </div>

  </div>

  <div class="hai-directions">
    <p class="hai-directions-title">Research Directions — What Would Make This Happen</p>
    <ul class="direction-list">
      <li>
        <strong>Operationalization and measurement.</strong> Translate each competency into behavioral indicators measurable through think-aloud protocols, log analysis, and output quality scoring. Develop and validate a 4D Competency Scale (4DCS) as a psychometric instrument usable in field settings.
      </li>
      <li>
        <strong>Controlled experiments linking competency to quality.</strong> Design analytical tasks where ground-truth output quality is measurable. Assign participants with varied 4D competency profiles to AI-assisted and unaided conditions. Test whether competency scores predict quality outcomes independently of technical skill.
      </li>
      <li>
        <strong>Cognitive task analysis of expert versus novice analysts.</strong> Use think-aloud protocols during naturalistic AI-assisted analysis to surface how delegation and discernment decisions are actually made — and how they fail. Build a taxonomy of failure modes mapped back to deficits in specific 4D competencies.
      </li>
      <li>
        <strong>Interface design for discernment scaffolding.</strong> Analytics tool interfaces currently optimize for task completion speed. Redesign and evaluate interfaces that scaffold discernment: calibrated confidence displays, source attribution, structured uncertainty flags, and "override trails" that document when and why analysts rejected AI suggestions.
      </li>
      <li>
        <strong>Longitudinal study of teams adopting AI tools.</strong> Track analytics teams over 12–18 months as they integrate LLM-based tools. Measure how individual 4D competency profiles evolve, whether they diverge across team members, and what organizational factors (culture, process, incentives) predict competency retention versus atrophy.
      </li>
      <li>
        <strong>Training intervention design.</strong> Develop deliberate practice exercises for each competency and evaluate their effectiveness in a randomized design. Identify which competencies respond to structured training versus requiring extended on-the-job calibration.
      </li>
    </ul>
  </div>

</div>

<!-- ── Other Research Interests ─────────────────────────────────────────────── -->
<div class="focus-grid" style="margin-bottom:3rem;">

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
    <span class="focus-num">03</span>
    <div class="focus-body">
      <p class="focus-title">Uncertainty Quantification Under Chaotic Data</p>
      <p class="focus-desc">
        Standardizing how uncertainty is measured, communicated, and propagated in pipelines built on noisy, incomplete, or shifting data. Interested in calibration, conformal prediction, and Bayesian methods as alternatives to point-estimate reporting.
      </p>
    </div>
  </div>

  <div class="focus-item">
    <span class="focus-num">04</span>
    <div class="focus-body">
      <p class="focus-title">AI Fairness, Safety &amp; Responsible Deployment</p>
      <p class="focus-desc">
        How generative AI systems fail, who they fail for, and what structural measures reduce harm in practice. Interested in bias measurement in production ML, misuse prevention in Gen AI applications, and governance frameworks that make deployment accountable rather than aspirational.
      </p>
    </div>
  </div>

</div>

<!-- ── Research Experience ────────────────────────────────────────────────── -->
<p class="rs-label">Research Experience</p>

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

<!-- ── Publications ─────────────────────────────────────────────────────────── -->
<p class="rs-label" style="margin-top:3rem;">Publications</p>

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
