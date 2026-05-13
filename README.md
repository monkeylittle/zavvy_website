# zavvy_website

Marketing landing page for [Zavvy](https://zavvyapp.com) — the barcode-scanning
shopping basket app that compares totals across major supermarkets in the
UK and Ireland.

## Stack

Plain HTML + CSS. No build step, no JS framework. Open `index.html` in a
browser, or serve the directory with any static file server:

```bash
python3 -m http.server 8000        # then visit http://localhost:8000
```

## Files

- `index.html` — single-page landing site (hero, how-it-works, stores, FAQ).
- `styles.css` — design system + section styles.

## Deploy

Suitable for any static host: GitHub Pages, Cloudflare Pages, S3 +
CloudFront, Netlify, Vercel. Point the host at the repo root.
