# COPY — Game Design & Build Plan

**"Abundance doesn't fix emptiness — giving does."**

- Genre: Cozy stealth-economic / magical-realism slice-of-life
- Platform: Web (browser)
- Perspective: Top-down 2D
- Art (prototype): Colored rectangles + text labels
- Art (final): Pixel art (later phase)
- Date: 2026-07-21
- Status: Phase 0 — Complete ✓

---

## 1. TECH STACK

| Layer | Choice | Why |
|-------|--------|-----|
| Engine | Phaser 3 | 2D top-down, tilemaps, input, physics built in. Browser-native. Free. |
| Language | JavaScript (ES6+) | No build step to start. Migrate to TypeScript later. |
| Bundler | Vite | Instant dev server, hot reload, zero config. |
| Maps | Tiled → JSON | Design neighborhood visually, export to Phaser tilemap. |
| Hosting | itch.io / GitHub Pages | Free, instant shareable link. |
| Version Control | Git + GitHub | Non-negotiable from day one. |

No server. No database. No accounts. Pure client-side game.

---

## 2. CORE RULES

### 2a. Duplication Rules

| Rule | Detail |
|------|--------|
| CAN duplicate | Objects only. Mugs, chairs, books, phones, food, tools, furniture. |
| CANNOT duplicate | People. Animals. The player. Abstract things (money directly). |
| Size limit | Scales with level. Lvl 1: hand-held. Lvl 3: furniture. Lvl 5: vehicles (never a whole bus). |
| Cost | Mana (per duplication, scales with size) + Health (small drain, recovers with sleep/food). |
| Secrecy | NPCs must NOT see it happen. Witnessed → suspicion rises. 100% suspicion → GAME OVER. |
| Uniqueness | Player is the ONLY person with this power. No one else. Ever. |

### 2b. Economic Loop

1. Duplicate object (secretly, unseen)
2. List on "CopyMart" (in-game phone menu, fictional marketplace)
3. Buyer picks up from dead-drop location (no face-to-face)
4. Money arrives as "legit" income
5. Spend on: rent, food, mana recovery (coffee), apartment upgrades, gifts for NPCs

### 2c. Day-Night Cycle

- One in-game day ≈ 8 real minutes.
- Morning: apartment (safe zone, save point, inner monologue).
- Daytime: neighborhood (NPCs active, shops open, selling window).
- Evening: fewer NPCs, easier to duplicate risky items.
- Night: almost no one outside. Best for big duplications. Health drains if you skip sleep.

---

## 3. THE NEIGHBORHOOD (Full Scope)

```
┌─────────────────────────────────────────────┐
│ YOUR APARTMENT │ ← Start. Safe zone.
│ (bed, desk, shelf, kitchen) │
└──────────────────┬──────────────────────────┘
                   │ (door / stairs)
┌──────────────────┴──────────────────────────┐
│             STREET (main)                   │
│                                             │
┌────┴────┐         ┌────┴─────┐
│ PARK    │         │ CORNER   │
│ (bench, │         │ SHOP     │
│ tree,   │         │(supplies)│
│ pond)   │         └──────────┘
└─────────┘              │
       │           ┌─────┴─────┐
       │           │ DEAD-     │
       │           │ DROP      │
       │           │ SPOT      │
       │           │ (sell)    │
       │           └───────────┘
┌──────┴────────────────────────┐
│ OFFICE BUILDING               │ ← Boring day job.
│ (daytime obligation)          │   Duplicate office supplies = early game.
└───────────────────────────────┘
```

Total walkable area: ~5 screens. That's the whole world.

---

## 4. PROGRESSION

| Level | Unlock | Example |
|-------|--------|---------|
| 1 | Hand-held (mug, pen, phone, apple) | Duplicate staplers. Sell $5 each. |
| 2 | Medium (chair, lamp, backpack) | Furnish apartment. Gift a lamp to neighbor. |
| 3 | Large (table, bicycle, TV) | Bigger sales. More suspicion risk. |
| 4 | Complex (laptop, guitar, power tools) | High-value. Government agents patrol. |
| 5 | Very large (car, piano — NOT a bus) | Endgame. Final choice: hoard or give away. |

---

## 5. PHASE 0 — COMPLETED ✓

### What exists on screen:

- ✓ A rectangle room (apartment). Walls = grey rectangles.
- ✓ Blue rectangle labeled `YOU` (player). WASD / arrow keys.
- ✓ Brown rectangle labeled `MUG` on a yellow rectangle labeled `TABLE`.
- ✓ Grey rectangle labeled `SHELF` on the wall.
- ✓ HUD corner: `MANA: ██████ 100%` and `HP: ██████ 100%`.

### The interaction (the entire prototype):

1. ✓ Walk `YOU` next to `MUG`.
2. ✓ Press `E`.
3. ✓ 1.5-second pause. Mug flickers (opacity blink). Soft *pop* sound.
4. ✓ Second `MUG` appears beside the first. Mana −10.
5. ✓ Press `E` on a mug → pick up (label: `YOU + MUG`).
6. ✓ Walk to `SHELF`. Press `E`. Mug placed. Label: `SHELF (1 mug)`.
7. ✓ Walk back. Two mugs on table. You stare.
8. ✓ Text fades in at bottom: *"Two mugs. One for coffee. One for... who?"*

### Technical checklist:

- [x] Vite + Phaser 3 project scaffolded
- [x] One scene: `ApartmentScene`
- [x] Player rectangle, WASD movement, wall collision
- [x] One interactable (`MUG`), proximity detection
- [x] `E` key → duplication (1.5s timer, flicker, spawn copy)
- [x] Mana cost deducted
- [x] Pick-up / carry / place-down (1 item at a time)
- [x] `SHELF` as valid drop target
- [x] HUD: mana bar, HP bar
- [x] One narrative line on first duplication
- [x] Soft pop sound (procedurally generated)
- [x] Runs at `localhost:5173`

---

## 6. FUTURE PHASES

| Phase | What |
|-------|------|
| 1 | One NPC neighbor. Vision cone. Suspicion meter. Game-over screen. |
| 2 | Street, park, shop. Day-night cycle. Office building. |
| 3 | CopyMart selling. Money. Rent. Economic pressure. |
| 4 | 3 NPC homes. Dialogue. Gift-giving. Emotional arc. |
| 5 | Levels 2–5 unlocks. Bigger objects. Agents. Cameras. |
| 6 | Final choice ending. Polish. Sound. Music. Replace boxes → pixel art. |
| 7 | Ship to itch.io. |

---

## 7. THE FEELING (North Star)

Every decision filters through this:

> A tired man stands in a small kitchen.
> There are two identical mugs on the counter.
> He picks one up. Puts it down. Picks up the other.
> They are exactly the same.
> He doesn't know why that makes him sad.

If a feature doesn't serve *that* feeling, cut it.

---

*Document: COPY — Game Design & Build Plan*
*Last updated: 2026-07-21*
*Status: Phase 0 — Complete ✓*
