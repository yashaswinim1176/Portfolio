# 🏰 Castle Scroll Animation — Portfolio

A cinematic **scroll-driven frame animation** built with pure HTML5 Canvas and vanilla JavaScript. A majestic Gothic castle on a rocky ocean island at sunset, brought to life by scrolling. No frameworks. No dependencies.

**🔗 Live Demo → [https://yashaswinim1176portfolio.netlify.app](https://yashaswinim1176portfolio.netlify.app)**

---

## ✨ Features

| Feature | Detail |
|---|---|
| **150-frame animation** | High-quality JPEG frames from source footage |
| **Scroll-driven playback** | Scroll position maps 1:1 to frame index |
| **Smooth lerp interpolation** | Buttery-smooth frame transitions at every RAF tick |
| **HiDPI / Retina support** | Canvas scaled by `devicePixelRatio` — crisp on all screens |
| **Cover-fit framing** | Image always fills the full viewport — no letterboxing |
| **Preloader with progress** | Minimal white bar shows % loaded; fades out when ready |
| **Zero dependencies** | Pure HTML + CSS + Vanilla JS |

---

## 📁 Project Structure

```
Portfolio/
├── index.html                       # Personal portfolio page
├── netlify.toml                     # Netlify deploy config
├── server.ps1                       # Local dev server (Windows / PowerShell)
├── README.md                        # This file
└── ezgif-casteljpg/                 # Castle scroll animation
    ├── index.html                   # Animation page (canvas + scroll logic)
    ├── ezgif-frame-001.jpg          # Animation frames 001 – 150
    ├── ...
    └── ezgif-frame-150.jpg
```

---

## 🚀 Running Locally

### PowerShell Server (Windows)

```powershell
# From the project root
powershell -ExecutionPolicy Bypass -File server.ps1
```

Then open → **http://localhost:8080**

### VS Code Live Server

Install [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer), right-click `ezgif-casteljpg/index.html` → **Open with Live Server**.

### Python / Node

```bash
# Python 3
python -m http.server 8080

# Node
npx serve .
```

> ⚠️ Must be served over **HTTP** — `file://` URLs will block images due to CORS.

---

## 🌐 Netlify Deployment

This repo auto-deploys via Netlify on every push to `main`.

- **Publish directory:** `ezgif-casteljpg/`
- **JPEG frames** → `Cache-Control: immutable, max-age=31536000` (1 year)
- **HTML files** → `Cache-Control: no-cache` (always fresh on deploy)

---

## ⚙️ Customisation

Inside `ezgif-casteljpg/index.html`:

```js
const TOTAL = 150;   // number of frames
const LERP  = 0.09;  // smoothing — lower = silkier, higher = snappier
```

| `LERP` | Feel |
|---|---|
| `0.05` | Dreamy / cinematic |
| `0.09` | ✅ Default — smooth & responsive |
| `0.15` | Snappier / more direct |

---

## 🛠️ Tech Stack

- **HTML5 Canvas API** — frame rendering
- **`requestAnimationFrame`** — 60 fps animation loop
- **Linear interpolation (lerp)** — smooth transitions
- **`window.devicePixelRatio`** — HiDPI support
- **Netlify** — hosting & global CDN

---

## 📄 License

MIT — free to use, modify, and distribute.
