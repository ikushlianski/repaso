# Navigation UI Specification

## Desktop Layout
```
┌─────────────────────────────────────────┐
│ [Logo] My Decks  Study  Browse Settings │ 
├─────────────────────────────────────────┤
│                                         │
│  [Content Area]                         │
│                                         │
│                                         │
└─────────────────────────────────────────┘
```

## Sidebar Alternative
```
┌───────┬─────────────────────────────────┐
│ Logo  │  Breadcrumb > Current > Page    │
├───────┼─────────────────────────────────┤
│My Deck│                                 │
│Study  │  [Main Content Area]            │
│Browse │                                 │
│Settings│                                │
└───────┴─────────────────────────────────┘
```

## Mobile Adaptation
```
┌─────────────────────────────────────────┐
│ [≡] Repaso              [@] [Settings]  │
├─────────────────────────────────────────┤
│                                         │
│  [Content Area]                         │
│                                         │
├─────────────────────────────────────────┤
│ [Decks] [Study] [Browse] [More]         │
└─────────────────────────────────────────┘
```

## States
- **Active**: Current section highlighted with color/background
- **Hover**: Subtle visual feedback on interactive elements  
- **Mobile**: Hamburger menu or bottom tabs