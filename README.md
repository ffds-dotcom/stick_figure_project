# Stick Figure Project

A tiny browser platformer where you run and jump a stick figure across floating platforms. The whole game lives in a single `index.html` file — no build step, no dependencies, no server required.

Built with plain HTML5 Canvas and vanilla JavaScript.

## Demo / Screenshot

A stick figure stands on grass-topped platforms against a red sky with drifting clouds. Walk left/right to make the legs swing, and jump between the three platforms.

> Tip: enable **GitHub Pages** for this repo (Settings → Pages → deploy from `main`) to get a public link to play in the browser.

## Features

- 🕹️ **Keyboard controls** — Arrow keys or WASD to move, Space / Up to jump
- 🦵 **Procedural walk animation** — the figure's legs swing while moving on the ground
- 🌍 **Simple physics** — gravity, jumping, and AABB platform collision detection
- 🧱 **Three platforms** — a full-width ground plus two elevated ledges to hop between
- 🎨 **Hand-drawn look** — canvas-rendered sky gradient, clouds, grass-topped platforms, and a stroked stick figure
- ♻️ **Auto-respawn** — fall off the bottom of the screen and you reset to the start
- 📦 **Zero dependencies** — one self-contained HTML file

## Controls

| Action      | Keys                         |
| ----------- | ---------------------------- |
| Move left   | `←` or `A`                   |
| Move right  | `→` or `D`                   |
| Jump        | `Space`, `↑`, or `W`         |

## Getting Started

No installation or build tools needed.

### Option 1 — Open the file directly

1. Clone the repository:
   ```bash
   git clone https://github.com/ffds-dotcom/stick_figure_project.git
   cd stick_figure_project
   ```
2. Open `index.html` in any modern web browser (double-click it, or drag it into a browser window).

### Option 2 — Run a local web server (optional)

Any static server works. For example, with Python:

```bash
python3 -m http.server 8000
```

Then visit <http://localhost:8000> in your browser.

## How It Works

The game runs entirely on the HTML5 `<canvas>` element (`800 × 500`) and a `requestAnimationFrame` loop that does two things every frame:

1. **`update()`** — reads the pressed keys, applies horizontal movement and gravity, resolves collisions against each platform, advances the leg-swing animation, clamps the player to the canvas, and respawns the figure if it falls off-screen.
2. **`draw()`** — clears the canvas and repaints the sky gradient, clouds, platforms, and the stick figure.

Tweakable constants near the top of the script let you change the feel of the game:

```js
const SPEED = 3.5;   // horizontal movement speed
const JUMP  = -11;   // jump strength (negative = up)
const GRAV  = 0.45;  // gravity per frame
```

You can also edit the `platforms` array to change the level layout, or `drawStickFigure()` to change how the character looks.

## Project Structure

```
stick_figure_project/
├── index.html   # The entire game: markup, styles, and JavaScript
└── README.md    # This file
```

## Built With

- HTML5 Canvas
- Vanilla JavaScript (no frameworks or libraries)
- CSS

## Contributing

Issues and pull requests are welcome. Fun ideas to extend it:

- Add coins, enemies, or a scoring system
- Add scrolling / a larger level
- Add a double-jump or wall-jump
- Mobile / touch controls

## License

No license is currently specified. Add a `LICENSE` file (e.g. [MIT](https://choosealicense.com/licenses/mit/)) if you'd like to make reuse terms explicit.
