# Edge Cases

## Validation Issues
- **Empty name**: Show inline error, disable create button
- **Duplicate names**: Allow but suggest uniqueness
- **Very long names**: Truncate display but preserve full name
- **Special characters**: Sanitize but allow Unicode for international users

## System States
- **Network failure**: Save to local storage, sync when online
- **Storage full**: Show warning before creation fails
- **Concurrent creation**: Handle race conditions gracefully

## User Behavior
- **Multiple rapid clicks**: Debounce create button
- **Navigate away during creation**: Auto-save draft
- **Browser crash**: Restore unsaved deck from local storage

## Display Issues
- **Many decks**: Pagination or infinite scroll
- **No decks**: Show onboarding flow with sample deck creation
- **Loading states**: Show skeleton while fetching deck list