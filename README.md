# PRHS Walking Tour — Multi‑Stop WebAR

Single page, many sites: open `tour.html?site=pickwick` (or hodges, depot, library, pantry). Each stop loads its own overlay, avatar, and links from `config.json`.

## Deploy fast
- **Netlify Drop:** https://app.netlify.com/drop → drag folder → get https link
- Test links:
  - `…/tour.html?site=pickwick`
  - `…/tour.html?site=hodges`
  - `…/tour.html?site=depot`
  - `…/tour.html?site=library`
  - `…/tour.html?site=pantry`

## QRs
Print one QR per stop to its URL. Use error correction **H** and print the short URL under the code.

## Replace assets
Put real files in `assets/stops/<site>/` keeping the same filenames:
- `overlay.jpg` — Historic façade image (2000–3000px wide, <5 MB)
- `sponsor_avatar_alpha.mov` — HEVC with **alpha** (transparent) for Safari/iOS
- `sponsor_avatar_alpha.webm` — VP9 with **alpha** for Chrome/Edge/Android
- `sponsor_avatar.mp4` — Fallback MP4 (no alpha)
- `sponsor_logo.png` — Sponsor logo (transparent PNG recommended)
- `avatar_poster.png` — Poster frame shown before/if video plays

Edit `config.json` to set the **Donate** and **Sponsor About** links per stop.

## iPhone camera tips
Open in **Safari**, allow camera, and ensure the page is **https**. If “Camera unavailable,” close other camera apps or restart.

## Add more stops
1) Duplicate a stop folder under `assets/stops/NEWKEY`  
2) Add `"NEWKEY": { ... }` to `config.json`  
3) Print a QR for `…/tour.html?site=NEWKEY`
