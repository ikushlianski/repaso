# Edge Cases

## Navigation States
- **Deep nesting**: Breadcrumbs truncate gracefully with "..." for very long paths
- **No decks**: Show empty state with "Create your first deck" CTA
- **Offline mode**: Navigation works but shows offline indicator

## Responsive Behavior  
- **Tablet landscape**: Navigation adapts between mobile and desktop styles
- **Very wide screens**: Content area has max-width, navigation doesn't stretch awkwardly
- **Touch devices**: Navigation items have adequate touch targets (44px minimum)

## Accessibility
- **Keyboard navigation**: Tab order flows logically through navigation items
- **Screen readers**: Proper landmarks and skip links for navigation
- **High contrast**: Navigation remains visible in high contrast modes

## Performance
- **Slow connections**: Navigation loads first, content loads progressively  
- **Route changes**: Loading states during navigation transitions