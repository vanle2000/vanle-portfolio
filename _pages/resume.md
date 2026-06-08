---
title: ""
permalink: /resume/
layout: single
author_profile: false
classes: wide
---

<style>
/* ── Resume page ──────────────────────────────────────────────────────────── */
.resume-wrap {
  max-width: 860px;
  margin: 3rem auto 5rem;
  padding: 0 clamp(1rem, 4vw, 2rem);
}

/* Header row */
.resume-header {
  display: flex;
  align-items: flex-end;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 1.25rem;
  margin-bottom: 2rem;
}

.resume-header-left h1 {
  font-family: "Playfair Display", Georgia, serif;
  font-size: clamp(1.5rem, 4vw, 2rem);
  font-weight: 800;
  color: #1C1410;
  letter-spacing: -0.01em;
  line-height: 1.15;
  margin: 0 0 0.3rem;
}

.resume-header-left p {
  font-family: "IBM Plex Mono", monospace;
  font-size: 0.7rem;
  font-weight: 500;
  color: #A89888;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  margin: 0;
}

.resume-actions {
  display: flex;
  gap: 0.65rem;
  flex-wrap: wrap;
}

.btn-download {
  display: inline-flex;
  align-items: center;
  gap: 0.45rem;
  font-family: "IBM Plex Mono", monospace;
  font-size: 0.75rem;
  font-weight: 600;
  letter-spacing: 0.04em;
  color: #FDFAF5;
  background: #7A2838;
  border: none;
  border-radius: 6px;
  padding: 0.62rem 1.25rem;
  text-decoration: none;
  transition: background 0.2s, transform 0.2s cubic-bezier(.34,1.56,.64,1),
              box-shadow 0.2s;
  cursor: pointer;
}
.btn-download:hover {
  background: #5C1A24;
  transform: translateY(-1px);
  box-shadow: 0 4px 16px rgba(122,40,56,.28);
  text-decoration: none;
  color: #FDFAF5;
}

.btn-open {
  display: inline-flex;
  align-items: center;
  gap: 0.45rem;
  font-family: "IBM Plex Mono", monospace;
  font-size: 0.75rem;
  font-weight: 600;
  letter-spacing: 0.04em;
  color: #7A2838;
  background: rgba(122,40,56,.07);
  border: 1.5px solid rgba(122,40,56,.22);
  border-radius: 6px;
  padding: 0.62rem 1.25rem;
  text-decoration: none;
  transition: all 0.2s cubic-bezier(.34,1.56,.64,1);
}
.btn-open:hover {
  background: rgba(122,40,56,.12);
  border-color: rgba(122,40,56,.4);
  transform: translateY(-1px);
  text-decoration: none;
  color: #7A2838;
}

/* PDF viewer container */
.pdf-frame-wrap {
  border: 1px solid #EAE0CE;
  border-radius: 10px;
  overflow: hidden;
  box-shadow: 0 4px 24px rgba(28,20,16,.07), 0 1px 4px rgba(28,20,16,.04);
  background: #F4EDE0;
}

.pdf-frame {
  display: block;
  width: 100%;
  height: 1060px;
  border: none;
}

/* Fallback for browsers that don't render PDF in iframe */
.pdf-fallback {
  display: none;
  padding: 3rem 2rem;
  text-align: center;
}

.pdf-fallback p {
  font-size: 0.9rem;
  color: #7A6A5A;
  margin: 0 0 1.25rem;
}

/* Mobile: swap to link-only */
@media (max-width: 700px) {
  .pdf-frame { height: 600px; }
  .resume-header { flex-direction: column; align-items: flex-start; }
}

@media (max-width: 480px) {
  .pdf-frame-wrap { border-radius: 8px; }
  .pdf-frame { height: 480px; }
}
</style>

<div class="resume-wrap">

  <div class="resume-header">
    <div class="resume-header-left">
      <h1>Van (Elizabeth) Le</h1>
      <p>Data Scientist &nbsp;&middot;&nbsp; Business Intelligence Engineer &nbsp;&middot;&nbsp; Analytics Engineer</p>
    </div>
    <div class="resume-actions">
      <a class="btn-download"
         href="{{ site.baseurl }}/assets/files/VanLe_DataScientist_resume.pdf"
         download="VanLe_DataScientist_resume.pdf">
        <svg width="13" height="13" viewBox="0 0 16 16" fill="currentColor" aria-hidden="true">
          <path d="M.5 9.9a.5.5 0 0 1 .5.5v2.5a1 1 0 0 0 1 1h12a1 1 0 0 0 1-1v-2.5a.5.5 0 0 1 1 0v2.5a2 2 0 0 1-2 2H2a2 2 0 0 1-2-2v-2.5a.5.5 0 0 1 .5-.5z"/>
          <path d="M7.646 11.854a.5.5 0 0 0 .708 0l3-3a.5.5 0 0 0-.708-.708L8.5 10.293V1.5a.5.5 0 0 0-1 0v8.793L5.354 8.146a.5.5 0 1 0-.708.708l3 3z"/>
        </svg>
        Download PDF
      </a>
      <a class="btn-open"
         href="{{ site.baseurl }}/assets/files/VanLe_DataScientist_resume.pdf"
         target="_blank" rel="noopener">
        <svg width="13" height="13" viewBox="0 0 16 16" fill="currentColor" aria-hidden="true">
          <path fill-rule="evenodd" d="M8.636 3.5a.5.5 0 0 0-.5-.5H1.5A1.5 1.5 0 0 0 0 4.5v10A1.5 1.5 0 0 0 1.5 16h10a1.5 1.5 0 0 0 1.5-1.5V7.864a.5.5 0 0 0-1 0V14.5a.5.5 0 0 1-.5.5h-10a.5.5 0 0 1-.5-.5v-10a.5.5 0 0 1 .5-.5h6.636a.5.5 0 0 0 .5-.5z"/>
          <path fill-rule="evenodd" d="M16 .5a.5.5 0 0 0-.5-.5h-5a.5.5 0 0 0 0 1h3.793L6.146 9.146a.5.5 0 1 0 .708.708L15 1.707V5.5a.5.5 0 0 0 1 0v-5z"/>
        </svg>
        Open in Tab
      </a>
    </div>
  </div>

  <div class="pdf-frame-wrap">
    <iframe
      class="pdf-frame"
      src="{{ site.baseurl }}/assets/files/VanLe_DataScientist_resume.pdf"
      title="Van (Elizabeth) Le, Data Scientist Resume"
      aria-label="Resume PDF viewer">
      <div class="pdf-fallback">
        <p>Your browser does not support inline PDF viewing.</p>
        <a class="btn-download"
           href="{{ site.baseurl }}/assets/files/VanLe_DataScientist_resume.pdf"
           download="VanLe_DataScientist_resume.pdf">
          Download PDF
        </a>
      </div>
    </iframe>
  </div>

</div>
