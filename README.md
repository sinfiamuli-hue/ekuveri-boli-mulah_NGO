# Ekuveri Boli Mulah — Website

**Live site:** https://ebm.sinfia.net

Bilingual (English / ދިވެހި) cultural performance website for Ekuveri Boli Mulah, M. Mulak, Maldives.  
Hosted on **GitHub Pages** · Custom domain via **Cloudflare** (`ebm.sinfia.net`)

---

## Repository Structure

```
ekuveri-boli-mulah/
├── .github/
│   └── workflows/
│       └── deploy.yml        # Auto-deploy to GitHub Pages on push to main
├── assets/
│   ├── fonts/
│   │   ├── MvDheliFihi.woff2       # Headings (H1/H2/H3) — Dhivehi
│   │   ├── MvDheliFihi.ttf
│   │   ├── MvIzyanSuruhee.woff2    # Subheadings / labels — Dhivehi
│   │   ├── MvIzyanSuruhee.ttf
│   │   ├── MvAlram.woff2           # Body / nav / buttons — Dhivehi
│   │   └── MvAlram.ttf
│   ├── hero.jpg                    # Hero background photo
│   └── logo.png                    # Group logo
├── index.html                      # Main bilingual page
├── style.css                       # All styles + RTL + font declarations
├── script.js                       # Scroll reveal, nav, language switcher
├── CNAME                           # Custom domain → ebm.sinfia.net
└── README.md
```

---

## One-Time Setup

### 1 — Create the GitHub repository

1. Go to [github.com/new](https://github.com/new)
2. Name it `ekuveri-boli-mulah` (or any name you prefer)
3. Set it to **Public** *(required for free GitHub Pages)*
4. Do **not** initialise with README (you'll push this folder)
5. Click **Create repository**

### 2 — Push these files

```bash
# From inside this folder on your computer:
git init
git add .
git commit -m "Initial deploy — bilingual EBM website"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/ekuveri-boli-mulah.git
git push -u origin main
```

### 3 — Enable GitHub Pages

1. Go to your repo → **Settings** → **Pages**
2. Under *Source*, select **GitHub Actions**
3. The workflow in `.github/workflows/deploy.yml` will auto-run
4. Under *Custom domain*, type `ebm.sinfia.net` and click **Save**
5. Tick **Enforce HTTPS** once the DNS check passes ✅

---

### 4 — Configure Cloudflare DNS (`sinfia.net`)

Log into [Cloudflare Dashboard](https://dash.cloudflare.com) → `sinfia.net` → **DNS** → **Add record**:

| Type  | Name | Content                    | Proxy status | TTL  |
|-------|------|----------------------------|--------------|------|
| CNAME | ebm  | YOUR_USERNAME.github.io    | **DNS only** (grey cloud ☁️) | Auto |

> ⚠️ **Important:** Set proxy to **DNS only (grey cloud)** — NOT proxied (orange).  
> GitHub Pages needs to verify ownership via DNS. Proxying breaks the HTTPS certificate.

After saving, wait **5–10 minutes** for DNS to propagate, then check GitHub Pages settings — it should show a green ✅ and enable HTTPS automatically.

---

## Making Updates

Edit any file locally, then:

```bash
git add .
git commit -m "describe your change"
git push
```

GitHub Actions will automatically redeploy the site within ~30 seconds.

---

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Hosting | GitHub Pages (free) |
| CDN / DNS | Cloudflare |
| Languages | HTML · CSS · Vanilla JS |
| Fonts (EN) | Cormorant Garamond · Jost (Google Fonts) |
| Fonts (DV) | Mv Dheli Fihi · Mv Izyan Suruhee · Mv Alram (local) |
| i18n | Custom `data-lang` attribute system + `localStorage` |
| RTL | `html[lang="dv"] { direction: rtl }` |

---

## Contact

📧 ekuveribolimulah@gmail.com  
💬 WhatsApp: +960 911 4145 · +960 973 2929
