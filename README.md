# 🤖 PTEC NoteBot — Crisp Edition

**PTEC NoteBot** is a crisp, retro-styled endless flyer game built entirely within a single HTML file. Inspired by classic "tap-to-flap" arcade games, it features a neon-lit cyberpunk cityscape, synthesized audio, and a unique **Boost** mechanic. 

Guide the NoteBot through an endless flight, dodge the columns, and see how far you can go!

---

## ✨ Features

- 🎮 **Endless Arcade Gameplay**: Classic physics-based flight with progressively increasing difficulty.
- ⚡ **Boost Mechanic**: Successfully pass **3 columns** to unlock a temporary speed boost and invincibility shield.
- 🏆 **Local Persistence**: High scores and audio preferences are saved locally on your device via `localStorage`.
- 🎵 **Procedural Audio**: Crisp, retro sound effects generated on the fly using the Web Audio API (no external `.mp3` or `.wav` files needed).
- 📱 **Responsive & Touch-Friendly**: Fully playable on both desktop (keyboard) and mobile (touch) devices with adaptive UI scaling.
- 🎨 **Dual Rendering Engine**: Uses a Sprite Sheet for crisp character animations, with a beautiful procedural vector fallback if the sprite sheet fails to load.
- ⏸️ **Full Game State Control**: Includes Title Screen, Game Over, Pause, and Mute functionalities.

---

## 🎮 Controls

### Desktop (Keyboard)
| Action | Keys |
| :--- | :--- |
| **Flap / Start** | `Space`, `W`, or `Up Arrow` |
| **Boost** | `B`, `Left Shift`, or `Right Shift` *(Unlocks after 3 columns)* |
| **Pause / Resume** | `P` or `Esc` |
| **Mute / Unmute** | `M` |
| **Restart** | `R` *(on Game Over screen)* |
| **UI Navigation** | `Enter` *(to select Play/Retry)* |

### Mobile / Tablet (Touch)
- **Flap / Start**: Tap anywhere on the screen.
- **Boost**: Tap the glowing **⚡ BOOST** button that appears in the bottom right corner once unlocked.
- **Pause**: Tap the screen when the pause overlay is active.
- **Mute**: Tap the speaker icon in the top right corner.

---

## 🚀 Getting Started

Since this is a zero-dependency, single-file application, running it is incredibly simple:

1. **Download** the HTML file (e.g., `index.html`).
2. **Open** the file directly in any modern web browser (Chrome, Firefox, Safari, Edge).
3. *(Optional)* **Sprite Sheet**: The game includes an embedded base64 fallback image. If you have a custom `notebot_sprites.png` sprite sheet, place it in the same directory and update the `sheet.src` in the code to `'notebot_sprites.png'` for custom animations. Otherwise, the game will automatically render the beautiful vector-based NoteBot.
4. **Play!** Click "PLAY" or press `Space` to start your flight.

*Note: For the best experience on mobile, add the page to your Home Screen to play in full-screen standalone mode.*

---

## 🛠️ Technical Stack

- **Core**: Vanilla HTML5, CSS3, JavaScript (ES6+)
- **Rendering**: HTML5 `<canvas>` API (60 FPS game loop with delta-time physics)
- **Audio**: Web Audio API (Oscillators and Noise Buffers for SFX)
- **Storage**: `window.localStorage` (with safe try/catch wrappers for private browsing modes)
- **Styling**: CSS Variables, Flexbox, Grid, and custom `@keyframes` animations for the UI overlays.
- **No Build Tools**: No Webpack, Vite, React, or external libraries required. Just pure web standards.

---

## 📂 Code Architecture

The entire game is encapsulated within an IIFE (Immediately Invoked Function Expression) to prevent global scope pollution. Key modules include:

- **State Machine**: Manages transitions between `TITLE`, `READY`, `PLAY`, `DEAD`, and `OVER` states.
- **Scenery Generator**: Procedurally generates parallax starfields, clouds, motes, and multi-layered city skylines.
- **Physics & Collision**: Custom circle-rectangle collision detection for the NoteBot and the pipes.
- **Particle System**: Handles visual feedback like flap puffs, boost trails, speedlines, and death explosions.
- **Audio Engine**: A lightweight synthesizer that creates distinct tones for flapping, scoring, boosting, and crashing.

---

## 🏆 Medals & Scoring

Earn medals based on your flight distance:
- `· FLIGHT TRAINEE` (0 - 4)
- `● STICKY ROOKIE` (5 - 14)
- `▲ PAPER PILOT` (15 - 29)
- `◆ NOTE ACE` (30 - 49)
- `★ ENDLESS LEGEND` (50+)

---

## 📄 License

This project is provided as-is for educational and entertainment purposes. Feel free to fork, modify, and distribute your own versions of the NoteBot!
