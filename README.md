# 🚀 Rakesh Roy — Portfolio Website

**Premium Python Backend Engineer Portfolio**  
Futuristic, interactive, single-file HTML/CSS/JS portfolio.

---

## 📁 File Structure

```
portfolio/
├── index.html          ← Complete portfolio (all-in-one)
└── README.md           ← This file
```

> Everything is self-contained in `index.html` — no build step needed.

---

## ✨ Features

| Feature | Details |
|---|---|
| 🖥️ **Boot Loader** | Animated terminal boot sequence on first load |
| ⌨️ **Typed.js effect** | Rotating role titles with cursor animation |
| 🎨 **Custom cursor** | Dot + ring cursor with hover expansion |
| 🌌 **Canvas background** | Animated particle network with grid overlay |
| 🃏 **VanillaTilt** | 3D hover tilt on project & service cards |
| 🖱️ **Glow trail** | Mouse-follow glow dot trail |
| 📜 **AOS animations** | Scroll-triggered fade/slide-in on all sections |
| 💻 **Live Terminal** | Interactive fake terminal with 7+ commands |
| 📊 **Animated counters** | Stats count up when scrolled into view |
| 📱 **Fully responsive** | Mobile-first, Bootstrap 5 layout |
| 🔝 **Scroll to top** | Fixed button appears after 400px scroll |
| 🎯 **Active nav** | Highlights current section in navbar |

---

## 🌐 Deployment Options

### Option 1 — GitHub Pages (Free, Recommended)

```bash
# 1. Create a new GitHub repo named: rakeshroy.github.io
#    (or any repo name — use Settings > Pages to deploy)

# 2. Clone and add file
git init my-portfolio
cd my-portfolio
cp /path/to/index.html .
cp /path/to/README.md .

# 3. Push to GitHub
git add .
git commit -m "🚀 Initial portfolio deploy"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
git push -u origin main

# 4. Enable GitHub Pages
#    Go to: Repo → Settings → Pages → Source: Deploy from branch → main / root
#    Your site will be live at: https://YOUR_USERNAME.github.io/YOUR_REPO/
```

---

### Option 2 — Netlify (Drag & Drop — Fastest)

1. Go to [https://app.netlify.com/drop](https://app.netlify.com/drop)
2. Drag and drop the **portfolio folder** (containing `index.html`)
3. Your site is instantly live with a `*.netlify.app` URL
4. Optionally connect a custom domain

---

### Option 3 — Vercel

```bash
npm install -g vercel
cd portfolio/
vercel
# Follow prompts → site is live in 30 seconds
```

---

### Option 4 — Traditional Hosting (cPanel / VPS)

```bash
# Upload index.html to your public_html or www folder via FTP/SFTP
# No server-side setup needed — pure static HTML
```

---

## ⚙️ Customization Guide

### Update Contact Info
Search for these in `index.html` and replace:
```
rakeshroy.dev@gmail.com   → your email
+91-8919736316            → your phone
rakeshroy-dev             → your LinkedIn handle
918919736316              → your WhatsApp number (no +)
```

### Change Colors
Edit CSS variables at the top of `<style>`:
```css
--py-blue:    #38BDF8;   /* Primary accent */
--py-violet:  #8B5CF6;   /* Secondary accent */
--py-cyan:    #22D3EE;   /* Highlight */
--py-emerald: #10B981;   /* Success / live indicator */
```

### Add/Remove Sections
Each section has a clear `<!-- ===== SECTION NAME ===== -->` comment.
Sections are ordered: Hero → About → Skills → Experience → Projects → Terminal → Services → Stats → Contact → Footer.

### Add a Resume PDF Download
1. Place your resume as `resume.pdf` in the same folder
2. Find the **Hire Me** button in the hero and add a download link:
```html
<a href="resume.pdf" download class="btn-outline-glow">
  <i class="fa-solid fa-download"></i> Download CV
</a>
```

---

## 📱 Mobile Performance Tips

- Particle count auto-scales by screen size (`Math.min(120, W*H/12000)`)
- Tech badge floaters are hidden below 992px
- VanillaTilt 3D effect gracefully degrades on touch devices
- Canvas background is `position:fixed` — GPU composited
- AOS animations use `will-change: transform, opacity`

---

## 🔍 SEO Checklist

- [x] `<title>` tag set
- [x] `<meta name="description">` set
- [x] `<meta name="keywords">` set
- [x] OpenGraph `og:title` and `og:description` set
- [x] Semantic HTML5 (`<section>`, `<nav>`, `<footer>`)
- [ ] Add `<meta property="og:image">` with a screenshot of your portfolio
- [ ] Add `<link rel="canonical" href="https://yourdomain.com">`
- [ ] Submit to Google Search Console after deploy

---

## 🛠️ Tech Stack Used

| Technology | Purpose |
|---|---|
| HTML5 | Semantic structure |
| CSS3 | All styling, animations, glassmorphism |
| Bootstrap 5.3 | Responsive grid + navbar |
| JavaScript (Vanilla) | All interactivity |
| AOS 2.3 | Scroll-triggered animations |
| VanillaTilt 1.8 | 3D card hover effects |
| Font Awesome 6.5 | Icons |
| Google Fonts | Sora + JetBrains Mono + Outfit |
| HTML Canvas API | Particle network background |

---

## 📄 License

Personal portfolio — all rights reserved by **Rakesh Roy**.

---

*Built with precision. Powered by Python.* 🐍
