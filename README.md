# Cutout Studio

A free background remover that runs entirely in your browser. It's a single `index.html` file: images never leave your device, and there are no accounts, watermarks or limits.

## Use it

- **Easiest:** download `index.html` and double-click it. It opens in Chrome, Edge, Firefox or Safari.
- **Best for daily use:** host it, for example with GitHub Pages (Settings → Pages → deploy from the `main` branch). When the page is hosted, the browser keeps the AI model in its cache after the first download. When you open the file from disk, the browser can't cache it, so the model downloads again each time you open the page.

The first time you process an image, the page downloads the AI model: about 176 MB at Full precision, or about 44 MB in Compact mode.

## Features

- **Input:** JPEG, PNG, WebP (plus AVIF, BMP and GIF). Add images by drag & drop, Ctrl+V paste or the file picker. You can add many images at once.
- **Output:** transparent PNG or WebP, or JPG on a solid color. You can download images one at a time, as a ZIP, or copy to the clipboard. The output keeps the original resolution, with an optional crop to the subject.
- **AI models:** BRIA RMBG‑1.4 (default), IS‑Net and MODNet (portraits). The page uses WebGPU when your browser supports it and falls back to the CPU otherwise. If a model host is unreachable, it switches to IS‑Net from a mirror.
- **Edge quality:**
  - full‑resolution edge refinement (a color guided filter) for hair and fur
  - color decontamination (Blur‑Fusion), which removes background color bleeding into soft edges
  - removal of stray specks
- **Edge controls:** shrink/grow, feather and hardness sliders, with *Apply to all images*.
- **Touch up:** Erase and Restore brushes with adjustable size and softness, undo/redo, zoom and pan.
- **Views:** Result, before/after Compare slider, Original, and the alpha Mask.
- **Backgrounds:** transparent, any color, a blurred version of the original (portrait mode), or your own image.

## Keyboard shortcuts

| Keys | Action |
| --- | --- |
| Ctrl+V / Ctrl+O | Paste / open images |
| Ctrl+S / Ctrl+Shift+C | Download / copy result |
| V · E · R | Move · Erase brush · Restore brush |
| [ · ] | Brush size |
| Ctrl+Z / Ctrl+Shift+Z | Undo / redo |
| Space + drag, mouse wheel | Pan, zoom |
| 0 | Fit to screen |
| 1–4 | Result · Compare · Original · Mask |
| ← → | Previous / next image |

## Model licenses

The AI models are downloaded at runtime from Hugging Face or IMG.LY's CDN; none are included in this repository.

- **RMBG‑1.4** by BRIA AI: free for personal and non‑commercial use. Commercial use needs a license from BRIA.
- **IS‑Net**: the copy served by IMG.LY is published under AGPL‑3.0.
- **MODNet**: Apache‑2.0.

For commercial work, check the license of the model you use, or switch to MODNet under *AI & quality*.
