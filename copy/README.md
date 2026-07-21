# COPY

**"Abundance doesn't fix emptiness — giving does."**

A cozy stealth-economic / magical-realism slice-of-life game.

## Phase 0: The One Room

This is the initial prototype containing only the apartment scene with:
- Player movement (WASD)
- Duplication system (E key)
- Mana/HP HUD
- One narrative moment

## Running the Game

```bash
npm run dev
```

Then open `http://localhost:5173` in your browser.

## Controls

- **WASD** - Move player
- **E** - Interact (duplicate item, pick up, place down)

## Prototype Features

- Walk to the MUG on the TABLE
- Press E to duplicate (takes 1.5 seconds, costs 10 mana)
- First duplication triggers narrative text: *"Two mugs. One for coffee. One for... who?"*
- Pick up items and place them on the SHELF

## Tech Stack

- Phaser 3
- Vite
- JavaScript (ES6+)

## File Structure

```
copy/
├── index.html
├── package.json
├── vite.config.js
├── public/
│   └── sounds/
├── src/
│   ├── main.js
│   ├── scenes/
│   │   └── ApartmentScene.js
│   ├── entities/
│   │   ├── Player.js
│   │   └── Item.js
│   ├── systems/
│   │   ├── DuplicationSystem.js
│   │   └── HUD.js
│   ├── data/
│   │   └── items.json
│   └── text/
│       └── monologues.json
├── docs/
└── README.md
```

---

*Phase 0 — Just the room. The mug. The pop. The question.*
