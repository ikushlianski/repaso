# 0012 - Anki Migration

Enable seamless migration from Anki and other flashcard platforms to accelerate user onboarding and reduce switching friction.

## Business Value

- Dramatically reduces time-to-value for new users
- Captures users from established flashcard platforms
- Eliminates the biggest barrier to adoption (data migration)
- Creates competitive advantage through superior migration experience
- Enables rapid user base growth from existing flashcard communities

## Key Requirements

### Anki Import
- Support for .apkg (Anki package) files
- Preserve card content, formatting, and media
- Maintain deck hierarchy and organization
- Transfer study progress and scheduling data
- Handle Anki-specific features gracefully

### Other Platform Support
- Quizlet export formats
- SuperMemo compatibility
- Generic CSV/JSON import options
- Manual import for unsupported formats

### Migration Experience
- One-click import for simple cases
- Background processing for large collections
- Progress tracking and error reporting
- Preview before final import
- Rollback capability if needed

### Data Transformation
- Convert Anki-specific formatting to Repaso format
- Map Anki card types to Repaso equivalents
- Preserve media files and attachments
- Handle scheduling algorithm differences
- Maintain tag and deck relationships

## Dependencies

- Core flashcard system (0015)
- File upload and processing infrastructure
- Media storage and management
- Background job processing system

## Success Metrics

- Migration completion rate
- Time from upload to first study session
- User retention after migration
- Support ticket volume for migration issues
- Number of cards successfully imported
