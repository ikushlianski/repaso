# Card List UI Specification

## Main Card List View
```
┌─────────────────────────────────────────────────────────────────┐
│ ← Back to Decks    Spanish Verbs (24 cards)     [+ New Card]    │
├─────────────────────────────────────────────────────────────────┤
│ [Search cards...] [All ▼] [Recent ▼] [Difficulty ▼]  [⊞ Select] │
├─────────────────────────────────────────────────────────────────┤
│ □ What is the past tense of "hablar"?                          │
│   → hablé, hablaste, habló...        📅 2 days ago  ⭐⭐⭐       │
│   [Study] [Edit] [•••]                                         │
├─────────────────────────────────────────────────────────────────┤
│ □ Complete: "Me gusta _____ español"                           │
│   → estudiar                         📅 1 week ago   ⭐⭐        │
│   [Study] [Edit] [•••]                                         │
├─────────────────────────────────────────────────────────────────┤
│ □ Conjugate "tener" in present tense                           │
│   → tengo, tienes, tiene...          📅 Yesterday    ⭐⭐⭐⭐      │
│   [Study] [Edit] [•••]                                         │
└─────────────────────────────────────────────────────────────────┘
```

## Card Preview States
- **Default**: Shows question preview and answer snippet
- **Selected**: Highlighted background with checkbox checked
- **Study mode**: Quick study button becomes prominent
- **Mobile**: Stacked layout with collapsed actions

## Filter Options
- All cards / New / Due for review / Mastered
- Sort by: Date added, Last studied, Difficulty, Alphabetical
- Search: Full text search across question and answer content