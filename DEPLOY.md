# Vercel Semaglutide — Deployment Guide

## ✅ Files to upload to GitHub

```
vercel-semaglutide/
├─ index.html               ← Semaglutide landing page (entry point)
├─ vercel.json              ← Vercel config (cleanUrls only)
├─ DEPLOY.md                ← This file
├─ download                 ← Blank file (required by repo convention)
└─ images/
   ├─ hero-bg.jpg
   ├─ coach-chris-lane.png
   ├─ final-cta-bg.jpg
   ├─ science-bg.jpg
   ├─ clinical-results.jpg
   ├─ pharmacy-greenwich.jpg
   ├─ patient-result-1.jpg
   ├─ patient-result-2.jpg
   ├─ doctors/
   │  ├─ dr-palumbo.jpg
   │  ├─ angela-kifer-thomas.jpg
   │  ├─ dr-patel.jpg
   │  ├─ dr-colon-molero.jpg
   │  ├─ samuel-palmer.jpg
   │  ├─ dr-akler.jpg
   │  ├─ brett-whaley.jpg
   │  ├─ michael-gype.jpg
   │  ├─ dr-chandler.jpg
   │  ├─ brittany-umana.jpg
   │  └─ dr-ahmed.jpg
   └─ logos/
      ├─ lecom.svg
      ├─ utmb-health.svg
      ├─ cu-colorado.svg
      ├─ ponce.svg
      ├─ vanderbilt.svg
      ├─ tel-aviv.svg
      ├─ texas-tech.svg
      ├─ cleveland-state.svg
      ├─ maryville.svg
      └─ kentucky.svg
```

---

## 🚀 Deploy to Vercel (step-by-step)

### 1 — Push to GitHub
```bash
git init
git add .
git commit -m "initial commit"
git branch -M main
git remote add origin https://github.com/YOUR-ORG/semaglutide-landing.git
git push -u origin main
```

### 2 — Import in Vercel
1. Go to https://vercel.com/new
2. Click **Import Git Repository** → select your repo
3. **Framework Preset**: `Other`
4. **Root Directory**: *(leave blank)*
5. **Build Command**: *(leave blank)*
6. **Output Directory**: *(leave blank)*
7. **Install Command**: *(leave blank)*
8. Click **Deploy**

### 3 — Done ✅
Vercel detects `index.html` at the root and serves the static site directly. No build step required.

---

## ⚠️ What NOT to do

| Action | Why it breaks |
|---|---|
| Add a `build` script to package.json | Vercel runs it and fails |
| Use `"/(.*)"` rewrite in vercel.json | Intercepts ALL requests including CSS and images |
| Set Root Directory to a subfolder in Vercel | Vercel looks in the wrong place |
| Use absolute image paths like `/images/hero-bg.jpg` | Breaks when served from a subfolder |

---

## ✅ Iframe Compliance (conventions.md §1)

This page is fully iframe-safe:

- [x] No `vh`, `dvh`, or `svh` units used in any section height
- [x] Hero uses `min-height: clamp(560px, 60vw, 860px); height: auto`
- [x] All hero images use `object-fit: cover`
- [x] All `position: absolute` layers inside parent with explicit non-viewport height
- [x] All image paths are relative (`images/` not `/images/`)
- [x] No circular sizing dependencies

---

## 📞 CTA URLs

| Button | URL |
|---|---|
| Primary CTA | `https://precisiontelemed.com/start-your-weight-loss-program-semaglutide/` |
| Secondary CTA | `#science` (anchor) |
| General consultation | `https://precisiontelemed.com/start-general-consultation-program/` |
