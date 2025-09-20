# Edge Cases

## Network Issues
- Auto-save fails → Show retry indicator
- Offline mode → Queue saves for sync
- Connection restored → Batch sync pending changes

## User Behavior
- Rapid typing → Debounce saves properly
- Browser crash → Restore from last auto-save
- Multiple tabs → Handle concurrent edits

## Content Limits
- Extremely long text → Warn at 1000 chars
- Empty cards → Allow but show validation hint
- Special characters → Sanitize but preserve formatting

## System States
- Server down → Graceful degradation to local storage
- Memory full → Clear old drafts automatically