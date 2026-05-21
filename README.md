# Van Le — Personal Portfolio Website

---

## Case Study

### Introduction
A data scientist's portfolio website is not just a resume — it is a demonstration of technical judgment. This site was built to present research, projects, and professional background in a clean, fast, and fully customizable format. The goal was to own the presentation layer completely: no medium.com, no Notion, no third-party constraints.

### Problem
Off-the-shelf portfolio platforms (Squarespace, Wix, Cargo) limit customization and own your content. GitHub profile READMEs lack structure for showcasing research and long-form project writeups. The need was a self-hosted, version-controlled, statically-generated site that could evolve alongside the work it documents.

### Solution
Built on **Jekyll** with the **Minimal Mistakes** theme — a static site generator that compiles Markdown and YAML into a fully deployable website. Hosted on **GitHub Pages** for free, with zero server maintenance. The site is structured around four core pages:

- **About** — Professional identity, interests, and background
- **Projects** — Data science and research portfolio
- **Research** — Academic work and publications
- **CV** — Downloadable curriculum vitae

The theme is configured via `_config.yml` and `_data/info.yml` — no HTML required for content changes.

### Result
A fast, responsive, version-controlled personal site deployable from a single `git push`. Every content change is tracked in git history. The full design system (typography, layout, navigation, dark mode skins) is available via SCSS variables — no external dependencies, no vendor lock-in.

---

## Tech Stack

| Layer | Tools |
|-------|-------|
| Static site generator | Jekyll (Ruby) |
| Theme | Minimal Mistakes |
| Hosting | GitHub Pages |
| CI/CD | Travis CI (`.travis.yml`) |
| Styling | SASS/SCSS (custom skin system) |
| Search | Lunr.js (client-side full-text search) |
| Package management | npm, Bundler (Gemfile) |

---

## Data Architecture

```
Repository Structure
│
├── _config.yml              ← Site-wide settings (title, author, theme skin, navigation)
├── _data/
│   ├── info.yml             ← Author bio, education, contact links
│   ├── navigation.yml       ← Header navigation links
│   └── ui-text.yml          ← Internationalization strings
├── _pages/
│   ├── about.md             ← About page content
│   ├── cv.md                ← CV page
│   ├── projects.md          ← Projects listing
│   └── research.md          ← Research page
├── _posts/                  ← Blog posts / news items (Markdown)
├── assets/
│   ├── css/                 ← Compiled stylesheets
│   ├── files/cv             ← CV PDF file
│   └── js/                  ← Bundled JavaScript (lunr, jQuery, plugins)
└── _sass/                   ← SCSS source (theme variables, layout, skins)
```

---

## Key Insights & Analytics

1. **Static sites load 10–100x faster than CMS-driven sites** — no database, no server-side rendering, no cold start. All content is pre-compiled HTML/CSS/JS served directly from CDN.

2. **Version control as content management** — every update to the portfolio is a git commit with a message, author, and timestamp. This creates an auditable history of your professional evolution.

3. **Lunr.js enables full-text search client-side** — users can search all content without a backend search service. Search index is generated at build time.

4. **10 built-in color skins** (air, aqua, contrast, dark, dirt, mint, neon, plum, sunrise, default) — the entire visual identity can be changed in one line of `_config.yml`.

---

## How to Run Locally / Deploy

**Prerequisites:** Ruby, Bundler, Node.js, npm

```bash
# Clone the repo
git clone https://github.com/vanle2000/vanle-portfolio.git
cd vanle-portfolio

# Install Ruby dependencies
bundle install

# Install JS dependencies
npm install

# Serve locally with live reload
bundle exec jekyll serve --livereload
# → Open http://localhost:4000

# Build for production
bundle exec jekyll build
# → Output in _site/ folder
```

**Deploying to GitHub Pages:**
- Push to the `main` branch — GitHub Actions / Travis CI automatically builds and deploys
- Custom domain: add a `CNAME` file with your domain and configure DNS

**Customization:**
- Edit `_data/info.yml` to update name, education, contact links
- Edit `_config.yml` to change theme skin, site title, author profile
- Add new pages in `_pages/` as Markdown files with YAML frontmatter
- Add CV PDF to `assets/files/cv/`

---

## Challenges & What Could Be Improved

| Challenge | Improvement Path |
|-----------|-----------------|
| About page has placeholder content | Write 2–3 lines on DS + BIE focus area and current goals |
| Projects page is empty | Add project cards linking to each data science repo with a screenshot and one-line summary |
| CV file not deployed in `assets/files/cv/` | Upload current CV as PDF |
| No blog posts in `_posts/` | Write short technical posts — even 3–5 posts signal active thought leadership |
| Travis CI is deprecated for public repos | Migrate CI/CD to GitHub Actions |
| No Google Analytics or Plausible configured | Add analytics to track which projects get the most attention |
| No dark mode toggle for visitors | Enable via Minimal Mistakes skin toggle configuration |
