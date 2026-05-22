# Van Le  -  Personal Portfolio Website

---


### Introduction
A data scientist's portfolio website is not just a resume  -  it is a demonstration of technical judgment. This site was built to present research, projects, and professional background in a clean, fast, and fully customizable format. The goal was to own the presentation layer completely: no medium.com, no Notion, no third-party constraints.

Built on **Jekyll** with the **Minimal Mistakes** theme  -  a static site generator that compiles Markdown and YAML into a fully deployable website. Hosted on **GitHub Pages** for free, with zero server maintenance. The site is structured around four core pages:

- **About**  -  Professional identity, interests, and background
- **Projects**  -  Data science and research portfolio
- **Research**  -  Academic work and publications
- **CV**  -  Downloadable curriculum vitae

The theme is configured via `_config.yml` and `_data/info.yml`  -  no HTML required for content changes.

### Result
A fast, responsive, version-controlled personal site deployable from a single `git push`. Every content change is tracked in git history. The full design system (typography, layout, navigation, dark mode skins) is available via SCSS variables  -  no external dependencies, no vendor lock-in.

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
- Push to the `main` branch  -  GitHub Actions / Travis CI automatically builds and deploys
- Custom domain: add a `CNAME` file with your domain and configure DNS

---

