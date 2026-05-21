# Breton Sikh Association v2.0 — Vercel Deployment Guide

## What's in this folder
- `index.html` — Complete v2.0 landing page (new brand system)
- `vercel.json` — Vercel configuration (security headers, caching, clean URLs)
- `logo.png` — Your BSA logo (you need to add this file)
- `.gitignore` — Git ignore rules
- This guide

## Important: Add your logo
Place your BSA logo as `logo.png` in this folder before deploying. The site references it for the hero medallion, nav, and footer.

---

## Option A: Deploy via Vercel CLI (Fastest)

### 1. Install Vercel CLI
```bash
npm install -g vercel
```

### 2. Navigate to this folder
```bash
cd bsa-website
```

### 3. Deploy
```bash
vercel
```
- It will ask you to log in (opens browser)
- Select "Link to existing project?" → No
- Project name: `bsa-website`
- Directory: `.` (current)
- It deploys automatically and gives you a preview URL

### 4. Deploy to production
```bash
vercel --prod
```

---

## Option B: Deploy via GitHub + Vercel Dashboard

### 1. Push to GitHub
```bash
cd bsa-website
git init
git add .
git commit -m "Breton Sikh Association website"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/bsa-website.git
git push -u origin main
```

### 2. Import in Vercel
1. Go to https://vercel.com and sign in with GitHub
2. Click "Add New..." → "Project"
3. Import your `bsa-website` repository
4. Framework Preset: "Other"
5. Click "Deploy"

---

## Moving Your Domain (bretonsikhassociation.com)

### Step 1: Add domain in Vercel
1. Go to your project in Vercel dashboard
2. Settings → Domains
3. Type `bretonsikhassociation.com` and click Add
4. Also add `www.bretonsikhassociation.com`

### Step 2: Update DNS at your registrar
Vercel will show you the DNS records needed. Typically:

**Option A — Nameservers (recommended):**
Point your domain's nameservers to:
```
ns1.vercel-dns.com
ns2.vercel-dns.com
```

**Option B — DNS Records:**
```
Type: A     | Name: @   | Value: 76.76.21.21
Type: CNAME | Name: www | Value: cname.vercel-dns.com
```

Update these at wherever you bought your domain (GoDaddy, Namecheap, Cloudflare, etc.)

### Step 3: Remove from Netlify (after DNS propagates)
1. Wait for the site to work on Vercel (check https://bretonsikhassociation.com)
2. Go to Netlify dashboard
3. Site Settings → Domain management → Remove custom domain
4. Optionally delete the Netlify site

---

## SSL/HTTPS
Vercel automatically provisions a free SSL certificate once DNS is pointed correctly. No action needed.

## Notes
- DNS propagation can take 5 minutes to 48 hours (usually under 30 minutes)
- Don't remove the domain from Netlify until it's working on Vercel
- Your logo.png should be placed in this same folder alongside index.html
