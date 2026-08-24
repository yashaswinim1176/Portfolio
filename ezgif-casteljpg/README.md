# 🏰 Castle Scroll Animation

A cinematic **scroll-driven frame animation** — a majestic Gothic castle on a rocky island at sunset, brought to life by scrolling. Built with pure HTML5 Canvas and vanilla JavaScript. No frameworks, no dependencies.

**🔗 Live Demo → [https://yashaswinim1176portfolio.netlify.app](https://yashaswinim1176portfolio.netlify.app)**

---

## ✨ Features

| Feature | Detail |
|---|---|
| **150-frame animation** | High-quality JPEG frames exported from source footage |
| **Scroll-driven playback** | Scroll position maps directly to frame index |
| **Smooth lerp interpolation** | `LERP = 0.09` — buttery-smooth frame transitions every RAF tick |
| **HiDPI / Retina support** | Canvas scaled by `devicePixelRatio` for crisp rendering on all screens |
| **Cover-fit framing** | Images always fill the full viewport, no letterboxing |
| **Preload with progress bar** | Minimal loading bar shows % progress; fades out when ready |
| **Zero dependencies** | Pure HTML + CSS + Vanilla JS — no libraries needed |

---

## 📁 Project Structure

```
Portfolio/
├── index.html              # Main page — canvas + scroll animation logic
├── netlify.toml            # Netlify deployment config (cache headers)
├── server.ps1              # Local dev server (PowerShell / Windows)
├── ezgif-frame-001.jpg     # Animation frames 001–150
├── ezgif-frame-002.jpg
├── ...
└── ezgif-frame-150.jpg
```

---

## 🚀 Running Locally

### Option 1 — PowerShell Server (Windows)

```powershell
# From the project folder
powershell -ExecutionPolicy Bypass -File server.ps1
```

Then open → **http://localhost:8080**

### Option 2 — VS Code Live Server

Install the [Live Server extension](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer), right-click `index.html` → **Open with Live Server**.

### Option 3 — Any HTTP server

```bash
# Python
python -m http.server 8080

# Node
npx serve .
```

> ⚠️ The animation **must** be served over HTTP — opening `index.html` directly as a `file://` URL will block image loading due to browser CORS restrictions.

---

## 🌐 Deployment (Netlify)

This repo is connected to Netlify for automatic deployments.

1. Every push to `main` triggers a new Netlify build
2. The `netlify.toml` sets aggressive cache headers on `.jpg` frames (`immutable, max-age=31536000`) so repeat visitors load instantly
3. HTML files are set to `no-cache` so updates are always reflected immediately

---

## ⚙️ Customisation

Open `index.html` and tweak these constants at the top of the `<script>` block:

```js
const TOTAL = 150;    // number of frames
const LERP  = 0.09;   // smoothing factor — lower = silkier, higher = snappier
```

| `LERP` value | Feel |
|---|---|
| `0.05` | Very dreamy / cinematic |
| `0.09` | Default — smooth & responsive |
| `0.15` | Snappier / more direct |

---

## 🛠️ Tech Stack

- **HTML5 Canvas API** — frame rendering
- **`requestAnimationFrame`** — 60 fps animation loop
- **Linear interpolation (lerp)** — smooth frame transitions
- **`window.devicePixelRatio`** — HiDPI rendering
- **Netlify** — hosting & CDN

---

## 📄 License

MIT — free to use, modify, and distribute.
