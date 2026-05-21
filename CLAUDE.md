# Breton Sikh Association — Website

## Overview
Static HTML landing page for Breton Sikh Association, a volunteer Sikh NGO based in the Breton area.

## Tech Stack
- Vanilla HTML/CSS/JS (no framework)
- Hosted on Vercel (static deploy, no build step)
- Domain: bretonsikhassociation.com (to be connected)

## Project Structure
- `index.html` — Single-page landing site (hero, about, programs, contact)
- `vercel.json` — Vercel config: security headers, cache rules, SPA rewrites
- `logo.png` — BSA logo (needs to be added; referenced in nav, hero, footer)
- `.gitignore` — Git ignore rules

## Deployment
- **Auto-deploy on push**: every `git push` deploys to Vercel automatically
- GitHub repo: EightSeven-maker/bsa-website
- Preview URLs auto-generated for every branch/push
- No manual build step — Vercel serves the static files directly

## Development Notes
- Add `logo.png` to the root before production launch
- All changes go through: edit → commit → push → Vercel auto-deploys
- To add features, edit `index.html` directly (it's a single-page site)
- vercel.json controls routing, headers, and caching

## Domain Setup (pending)
1. Add domain in Vercel dashboard: Settings → Domains → bretonsikhassociation.com
2. Point DNS at registrar to Vercel nameservers or CNAME
3. Vercel provisions SSL automatically
4. Remove domain from Netlify after DNS propagates
