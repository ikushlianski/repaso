# Anki Import Architecture

Detailed technical architecture for importing Anki collections, focusing on .apkg package format and database migration.

## Anki Data Format

### Package Structure (.apkg)
- SQLite database containing all card data
- Media files in separate directory
- JSON metadata for deck structure
- Binary data for attachments and media

### Database Schema
- **cards**: Individual flashcard records
- **notes**: Card content and metadata
- **decks**: Deck hierarchy and settings
- **tags**: Tag definitions and relationships
- **revlog**: Study history and statistics
- **media**: Media file references

## Import Process

### Phase 1: Package Extraction
1. Validate .apkg file format and version
2. Extract SQLite database from package
3. Extract media files to temporary storage
4. Parse JSON metadata for deck structure
5. Validate data integrity and completeness

### Phase 2: Data Transformation
1. Map Anki card types to Repaso equivalents
2. Convert Anki formatting to Repaso rich text
3. Transform scheduling data to Repaso algorithm
4. Map deck hierarchy to Repaso structure
5. Convert tags and metadata

### Phase 3: Content Processing
1. Process and optimize media files
2. Upload media to CDN storage
3. Update media references in card content
4. Generate thumbnails for images
5. Extract and index text content

### Phase 4: Database Migration
1. Create Repaso deck structure
2. Insert cards with transformed content
3. Migrate study progress and statistics
4. Set up scheduling and due dates
5. Create tag relationships

## Technical Implementation

### File Processing
```typescript
interface AnkiPackageProcessor {
  extractPackage(file: File): Promise<ExtractedData>
  parseDatabase(db: SQLiteDatabase): Promise<AnkiData>
  transformContent(data: AnkiData): Promise<RepasoData>
  migrateMedia(media: MediaFile[]): Promise<MediaReference[]>
}
```

### Data Mapping
- **Card Types**: Basic → Question/Answer, Cloze → Cloze Deletion
- **Formatting**: HTML → Markdown/Rich Text
- **Scheduling**: Anki algorithm → Repaso spaced repetition
- **Media**: Anki references → CDN URLs
- **Tags**: Anki tags → Repaso tag system

### Error Handling
- Invalid package format detection
- Corrupted database recovery
- Missing media file handling
- Data validation and sanitization
- User-friendly error reporting

## Performance Considerations

### Large Collections
- Streaming database processing
- Chunked media upload
- Background processing queue
- Progress tracking and updates
- Memory-efficient parsing

### Optimization
- Parallel media processing
- Database batch inserts
- CDN pre-warming
- Caching for repeated operations
- Lazy loading for large datasets

## Security and Validation

### File Validation
- Package signature verification
- Malware scanning for media files
- Content sanitization
- Size limits and quotas
- Format validation

### Data Integrity
- Checksum verification
- Referential integrity checks
- Duplicate detection
- Data consistency validation
- Rollback capability
