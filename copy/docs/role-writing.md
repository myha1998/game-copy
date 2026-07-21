# Narrative & World Writer Role

## Responsibilities

- NPC dialogue (short, warm, slightly melancholy)
- Environmental storytelling (notes, signs, overheard conversations)
- Item descriptions (every duplicable object gets a 1-line description)
- The "online listing" text when player sells a duplicate
- Day-start / day-end inner monologue (2–3 sentences max)
- The quiet emotional arc: loneliness → connection → giving

## Voice

- Understated. Never explains the magic.
- NPCs talk like real tired people, not quest-givers.
- The world notices small things. A new bench. A second mug. No one asks why.

## Constraints

- No lore dumps. No tutorials disguised as dialogue.
- Max 3 sentences per NPC interaction.
- The player's power is NEVER named in-game. He just... can.

## Current Text Assets

### Monologues (src/text/monologues.json)

```json
{
    "firstDuplication": "Two mugs. One for coffee. One for... who?"
}
```

### Item Descriptions (src/data/items.json)

- **Mug**: "A simple coffee mug. Warm to the touch."
- **Table**: "A small kitchen table."
- **Shelf**: "A wall-mounted shelf for storage."

## Future Writing Needs

- Neighbor NPC dialogue (3 variants)
- Shopkeeper greetings
- CopyMart listing descriptions
- Day-start monologues (7 variants)
- Day-end reflections (7 variants)
- Game-over text (gentle, not punitive)
