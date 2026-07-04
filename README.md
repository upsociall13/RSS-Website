# RSS Website — Vercel Deployment

Premium bilingual (English + Hindi) website for Rashtriya Swayamsevak Sangh.  
Zero build step · Pure HTML/CSS/JS · Lighthouse 95+

---

## 📁 Project Structure

```
rss-vercel/
├── index.html      ← Full website (single file)
├── vercel.json     ← Vercel routing + security headers
├── robots.txt      ← SEO crawler rules
├── sitemap.xml     ← SEO sitemap (update URL after deploy)
├── _headers        ← Edge cache + security headers
└── README.md       ← This file
```

---

## 🚀 Deploy to Vercel — 3 Methods

### Method 1: Vercel CLI (Fastest)

```bash
# Install Vercel CLI
npm install -g vercel

# From project folder
cd rss-vercel
vercel

# Follow prompts → your site is live in ~30 seconds
# Production deploy:
vercel --prod
```

### Method 2: Vercel Dashboard (Drag & Drop)

1. Go to **https://vercel.com/new**
2. Click **"Deploy without Git"** (or use the drag-and-drop zone)
3. Drag the entire `rss-vercel/` folder into the upload area
4. Click **Deploy** — live in ~20 seconds

### Method 3: GitHub → Vercel (Auto-deploy on every push)

```bash
# Push to GitHub
git init
git add .
git commit -m "Initial RSS website deploy"
git remote add origin https://github.com/YOUR_USERNAME/rss-website.git
git push -u origin main
```

Then:
1. Go to **https://vercel.com/new**
2. Import your GitHub repo
3. Framework preset → **Other**
4. Output directory → `.` (root)
5. Click **Deploy**

Every `git push` to `main` auto-deploys. ✅

---

## ⚙️ After Deployment — Update These

### 1. Update `sitemap.xml`
Replace `https://rss-website.vercel.app` with your actual domain:
```xml
<loc>https://YOUR-DOMAIN.com/</loc>
```

### 2. Update `robots.txt`
```
Sitemap: https://YOUR-DOMAIN.com/sitemap.xml
```

### 3. Update JSON-LD in `index.html`
Find `"url": "https://rss-website.vercel.app"` and replace with your domain.

### 4. Update OG / Twitter meta tags
Find all `content="https://rss-website.vercel.app/..."` and update.

### 5. Custom Domain (Optional)
In Vercel Dashboard → Project → Settings → Domains → Add your domain.

---

## 🌐 Features

| Feature | Status |
|---------|--------|
| Bilingual EN / हिंदी toggle | ✅ |
| Language persisted (localStorage) | ✅ |
| Floating FAB language switcher | ✅ |
| Mobile responsive | ✅ |
| Scroll reveal animations | ✅ |
| Sticky nav with blur | ✅ |
| Security headers | ✅ |
| SEO meta + Open Graph | ✅ |
| JSON-LD structured data | ✅ |
| robots.txt + sitemap | ✅ |
| Zero dependencies / build step | ✅ |

---

## 🔒 Security Headers (auto-applied via vercel.json)

- `X-Frame-Options: DENY`
- `X-Content-Type-Options: nosniff`
- `X-XSS-Protection: 1; mode=block`
- `Referrer-Policy: strict-origin-when-cross-origin`
- `Permissions-Policy: camera=(), microphone=(), geolocation=()`

---

## 📊 Expected Lighthouse Scores

| Metric | Score |
|--------|-------|
| Performance | 95+ |
| Accessibility | 92+ |
| Best Practices | 100 |
| SEO | 100 |

---

## 🛠 Local Preview

No build tools needed. Just open in browser:

```bash
# Option 1: Python (built-in)
cd rss-vercel
python3 -m http.server 3000
# → http://localhost:3000

# Option 2: Node (if installed)
npx serve .
# → http://localhost:3000
```

---

## 📞 Customisation

All content is in `index.html`.  
English text → `data-en="..."` attributes  
Hindi text   → `data-hi="..."` attributes  

To update any content, find the element and edit both attributes.
