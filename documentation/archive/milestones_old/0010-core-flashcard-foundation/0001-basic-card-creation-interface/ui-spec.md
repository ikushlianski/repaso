# UI Specification

## Primary Interface
Clean editor with minimal chrome. Auto-focus on first input field. Real-time preview shows exact study appearance.

## Key Actions
- "New Card" button (primary CTA)
- Auto-save indicator (subtle)
- Card type selector (inline, non-intrusive)

## Layout
```
┌─────────────────────────────────────┐
│ [New Card +]              [Save ✓]  │
├─────────────────────────────────────┤
│                                     │
│  Question/Front                     │
│  ┌─────────────────────────────────┐ │
│  │ [cursor here on load]           │ │
│  └─────────────────────────────────┘ │
│                                     │
│  Answer/Back                        │
│  ┌─────────────────────────────────┐ │
│  │                                 │ │
│  └─────────────────────────────────┘ │
│                                     │
└─────────────────────────────────────┘
```

## States
- **Empty**: Placeholder text guides user
- **Typing**: Live preview updates
- **Saved**: Subtle confirmation indicator