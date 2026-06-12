# Gradient Columns — Animated Background

An interactive full-screen animated background made of vertical gradient columns that scroll seamlessly in a wave pattern, with a live control panel for switching color themes, randomizing palettes, and adjusting animation speed.

---

## Overview

This project renders **16 vertical columns**, each filled with a looping linear gradient. Columns scroll vertically in alternating directions (odd columns down, even columns up) with staggered animation delays, producing a smooth, hypnotic wave effect across the entire viewport.

A floating glass-style control panel lets the user:

- Switch between **60+ built-in color themes** (Deep Space, Cyberpunk, Aurora, Lava, Galaxy, Toxic, Neon City, Matrix, Oil Slick, and many more)
- Generate a **random color palette** with one click
- Adjust the **animation speed** via a slider (from slow ambient drift to fast strobe-like motion)
- **Hide/show** the control panel (button or `Ctrl+X` / `Cmd+X` shortcut)

A subtle film-grain overlay (SVG noise, blended via `mix-blend-mode: overlay`) adds texture and depth to the gradients.

---

## Features

- **Pure HTML/CSS/JS** — single file, no build tools, no dependencies, no frameworks
- **CSS custom properties** drive all colors and animation speed, enabling instant theme/speed updates without restarting animations from scratch
- **Seamless infinite scroll** — each column contains two stacked gradient rectangles (200% height) that loop perfectly via `translateY`
- **60+ curated themes** covering neon, pastel, monochrome, nature, and sci-fi aesthetics
- **Randomize button** generates a fresh palette from a curated color pool with automatically darkened base tones
- **Liquid glass UI** — translucent panel with backdrop blur, soft borders, and subtle glow on the active theme
- **Keyboard shortcut** (`Ctrl+X` / `Cmd+X`) to toggle the UI for a clean, distraction-free view
- **Responsive** — scales to any viewport size (`100vw` / `100vh`)
- Uses **Syne** and **DM Mono** Google Fonts for a modern, technical aesthetic

---

## File Structure

```
gradient-columns.html   ← everything (markup, styles, and script) in one file
```

Because the entire project is self-contained in a single HTML file, it can be opened directly in any modern browser or hosted anywhere static files are served (GitHub Pages, Netlify, Vercel, a local file system, etc.).

---

## Usage

1. Download `gradient-columns.html`.
2. Open it in any modern browser (Chrome, Firefox, Edge, Safari).
3. Use the bottom control panel to:
   - Click a **theme button** to apply a preset color palette
   - Click **✦ Randomize** for a random palette
   - Drag the **Speed** slider to control animation duration (range: 1–10, mapped to 12s → 1.2s per cycle)
   - Click **HIDE UI** (or press `Ctrl+X` / `Cmd+X`) to hide the panel

No installation, build step, or internet connection is required after the page has loaded (aside from the Google Fonts import, which gracefully falls back to system fonts if unavailable).

---

## Customization

All visual parameters are controlled through CSS custom properties defined on `:root`:

| Variable | Purpose |
|---|---|
| `--col-1` … `--col-8` | Base (dark) column background colors |
| `--accent-1` … `--accent-4` | Accent colors used in column gradients |
| `--speed` | Animation cycle duration (e.g. `4s`) |
| `--panel-bg`, `--panel-border`, `--btn-active` | Control panel styling |

To add a new theme, append an entry to the `THEMES` object in the `<script>` section with `bases` (8 colors) and `accents` (4 colors) arrays, then register its display name in `themeNames`.

To change the number of columns, update the `NUM_COLS` constant and add corresponding `nth-child` gradient and animation-delay rules in the CSS.

---

## Browser Compatibility

Built with standard, widely supported web APIs:

- CSS Custom Properties (CSS Variables)
- CSS `backdrop-filter` (for the glass panel effect — degrades gracefully without it)
- CSS Animations / Keyframes
- Vanilla JavaScript (ES6+) — `const`, arrow functions, template literals, `Array.from`

Recommended: latest versions of Chrome, Firefox, Safari, or Edge.

---

## Technologies Used

- HTML5
- CSS3 (Custom Properties, Flexbox, Keyframe Animations, `backdrop-filter`, `mix-blend-mode`)
- Vanilla JavaScript (no libraries or frameworks)
- Google Fonts: [Syne](https://fonts.google.com/specimen/Syne), [DM Mono](https://fonts.google.com/specimen/DM+Mono)

---

## License & Copyright

**All Rights Reserved.**

Copyright © 2026. This project and all of its source code, design, color themes, and visual assets are proprietary. No part of this project may be copied, modified, distributed, sublicensed, sold, or used — in whole or in part, for commercial or non-commercial purposes — without the prior written permission of the copyright holder.

Unauthorized use, reproduction, or distribution of this material, or any portion of it, is strictly prohibited and may result in legal action.

For licensing inquiries or permission requests, please contact the copyright holder directly.
