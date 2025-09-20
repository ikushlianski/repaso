# US010 - Anki Package Import

As an Anki user, I want to import my entire Anki collection so I can seamlessly transition to Repaso without losing any of my existing flashcards or study progress.

## Requirements

### Anki Package Support
- Import .apkg files directly
- Extract and process Anki database format
- Handle Anki's SQLite-based storage
- Support both Anki 2.0 and 2.1+ formats
- Preserve all card metadata and settings

### Content Preservation
- Maintain original card text and formatting
- Transfer all media files (images, audio, video)
- Preserve deck hierarchy and organization
- Keep all tags and their relationships
- Maintain card creation and modification dates

### Study Data Migration
- Transfer scheduling information (due dates, intervals)
- Preserve study statistics and progress
- Maintain difficulty ratings and review history
- Convert Anki's scheduling algorithm to Repaso format
- Handle suspended and buried cards appropriately

### Import Process
- Drag-and-drop or file picker for .apkg files
- Progress indicator during import process
- Preview of what will be imported before confirmation
- Error handling and reporting for problematic cards
- Option to retry failed imports

## User Stories

1. As an Anki user, I want to upload my .apkg file so I can import my entire collection in one step
2. As a user, I want to see a preview of my import so I know exactly what will be transferred
3. As a user, I want my study progress preserved so I don't lose months of learning data
4. As a user, I want all my media files transferred so my cards work exactly as before
5. As a user, I want clear error messages if something goes wrong so I can fix issues quickly
6. As a user, I want to start studying immediately after import so I can continue my learning without interruption

## Business Value

- Eliminates the biggest barrier to switching from Anki
- Captures users with established, valuable collections
- Reduces onboarding friction to near zero
- Creates immediate value for new users
- Leverages existing user investment in flashcard content
