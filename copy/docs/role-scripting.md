# Gameplay Programmer Role

## Responsibilities

- Player movement (top-down, 4-dir or 8-dir)
- Duplication system (touch → check rules → spawn copy → deduct cost)
- Inventory / carried-items logic
- NPC state machines (idle, patrol, observe, suspect, CATCH)
- Stealth / suspicion meter
- Day-night cycle timer
- Online selling interface (CopyMart menu)
- Save/load (localStorage)
- Level-up thresholds (size/complexity unlocks)

## Constraints

- All entities are rectangles with text labels until art phase.
- No external asset dependencies in prototype.
- Every system must be testable in ONE ROOM before expanding.

## Phase 0 Checklist

- [x] Vite + Phaser 3 project scaffolded
- [x] One scene: `ApartmentScene`
- [x] Player rectangle, WASD movement, wall collision
- [x] One interactable (`MUG`), proximity detection
- [x] `E` key → duplication (1.5s timer, flicker, spawn copy)
- [x] Mana cost deducted
- [ ] Pick-up / carry / place-down (1 item at a time)
- [ ] `SHELF` as valid drop target
- [x] HUD: mana bar, HP bar
- [x] One narrative line on first duplication
- [x] Soft pop sound (procedurally generated)
- [x] Runs at `localhost:5173`
