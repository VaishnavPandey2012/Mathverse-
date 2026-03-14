# 🚀 Mathverse: The Fractal Explorer

A single-file, browser-based math adventure game for kids and students. Travel across five alien planets, each themed around a different math topic, solving puzzles to level up and earn stars.

---

## ✨ Features

- **Five planets** covering Ratios, Prime Numbers, Area, Fractions, and Algebra
- **3D WebGL backgrounds** powered by Three.js — rotating planets, nebulae, particle effects
- **Streak system** — chain correct answers for score multipliers (up to 2×)
- **Hint system** — reveal a hint at a 25% score penalty
- **Star ratings** — earn 1–3 stars per level based on attempts
- **Progress saved** — scores and stars persist across sessions via localStorage
- **Keyboard friendly** — press Enter to submit answers
- **Responsive** — works on desktop and mobile

---

## 🪐 The Planets

| Planet | Subject | Levels | Puzzle Type |
|---|---|---|---|
| Aquaria | Ratios | 16 | Balance a chemical equation |
| Primoria | Prime Numbers | 16 | Find the next prime |
| Geometria | Area | 16 | Calculate rectangle or triangle area |
| Fractionis | Fractions | 16 | Tap the largest fraction |
| Infigeon | Algebra | ∞ | Solve for x |

---

## 🚀 Getting Started

No build step, no dependencies to install. Just open the file.

```bash
# Clone or download the project, then:
open index.html
```

Or drag `index.html` into any modern browser.

**Requirements:** A browser with WebGL support (Chrome, Firefox, Safari, Edge — all current versions work).

---

## 📁 Project Structure

```
Mathverse/
└── index.html   # The entire game — HTML, CSS, and JS in one file
```

All dependencies are loaded from CDN at runtime:

- [Three.js r128](https://threejs.org/) — 3D rendering & post-processing bloom
- [Tailwind CSS](https://tailwindcss.com/) — utility styling
- [Google Fonts](https://fonts.google.com/) — Orbitron + Rajdhani typefaces

---

## 🎮 How to Play

1. Open `index.html` in your browser
2. The **Starmap** shows all five planets and their level grids
3. Click any unlocked level node to start a puzzle
4. Type your answer into the input field (or tap a fraction card) and press **Submit** or **Enter**
5. Earn stars: 3 stars for first-try, 2 for second, 1 for any further attempt
6. Use the 💡 **Hint** button if you're stuck — it costs 25% of the level's base score
7. Chain correct answers to build a 🔥 **streak** for bonus multipliers
8. Complete all levels on a planet to fully explore it — Infigeon never ends!

---

## 🏆 Scoring

| Attempt | Base Score |
|---|---|
| 1st try | 100 pts |
| 2nd try | 75 pts |
| 3rd try | 50 pts |
| 4th+ try | 25 pts |

**Modifiers applied on top:**

- Hint used → ×0.75
- 2× streak → ×1.2
- 3–4× streak → ×1.5
- 5× streak → ×2.0

---

## 🛠️ Customisation

Everything lives in `index.html`. The planets array near the top of the `<script>` block is the easiest place to make changes:

```js
const planets = [
  {
    name: 'Planet Aquaria',
    subject: 'Ratios',
    bgColor: '#3b82f6',
    maxLevels: 16,
    description: lvl => `...`,
    hint:        lvl => `...`,
    setupPuzzle: lvl => `...`,   // returns HTML string
    checkAnswer: lvl => true/false,
  },
  // ...
];
```

To add a new planet, push a new object into the array following the same shape.

---

## 📦 Dependencies (CDN)

| Library | Version | Purpose |
|---|---|---|
| Three.js | 0.128.0 | 3D scene, bloom post-processing |
| es-module-shims | 1.6.3 | Import map support in older browsers |
| Tailwind CSS | latest | Utility-first CSS |
| Google Fonts | — | Orbitron, Rajdhani |

No npm, no bundler, no build pipeline required.

---

## 📄 License

MIT — do whatever you like with it.
