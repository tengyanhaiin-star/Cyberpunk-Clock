# NEON DECAY · CHRONOS UNIT

A cyberpunk analog clock built with pure HTML5 Canvas. No frameworks, no dependencies — just a single self-contained HTML file.

---

## Features

- **Real-time analog clock** with hour, minute, and second hands
- **Three animated progress arcs** — each hand has a corresponding neon arc that sweeps a half-circle and resets, with different anchor points per hand
- **Multilayer neon glow** on every element — rings, tick marks, hands, and text
- **12-color rainbow arc ring** cycling through cyan, blue, violet, magenta, pink, orange, yellow, and green
- **Digital time display** (HH:MM:SS) overlaid on the clock face
- **Automatic timezone detection** — reads your system timezone and displays it live
- **Responsive layout** — scales to any square viewport
- **iOS / iPhone compatible** — optimized for Safari with reduced blur passes, capped pixel ratio, safe area insets, and orientation change handling
- **Performance optimized** — static clock face is pre-rendered to an offscreen canvas and composited with a single `drawImage()` call per frame; only hands and arcs are redrawn each frame

## Color Language

| Element | Color |
|---------|-------|
| Hour hand & arc | Green |
| Minute hand & arc | Cyan |
| Second hand & arc | Magenta |
| Hour numerals | Green (Rationale font) |
| Digital time | Orange |
| NEON DECAY title | Violet |
| CHRONOS UNIT subtitle | Yellow |
| System info line | Blue |

## Usage

No installation or build step required.

**Option 1 — Open locally:**
Download `index.html` and open it in any modern browser.

**Option 2 — GitHub Pages:**
Visit the live demo at:
```
https://<your-username>.github.io/<your-repo-name>/
```

## Browser Compatibility

| Browser | Status |
|---------|--------|
| Chrome / Edge | ✅ Full support |
| Firefox | ✅ Full support |
| Safari (macOS) | ✅ Full support |
| Safari (iOS) | ✅ Optimized |

## Fonts

Loaded from Google Fonts CDN at runtime:

- **[Rationale](https://fonts.google.com/specimen/Rationale)** — hour numerals
- **[Tektur](https://fonts.google.com/specimen/Tektur)** — clock title
- **[Share Tech Mono](https://fonts.google.com/specimen/Share+Tech+Mono)** — digital readout and system info

An internet connection is required to load the correct fonts. The clock remains functional with system fallback fonts if offline.

## Technical Notes

- Built with **HTML5 Canvas 2D API** and `requestAnimationFrame`
- All sizing is expressed relative to the clock radius `R`, making it fully resolution-independent
- High-DPI / Retina rendering via `devicePixelRatio` scaling (capped at 2× on iOS)
- Static layer (background, rings, tick marks, numerals, decorative arcs, vignette) is cached to an offscreen canvas and rebuilt once per second after the first second of load
- During the first second after page load, the static layer is rebuilt every frame to ensure fonts render correctly before caching begins
- Smooth hand motion uses millisecond precision (`Date.getMilliseconds()`)

## License

MIT License — free to use, modify, and distribute.
