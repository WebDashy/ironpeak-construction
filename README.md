# Ironpeak Construction — WebDashy Template

A single-page marketing site template for a construction/general-contractor
business, built for use as a live preview template in [WebDashy](https://github.com/garmorpro/webdashy).

Plain HTML, CSS, and vanilla JS — no build step, no dependencies. Deploys as-is
to GitHub Pages, Vercel, Netlify, or any static host.

## Structure

- `index.html` — all page content and markup
- `styles.css` — all styling (custom properties for the palette/type at the top)
- `script.js` — mobile nav toggle + footer year

## Customizing for a real client

Everything here is placeholder content meant to be swapped out:

- Business name, phone, email, and address (search for "Ironpeak" and the
  placeholder contact details in `index.html`)
- Hero headline/copy, service descriptions, project names, testimonials
- The three "project" cards use plain color-block placeholders — replace
  `.project-media` in `styles.css` with real photography
- Contact form currently does nothing (`onsubmit="return false;"`) — wire it
  up to a real form handler (Formspree, Netlify Forms, a serverless function,
  etc.) before going live
- Update the license number in the footer, or remove it if not applicable

## Local preview

No build tools needed — just open `index.html` in a browser, or serve the
folder locally:

```bash
python3 -m http.server 8080
```

## Deploying

**GitHub Pages** (this repo): Settings → Pages → Deploy from branch → `main` / `/ (root)`.
