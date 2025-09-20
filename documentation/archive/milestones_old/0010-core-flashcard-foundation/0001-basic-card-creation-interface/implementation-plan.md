# Implementation Plan

## Core Components
- `CardEditor` - Main editing interface
- `AutoSave` - Background persistence hook
- `CardPreview` - Real-time preview component

## Technical Steps
1. Create basic editor layout with two text areas
2. Implement auto-save with 2-second debounce
3. Add real-time preview synchronization
4. Set up keyboard shortcuts (Ctrl+N for new card)
5. Add loading and saved states with visual feedback

## Data Flow
User types → debounced save → local state update → preview refresh → backend sync

## Key APIs
- `createCard()` - Initialize new card
- `updateCard(id, content)` - Auto-save changes
- `previewCard(content)` - Generate preview