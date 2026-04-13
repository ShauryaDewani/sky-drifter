# Sky Drifter 🎈

**CMPT 461 — Mobile VR · Trinity Western University**

A first-person hot-air balloon VR game built with [A-Frame 1.7.1](https://aframe.io).
Your balloon drifts forward automatically — tilt your head to steer, dodge clouds,
collect orbs, and fly through rings across two hand-crafted levels.

---

## Play Online

> 🔗 `https://shauryadewani.github.io/sky-drifter/`

Open in Chrome on your phone, tap the VR goggles icon, drop into a Cardboard headset.

---

## Levels

| # | Name | Sky | Goal |
|---|------|-----|------|
| 1 | Sunny Meadows | Bright day | Clear 65 % of gold rings |
| 2 | Sunset Canyon | Warm dusk | Fly the full canyon depth |

---

## Controls

| Action | Mobile VR (Cardboard) | Desktop |
|--------|----------------------|---------|
| Steer left / right | Tilt head left / right | Drag mouse |
| Ascend | Look up | Drag mouse up |
| Descend | Look down | Drag mouse down |
| Select menu button | Gaze + hold 1.5 s | Click |

---

## Scoring

- 🏅 **Ring** — +10 pts (fly through)
- ✨ **Orb** — +5 pts (collect)
- ☁️ **Cloud** — −15 pts (collision penalty, 2 s cooldown)

High score saved in `localStorage`.

---

## Project Structure

```
sky-drifter/
├── index.html               # Full game (single-file A-Frame)
├── manual.html              # Player manual & setup guide
├── README.md                # This file
└── assets/
    ├── textures/
    │   └── ASSET_LIST.txt   # What textures to drop in + sources
    └── audio/
        └── ASSET_LIST.txt   # What audio files to drop in + sources
```

---

## Running Locally

Browsers block local assets on `file://`. Use a local server:

```bash
# Python 3
python -m http.server 8080

# Node.js
npx serve .

# VS Code: right-click index.html → Open with Live Server
```

Then open `http://localhost:8080`.

---

## Deploying to GitHub Pages

```bash
# 1. Create a public GitHub repo named  sky-drifter
# 2. Push this folder to it
git init
git add .
git commit -m "Initial Sky Drifter commit"
git remote add origin https://github.com/shauryadewani/sky-drifter.git
git push -u origin main

# 3. In GitHub: Settings → Pages → Source: main / (root) → Save
# 4. Live in ~1 min at https://shauryadewani.github.io/sky-drifter/
```

---

## Adding Assets

All placeholder colors will work out of the box. To swap in real textures and audio:

1. Drop files into `assets/textures/` and `assets/audio/`.
2. See `ASSET_LIST.txt` in each folder for exact filenames and recommended free sources.
3. In `index.html`, uncomment the `<img>` tags inside `<a-assets>` and update
   the `material` attributes on each geometry element.

Recommended free CC0 sources: [Poly Haven](https://polyhaven.com/textures),
[ambientCG](https://ambientcg.com), [Kenney.nl](https://kenney.nl/assets),
[freesound.org](https://freesound.org).

---

## Features (Rubric Checklist)

- [x] Flash screen with name / student ID / course / institution
- [x] Setup screen — music mute toggle
- [x] Setup screen — sensitivity control (5 levels)
- [x] At least 2 distinct levels with different environments
- [x] Background music per level (mutable)
- [x] Sound effects (ring, orb, cloud, level-up)
- [x] Always-visible HUD (score + level name + personal best)
- [x] Head-tilt controls via device orientation / camera quaternion
- [x] Gaze-fuse cursor for menu buttons (1.5 s dwell)
- [x] Stereoscopic mobile VR (A-Frame WebXR / Cardboard)
- [x] Custom geometry objects — balloon, basket, rings, orbs, clouds, spires
- [x] Collision detection — ring pass-through, orb collect, cloud penalty
- [x] **Bonus** — Game complete screen with high score celebration on Level 2
- [x] **Bonus** — High score persisted in `localStorage`

---

## Dependencies (CDN — no install required)

| Library | Version | Purpose |
|---------|---------|---------|
| [A-Frame](https://aframe.io) | 1.7.1 | WebVR framework |

---

## License

MIT — see course submission guidelines for attribution requirements.

---

*Built for CMPT 461 · Due April 11, 2026*
