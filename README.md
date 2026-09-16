# stuartcorby.com

Static site for Stuart Corby's personal site, redesigned from the Coda export.

## Structure

- `index.html` — the main site (Career / Notables / Free IP / Snow & Water), a single page with hash-based
  section switching (`#home`, `#notables`, `#ip`, `#outdoors`) handled by a small inline script — no build
  step, no framework.
- `patents/` — the five patent write-ups, each a standalone printable HTML page styled to look like a typeset
  claim document:
  - `non-collision-serialisation.html`
  - `same-or-better-nft.html`
  - `seniority-tiered-financing.html`
  - `state-locking.html`
  - `url-gateway.html`
- `assets/` — photos and patent figures (`assets/figures/`).
- `netlify.toml` — publish directory (`.`), no build command, security headers, and a few short-URL redirects
  into `patents/`.

This was converted from the Coda `.dc.html` export (`x-dc` component template + `doc-page` custom element) into
plain static HTML/CSS/JS, so it has no dependency on Coda's runtime (`support.js`/`doc-page.js`) or on React
being loaded at runtime.

## Deploy

1. Push this repo to GitHub.
2. Connect it in Netlify — publish directory `.`, no build command (already set in `netlify.toml`).
3. Point DNS at your registrar: CNAME `www` → the Netlify subdomain, A record for the apex domain per
   Netlify's instructions.
4. Netlify auto-provisions SSL once DNS resolves.

## Local preview

Any static file server works, e.g.:

```
npx serve .
```
