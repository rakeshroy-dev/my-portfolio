# 🚀 Rakesh Roy — Portfolio Website

**Python/Django Backend Engineer Portfolio**
A single-file, dependency-free (besides fonts/icons via CDN) portfolio with a dark/light theme, a live interactive terminal, an animated skills radar, and a one-click résumé download.

🔗 **Live site:** [https://rakeshroy-dev.github.io/my-portfolio](https://rakeshroy-dev.github.io/my-portfolio/) <!-- update to your actual GitHub Pages URL -->

---

## 📁 File Structure

```
portfolio/
├── index.html     ← Entire site — markup, CSS, and JS in one file
├── resume.pdf     ← Résumé served for the "Resume" download button
└── README.md      ← This file
```

> No build step, no framework, no `node_modules`. Everything renders straight from `index.html`.

---

## ✨ Features

| Feature | Details |
|---|---|
| 🌗 **Dark / light theme** | Toggle in the navbar, persisted via `data-theme` on `<html>` |
| ⌨️ **Typed role rotator** | Cycles through role titles in the hero |
| 💻 **Live Terminal** | Interactive fake shell — `whoami`, `skills`, `projects`, `experience`, `contact`, `stats`, `clear` |
| 📡 **Skills radar (SVG)** | Hand-drawn proficiency radar chart, generated at runtime |
| 📊 **Animated stat counters** | Experience is calculated *live* from a start date, not hardcoded |
| 📄 **Résumé download** | Fetches `resume.pdf` and re-saves it locally with a dynamic, date-stamped filename — see below |
| ✉️ **Contact form** | Wired to EmailJS (free tier) — no backend required |
| 📱 **Fully responsive** | Custom mobile bottom nav + full-screen mobile menu, no Bootstrap |
| 🎯 **Scroll-based active nav** | Highlights the current section as you scroll |

---

## 📄 Résumé Download — Dynamic Filename

The **Resume** button (in the navbar, mobile menu, and hero) fetches `resume.pdf` from the repo root and re-saves it in the visitor's browser with a professional, date-stamped filename:

```
Rakesh_Roy_Python_Developer_DD_MM_YYYY.pdf
```

The date is generated from the visitor's local clock at click time (`new Date()`), so it always reflects **today's date** — no manual updates needed. The logic lives near the bottom of `index.html`, inside `downloadResume()`.

**To update your résumé:**
1. Replace `resume.pdf` in the repo root with your latest CV (keep the filename `resume.pdf`).
2. Commit & push — the download button automatically serves the new file with the current date.

If `resume.pdf` fails to fetch (e.g. blocked by CORS on some non–GitHub-Pages hosts), the button falls back to a plain `<a download>` link so the file still downloads, just without the JS-driven rename on a few older browsers.

---

## 🌐 Deployment — GitHub Pages (already live)

This repo is already deployed on GitHub Pages. To redeploy after edits:

```bash
git add index.html resume.pdf README.md
git commit -m "Update portfolio content"
git push origin main
```

GitHub Pages rebuilds automatically from the branch/folder configured under
**Repo → Settings → Pages → Build and deployment**. No build step is needed since `index.html` is static.

If you're setting this up fresh:

```bash
git init
git add .
git commit -m "Initial portfolio deploy"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
git push -u origin main
```

Then enable Pages: **Settings → Pages → Source: Deploy from a branch → `main` / `root`**.
Your site goes live at `https://YOUR_USERNAME.github.io/YOUR_REPO/` (or `https://YOUR_USERNAME.github.io/` if the repo is named `YOUR_USERNAME.github.io`).

> ⚠️ `resume.pdf` must sit in the **same folder** as `index.html` on Pages (repo root, unless you're serving from `/docs`) or the download button won't find it.

---

## ⚙️ Customization Guide

### Update contact info
Search `index.html` for these and replace:
```
rakeshroy.dev@gmail.com   → your email
+91-8919736316 / 918919736316 → your phone / WhatsApp number
rakeshroy-dev             → your LinkedIn handle
```

### Update the "live" experience counter
The years-of-experience shown across the hero, stats, and mini-stats are calculated automatically from a single start date — search for:
```js
const start = new Date(2021, 6, 1); // July 1 2021
```
Change this if your first full-time start date changes; every counter on the page updates from this one value.

### Contact form (EmailJS)
Update your own keys near the bottom of `index.html`:
```js
const EJS_CONFIG = {
  publicKey  : 'YOUR_PUBLIC_KEY',
  serviceId  : 'YOUR_SERVICE_ID',
  templateId : 'YOUR_TEMPLATE_ID',
};
```

### Change theme colors
CSS custom properties live at the top of `<style>` under `[data-theme="dark"]` and `[data-theme="light"]` — edit `--blue`, `--teal`, `--indigo`, etc.

### Add / remove sections
Each section is wrapped in a clear `<!-- SECTION NAME -->` comment. Current order: Nav → Hero → About → Skills → Experience → Projects → Terminal → Services → Contact → Footer.

---

## 🔍 SEO Checklist

- [x] `<title>` and `<meta name="description">` set
- [x] OpenGraph `og:title` / `og:description` set
- [x] Semantic HTML5 (`<section>`, `<nav>`, `<footer>`)
- [ ] Add `<meta property="og:image">` with a screenshot of the site
- [ ] Add `<link rel="canonical" href="https://your-domain/">`
- [ ] Submit sitemap / URL to Google Search Console after deploy

---

## 🛠️ Tech Stack Used

| Technology | Purpose |
|---|---|
| HTML5 | Semantic structure |
| CSS3 (custom, no framework) | Theming, layout, animations, glassmorphism |
| Vanilla JavaScript | Terminal, theme toggle, nav, counters, radar SVG, resume download |
| Font Awesome 6.5 | Icons (via CDN) |
| Google Fonts | Instrument Serif · DM Sans · JetBrains Mono |
| EmailJS | Contact form delivery (no backend) |

---

## 📄 License

Personal portfolio — all rights reserved by **Rakesh Roy**.

---

*Built with precision. Powered by Python & Django.* 🐍
