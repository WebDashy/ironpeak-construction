# Ironpeak Construction — WebDashy Template

A multi-page, SEO-structured marketing site template for a construction/
general-contractor business, built for use as a live preview template in
[WebDashy](https://github.com/garmorpro/webdashy).

Built with [Jekyll](https://jekyllrb.com/) using only the plugins GitHub
Pages runs natively (`jekyll-seo-tag`, `jekyll-sitemap`) — **no local build
step required to deploy**: push to `main` and GitHub Pages builds it for
you. A local Jekyll install is only needed if you want to preview changes
before pushing (see below).

## Why multiple pages

Search engines rank pages, not sites — a single page trying to cover every
service dilutes all of them. This template gives every service its own
URL, unique title/meta description, and dedicated content, so each can
actually rank for its own search terms (e.g. "custom home builder Denver"
vs. "kitchen renovation Denver").

## Structure

```
_config.yml           site-wide settings + business info (used across every page)
_layouts/default.html shared page shell — head/SEO tags, header, footer
_includes/             header.html, footer.html
assets/css/styles.css  all styling
assets/js/script.js    mobile nav toggle
index.html             home
services/index.html    services hub — links to each service page below
services/<slug>/       one folder per service, each its own page
about/                 company story + testimonials
projects/               project gallery
contact/                contact form + info
robots.txt              allows crawling, points to the auto-generated sitemap
```

`sitemap.xml` is generated automatically by the `jekyll-sitemap` plugin —
there's no file for it in this repo, GitHub builds it on every deploy.

## What's already handled for SEO

- Unique `<title>` and meta description per page (set in each page's front
  matter, rendered via `jekyll-seo-tag`)
- Canonical URLs and Open Graph / Twitter Card tags (also via `jekyll-seo-tag`)
- `LocalBusiness`/`GeneralContractor` structured data site-wide, plus a
  `Service` structured-data block on each service page
- Auto-generated `sitemap.xml` + `robots.txt`
- Semantic HTML, one `<h1>` per page, real (non-thin) content on every
  service page — search engines penalize near-duplicate pages, so each
  service page has genuinely different copy, not a find-and-replace clone

## Customizing for a real client

- Business name, phone, email, address, and license number all live in
  `_config.yml` under `business:` — change them once, they update
  everywhere (header, footer, contact page, structured data)
- Update `title`/`description`/`url` at the top of `_config.yml` too
- Swap the placeholder color-block project images (`.project-media` in
  `styles.css`) for real photography, and add real `alt` text once you do
- Contact form currently does nothing (`onsubmit="return false;"`) — wire
  it up to a real handler (Formspree, Netlify Forms, a serverless
  function, etc.) before going live
- Add a real social share image and set `logo:` in `_config.yml` to it,
  so shared links get a preview image

## Local preview

Requires Ruby (this repo pins Jekyll to the exact version GitHub Pages
runs, via the `github-pages` gem):

```bash
bundle install
bundle exec jekyll serve
```

Then open `http://localhost:4000/ironpeak-construction/`.

## Deploying

**GitHub Pages** (this repo): Settings → Pages → Deploy from branch →
`main` / `/ (root)`. GitHub builds the Jekyll site automatically on every
push — no local build or upload step needed.
