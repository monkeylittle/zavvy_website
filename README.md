# zavvy_website

Marketing site for [Zavvy](https://zavvyapp.com) — the barcode-scanning
shopping basket app that compares totals across major supermarkets in the
UK and Ireland.

## Stack

Hand-written HTML + CSS over a minimal **Jekyll** layout — GitHub Pages
builds it automatically, so there is no local build step required. Pages
are 100% plain HTML (no Markdown); Jekyll is here only for:

- A single shared shell (`_layouts/default.html`) that pulls in
  `_includes/nav.html`, `_includes/footer.html`, and JSON-LD structured
  data — so the header, footer, and SEO foundation are edited in one
  place.
- The `jekyll-seo-tag` plugin, which emits the per-page `<title>`,
  meta description, OpenGraph and Twitter card tags from each page's
  frontmatter.
- The `jekyll-sitemap` plugin, which auto-generates `/sitemap.xml`.

To preview locally (optional — pushes to `main` build live on GH Pages):

```bash
bundle install                     # one-off
bundle exec jekyll serve           # http://localhost:4000
```

Or, if you only want to look at the raw HTML without rendering the
layout:

```bash
python3 -m http.server 8000        # http://localhost:8000 (no nav/footer)
```

## Files

- `_config.yml` — site-wide config (title, description, plugins,
  default OG image).
- `_layouts/default.html` — shared shell every page renders into.
- `_includes/` — `nav.html`, `footer.html`, `structured-data.html`.
- `index.html` — the landing page.
- `privacy/`, `terms/`, `support/` — content pages.
- `styles.css` — design system + section styles.
- `robots.txt` — points crawlers at the auto-generated sitemap.

To add a new page, create `<slug>/index.html` with a frontmatter block
at the top:

```html
---
layout: default
title: Zavvy — <page title>
description: <one-line meta description for SEO + social shares>
permalink: /<slug>/
---
<section class="hero"> ... </section>
```

## Deploy

GitHub Pages, building from `main`. The `CNAME` file pins
`zavvyapp.com`.
