# Edge Cases

## Empty States
- **No cards**: Show onboarding message with "Create first card" CTA
- **No search results**: Clear message with option to clear filters
- **All cards filtered out**: Show active filters with reset option

## Performance Issues
- **Large collections**: Virtual scrolling kicks in at 100+ cards
- **Slow search**: Show loading spinner after 500ms delay
- **Network timeout**: Show retry option, cache last results

## User Interactions
- **Rapid typing**: Debounce search to avoid API spam
- **Bulk select all**: Handle collections larger than current page
- **Filter conflicts**: Show warning when filters produce no results

## Content Issues
- **Very long card content**: Truncate preview with "..." 
- **Missing metadata**: Gracefully handle cards without last studied date
- **Corrupted cards**: Show error state with option to delete