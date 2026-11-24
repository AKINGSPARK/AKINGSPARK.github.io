# Pick-Up Sticks Scorer

A modern, offline-capable score tracker for the classic game **Pick-Up Sticks** with a built-in combo system.

![Pick-Up Sticks Scorer](icon-512.svg)

## Live Demo

**[Play Now →](https://akingspark.github.io/)**

## Features

- **Real-time scoring** — Tap colored stick buttons to add points
- **Combo system** — Pick Red → Blue → Green in order for a **2× multiplier** (34 pts total)
- **Visual stick pool** — See remaining sticks at a glance with animated depletion
- **Player rankings** — Gold/silver/bronze badges for top 3
- **Undo** — Revert the last move (per-player history)
- **New Bundle** — Reset sticks for a new round, keep scores
- **Restart Game** — Full reset with confirmation
- **Dark/Light mode** — System preference + manual toggle (persisted)
- **PWA** — Installable, works offline after first visit
- **Keyboard shortcuts** — Full game control without mouse
- **Accessible** — ARIA labels, focus states, reduced motion support

## How to Play

| Stick | Value | Count | Max Points |
|-------|-------|-------|------------|
| Red | 10 | 7 | 70 |
| Blue | 5 | 7 | 35 |
| Yellow | 1 | 7 | 7 |
| Green | 2 | 8 | 16 |
| Black | 25 | 1 | 25 |

**Combo:** Pick **Red → Blue → Green** in exact order to score **double** on the Green (2 × 2 = 4 bonus + 17 base = 34 total for the sequence). Any other color or wrong order breaks the chain.

## Keyboard Shortcuts

| Key | Action |
|-----|--------|
| `A` | Add Player |
| `U` | Undo last move |
| `N` | New Bundle (reset sticks) |
| `R` | Restart Game (full reset) |
| `?` | Open How to Play |
| `Esc` | Close modal |

## Running Locally

```bash
# Option 1: Open directly (no server needed)
open index.html

# Option 2: Serve locally (required for PWA/service worker)
python3 -m http.server 8000
# Then open http://localhost:8000
```

## Deploying

### Netlify (drag & drop)
1. Go to https://app.netlify.com/drop
2. Drag the project folder
3. Get a permanent `*.netlify.app` URL

### Vercel
```bash
npx vercel --prod
```

### GitHub Pages
1. Push to a GitHub repo
2. Settings → Pages → Deploy from branch
3. Select `main` / `root`

### Surge.sh
```bash
npx surge . your-project.surge.sh
```

## Project Structure

```
├── index.html          # Main app (HTML + CSS + JS)
├── manifest.json       # PWA manifest
├── sw.js               # Service worker (offline caching)
├── icon-192.svg        # App icon (192×192)
├── icon-512.svg        # App icon (512×512)
└── README.md           # This file
```

## Data Persistence

All game state is stored in `localStorage`:
- Players & scores
- Remaining stick counts
- Undo history
- Rounds played & combos hit
- Theme preference

Clearing browser data resets the game. Use **Restart Game** button for a clean slate.

## Browser Support

- Chrome 80+
- Firefox 75+
- Safari 14+
- Edge 80+

## License

MIT — feel free to use, modify, and distribute.
