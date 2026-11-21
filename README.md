# ❄️ Arctic Flight

> **🎮 Play:** **[Arctic_Flight](https://ajil07.github.io/arctic-flight/)**

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![Canvas API](https://img.shields.io/badge/Canvas_2D-16--Bit_Procedural-38BDF8?style=for-the-badge)
![JavaScript](https://img.shields.io/badge/Vanilla_JS-Zero_Dependencies-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Web Audio](https://img.shields.io/badge/Web_Audio-Retro_Synth-58B4A8?style=for-the-badge)
![License: MIT](https://img.shields.io/badge/License-MIT-69B882?style=for-the-badge)

**Arctic Flight** is a 16-bit retro-styled atmospheric arcade game built entirely in a **single, zero-dependency HTML5 file** (`index.html`). Guide a nimble **Shima Enaga** (Japanese snow fairy bird) across undulating winter forests, through dynamic day/night Aurora Borealis cycles, past sudden blizzards, and into stratified glacial ice caverns—all rendered 100% procedurally with HTML5 Canvas and synthesized Web Audio.

---

## 📸 Gameplay Preview

<!-- Uncomment once you upload a gameplay GIF or screenshot to assets/gameplay.gif -->
<!-- ![Arctic Flight Gameplay](assets/gameplay.gif) -->

*Play directly in any desktop or mobile browser at **[https://ajil07.github.io/arctic-flight/](https://ajil07.github.io/arctic-flight/)**—no installation or downloads required.*

---

## ✨ The Result: Key Features

### 🐦 Nimble Player Character (The Shima Enaga)
* Procedurally drawn pure-white cotton-ball silhouette with glossy bead eyes, dark triangular beak, charcoal-tipped animated wings, and a slender tail.
* Compact, agile hitbox (`radius: 10`) with velocity-driven pitch tilt and trailing pixel-snow feather puffs on every flap.

### 🌲 Dynamic Biomes & 2.5D Cave Transitions
* **Outdoor Snowy Forest:** Features a **4-layer parallax pine forest** backed by angular polygonal mountains and rolling snow terrain. Obstacles spawn as **Chrome Dino-style clusters of 2–4 snow-covered pine trees** of varied heights and widths planted directly onto the undulating ground.
* **Foreground Ice Cave Entrance:** Transitioning between biomes triggers an obstacle-free glide zone framed by a massive, non-collidable **2.5D polygonal ice-and-rock archway** that scrolls in front of the bird as you fly through it.
* **Indoor Stratified Glacial Cave:** Razor-sharp faceted ice stalactites and stalagmites set against layered rock/ice strata, procedural mineral grain, and **multi-depth glowing crystals** embedded across far walls, mid-ground crevices, and near rocky outcrops.

### 🌌 Smooth Day / Night Cycle & Bioluminescence
* Gradually interpolates desaturated atmospheric gradients, obstacle shading, and lighting over a continuous 76-second cycle.
* **Outdoor Night:** Reveals twinkling pixel stars, a pale moon, and flowing emerald-to-cyan **Aurora Borealis** curtains.
* **Indoor Night:** Darkens the cavern into deep charcoal-teal shadows illuminated by glowing azure crystal clusters and hanging **bioluminescent ceiling glowworms**.

### 🌨️ Random Weather Event: Snowstorm (20+ Points)
* Once you reach **20 points**, blizzards can randomly roll in during the outdoor phase.
* Introduces fast diagonal snow streaks, a dense whiteout mist overlay, and subtle wind-gust physics that challenge your flight rhythm until the skies clear.

### ⚡ Progressive Horizontal Speed Scaling
* Smoothly ramps up the challenge in late-game runs without altering core jump gravity:

| Score Range | Speed Multiplier | Pacing Tier |
| :--- | :---: | :--- |
| `0 – 19` | `1.0x` | Classic Arctic Cruise |
| `20 – 24` | `1.1x` | Blizzard Threshold |
| `25 – 29` | `1.2x` | Brisk Gusts |
| `30 – 64` | `+0.1x` / 5 pts | Escalating Arcade Rush |
| `65+` | `2.0x` (Max Cap) | Peak Velocity |

### 🕹️ 16-Bit Retro Arcade UI & Procedural Audio
* Classic SNES/arcade cabinet bezel with an integrated top HUD (`SCORE`, live biome indicator, `BEST`, and 4 milestone stars unlocked at `5`, `15`, `30`, and `50` points).
* Crisp `PRESS START`, `PAUSED`, and `GAME OVER (PLAY AGAIN? YES / NO)` screens with stepped pixel drop-shadows.
* Synthesized Web Audio retro-synth flap chirp and collision crunch (with individual score chimes intentionally omitted for a cleaner atmosphere).

---

## 🎮 Controls

| Input | Action |
| :--- | :--- |
| `Space` / `↑` / `W` | Flap / Start / Quick Restart |
| `Left Click` / `Tap` | Flap / Start (Desktop & Mobile) |
| `P` / `Esc` | Pause / Resume |
| `M` | Toggle Retro Synth SFX |
| `R` | Instant Reset |

---

## 🛠️ Development Process & Evolution

Arctic Flight was built through an iterative design and engineering workflow—evolving from a classic arcade prototype into a cohesive, original atmospheric experience:

1. **Stage 1 — Core Arcade Engine:**
   Established a delta-time normalized (`60 FPS` baseline) HTML5 Canvas loop, responsive HiDPI (`devicePixelRatio`) scaling, velocity-based bird rotation, Web Audio synthesis, and persistent `localStorage` high scores.
2. **Stage 2 — Procedural Theme Exploration:**
   Tested 100% asset-free procedural rendering by replacing standard pipes and skies with custom organic geometry and particle systems (initially prototyping an underwater reef with coral pillars and rising bubbles) before pivoting to an original Arctic concept.
3. **Stage 3 — Arctic World-Building:**
   Designed the **Shima Enaga** protagonist, bottom-only snowy pine trees, a continuous Day/Night cycle with **Aurora Borealis**, an indoor glacial cavern with stalactites/stalagmites, nighttime glowing crystals and glowworms, and a 20+ point random snowstorm event.
4. **Stage 4 — 16-Bit Retro Overhaul & Layered Depth:**
   * Replaced translucent frosted-glass UI with a high-contrast **16-bit arcade cabinet frame** and integrated top HUD bezel.
   * Scaled down the bird and hitbox by ~28% for tighter, nimbler flight feel.
   * Shifted art direction from rounded shapes to **angular multi-polygon silhouettes** with desaturated, atmospheric color palettes.
   * Added a **4-layer parallax forest**, continuous **undulating terrain** (`getGroundY`), **Chrome Dino-style 2–4 pine tree clusters**, stratified cave rock textures, multi-depth crystal placement, and a **2.5D foreground cave archway** transition.
   * Refined audio by removing repetitive per-point chimes and tuning flap/hit effects to retro waveforms.
5. **Stage 5 — Endgame Pacing Polish:**
   Implemented stepped score-based horizontal speed scaling (`1.0x` → `2.0x`) synchronized across world scrolling and obstacle movement so high-score runs feel increasingly intense while staying fair.

---

## 🧩 Technical Architecture

Everything lives in a single self-contained `index.html` file with zero external images, fonts, or audio files:

* **Deterministic Procedural Graphics:** Uses lightweight 1D hash functions (`hash1D`) and multi-stop linear/radial gradients to draw mountain facets, pine tiers, mineral cave speckles, and crystal prisms consistently every frame.
* **Exact Geometric Hitboxes:** Implements circle-vs-triangle (`circleIntersectsTriangle`) and circle-vs-rectangle collision checks inset slightly from sharp pine and icicle tips so near-misses feel fair and responsive.
* **Continuous Terrain Function:** A dual-sine elevation function (`getGroundY(worldX)`) drives ground rendering, ground collision, tree planting, and stalagmite anchoring simultaneously.
* **Zero-Asset Web Audio API:** Synthesizes triangle-wave flap chirps and square-wave collision effects on the fly, unlocking automatically on the player's first gesture.

---

## 💻 How to Run Locally

Because **Arctic Flight** has zero dependencies or build steps, running it locally takes seconds:

```bash
# 1. Clone the repository
git clone https://github.com/ajil07/arctic-flight.git

# 2. Navigate into the project folder
cd arctic-flight

# 3. Open index.html directly in any modern browser
```

You can also double-click `index.html` in your file explorer or serve it with any static server (e.g., `npx serve` or VS Code's **Live Server** extension).

---

## 📁 Project Structure

```text
arctic-flight/
├── index.html          # Complete single-file game (HTML, CSS, Canvas JS, Web Audio)
├── README.md           # Project documentation, development process & live link
└── LICENSE             # MIT License
```

---

## 📄 License

This project is open-source and available under the **MIT License**.
