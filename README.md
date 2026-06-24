# Yinuo Liu's Personal Website

Personal academic website for Yinuo Liu, Data Analyst Coordinator at Nationwide Children's Hospital.  
Live site: [yinuoliu0708.github.io](https://yinuoliu0708.github.io)

Built on [Academic Pages](https://github.com/academicpages/academicpages.github.io).

---

## Folder Structure

```
.
├── _config.yml              # Site-wide settings (title, author, URLs, plugins)
├── _config_docker.yml       # Overrides for local Docker development
├── _pages/                  # Static pages (About, CV, Publications, Talks, Teaching, etc.)
├── _publications/           # One .md file per publication
├── _talks/                  # One .md file per talk or presentation
├── _teaching/               # One .md file per course taught
├── _layouts/                # HTML layout templates (single, archive, CV, etc.)
├── _includes/               # Reusable HTML partials (header, footer, sidebar, SEO, etc.)
├── _data/
│   ├── navigation.yml       # Top navigation bar links
│   ├── authors.yml          # Author metadata
│   └── ui-text.yml          # Localization strings
├── _sass/                   # SCSS stylesheets (layout, theme, vendor)
├── assets/
│   ├── css/                 # Compiled CSS + CV-specific styles
│   ├── js/                  # JavaScript (main bundle, collapse, plugins)
│   ├── fonts/               # Academicons font files
│   └── webfonts/            # Font Awesome web fonts
├── images/                  # Profile photos, favicons, and other site images
├── files/
│   ├── Papers/              # PDF copies of papers
│   ├── Slides/              # Presentation slide decks
│   └── Bibtex/              # BibTeX citation files
├── markdown_generator/      # Python/Jupyter scripts to generate publication and talk .md files from TSV/BibTeX
├── scripts/
│   ├── cv_markdown_to_json.py   # Converts CV markdown to JSON
│   └── update_cv_json.sh        # Shell helper to regenerate CV JSON
├── talkmap/                 # Leaflet map assets for the talk map page
├── talkmap.py               # Generates org-locations.js for the talk map
├── .github/workflows/       # GitHub Actions (e.g., scrape_talks.yml)
├── Dockerfile               # Docker image for local Jekyll development
├── docker-compose.yaml      # Docker Compose config
└── host_locally.sh          # Convenience script to serve the site locally
```

---

## Running Locally

**Option 1 — Docker (recommended):**

```bash
docker compose up
```

**Option 2 — Jekyll directly:**

```bash
./host_locally.sh
# or
jekyll serve -l -H localhost
```

Then open `http://localhost:4000`.

---

## Updating Content

| What to update | Where |
|---|---|
| Bio, links, social profiles | `_config.yml` → `author:` section |
| About page text | `_pages/about.md` |
| CV page | `_pages/cv.md` |
| Publications | Add a file to `_publications/` |
| Talks | Add a file to `_talks/` |
| Teaching | Add a file to `_teaching/` |
| Navigation menu | `_data/navigation.yml` |
| Profile photo | `images/` (update avatar path in `_config.yml`) |
| PDF files (papers, slides, CV) | `files/` |

To bulk-generate publication markdown from a BibTeX file, use the notebooks in `markdown_generator/`.

---

## Deployment

Pushes to `master` deploy automatically via GitHub Pages.  
Check build status: **Actions → All workflows**  
View live site: **Settings → Pages**
