# SpaceBrew-1 Teaser Site

A single-page, static teaser for the SpaceBrew-1 limited drop from Starbase Brewing — the world's first beer brewed with spaceflown yeast.

## What it is
- One self-contained file: `index.html` (HTML + CSS + JS inline, no build step, no dependencies).
- Modeled on limited-edition drop pages: full-bleed dark hero, restrained typography, live countdown, single email capture.
- Brand system: Orbitron (display) + Exo 2 (body), deep-space black, Mars-red accent. Subtle animated starfield.

## Run it
Just open `index.html` in a browser, or serve the folder:
```
python3 -m http.server -d spacebrew-teaser 8080
```

## Email capture (Klaviyo)
The signup form posts directly to Klaviyo's client-side subscription API. Set two
values in the `KLAVIYO` object inside the `<script>` at the bottom of `index.html`:

- **`COMPANY_ID`** — your Klaviyo **public** API key / Site ID (6 chars).
  Klaviyo → Settings → Account → API Keys → "Public API Key". Safe to expose client-side.
- **`LIST_ID`** — the list to subscribe people to.
  Klaviyo → Audience → Lists & Segments → your list → Settings (or read it from the URL).

Notes:
- Uses the `client/subscriptions` endpoint — only the **public** key is needed; never put
  your private key in this file.
- If the list has **double opt-in** enabled (Klaviyo's default), subscribers get a
  confirmation email before being added — recommended for compliance.
- No private keys, no backend, no build step required.

## Deploy
Static — drop the folder on Netlify, Vercel, Cloudflare Pages, or GitHub Pages as-is.
