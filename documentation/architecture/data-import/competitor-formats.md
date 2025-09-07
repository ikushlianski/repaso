# Competitor Format Support

Support for importing from various flashcard platforms beyond Anki, enabling comprehensive migration coverage.

## Supported Platforms

### Quizlet
- **Format**: Export files (.csv, .txt)
- **API**: Quizlet API integration for direct import
- **Features**: Study sets, folders, images, audio
- **Challenges**: Rate limiting, authentication
- **Strategy**: Both file import and API integration

### SuperMemo
- **Format**: Legacy .sm files, XML exports
- **Features**: Advanced scheduling, incremental reading
- **Challenges**: Complex algorithm mapping
- **Strategy**: Focus on content migration, simplify scheduling

### RemNote
- **Format**: JSON export, API access
- **Features**: Hierarchical notes, PDFs, flashcards
- **Challenges**: Complex note structure
- **Strategy**: Extract flashcard content, preserve hierarchy

### Memrise
- **Format**: CSV export, API integration
- **Features**: Courses, multimedia, community content
- **Challenges**: Course structure mapping
- **Strategy**: Focus on user-created content

### Generic Formats
- **CSV**: Standard comma-separated values
- **JSON**: Structured data format
- **XML**: Extensible markup language
- **TXT**: Plain text with custom delimiters

## Format Mapping

### Common Fields
```typescript
interface GenericCard {
  front: string
  back: string
  deck?: string
  tags?: string[]
  media?: MediaFile[]
  created?: Date
  modified?: Date
}
```

### Platform-Specific Mapping
- **Anki**: Complex mapping with scheduling data
- **Quizlet**: Simple front/back mapping
- **SuperMemo**: Algorithm-heavy with intervals
- **RemNote**: Hierarchical content extraction
- **Generic**: Flexible field mapping

## Technical Implementation

### Format Detection
```typescript
interface FormatDetector {
  detectFormat(file: File): Promise<ImportFormat>
  validateFile(file: File, format: ImportFormat): Promise<boolean>
  extractMetadata(file: File): Promise<FileMetadata>
}
```

### Import Adapters
```typescript
interface ImportAdapter {
  parse(file: File): Promise<ParsedData>
  transform(data: ParsedData): Promise<RepasoData>
  validate(data: RepasoData): Promise<ValidationResult>
}
```

### Error Handling
- Format-specific error messages
- Graceful degradation for unsupported features
- Partial import for corrupted files
- User guidance for manual fixes
- Detailed error reporting

## User Experience

### Import Wizard
- Step-by-step import process
- Format detection and confirmation
- Field mapping interface
- Preview before import
- Progress tracking

### Manual Import
- Template-based import for unsupported formats
- Field mapping interface
- Validation and error checking
- Batch import capabilities
- Custom format support

## Quality Assurance

### Data Validation
- Content sanitization
- Format validation
- Duplicate detection
- Media file verification
- Referential integrity

### Testing Strategy
- Unit tests for each format
- Integration tests for full pipeline
- Performance tests for large files
- Error scenario testing
- User acceptance testing

## Future Considerations

### Platform Expansion
- New platform support based on user demand
- API integration for real-time sync
- Community-contributed importers
- Plugin architecture for custom formats
- Automated format detection

### Advanced Features
- Incremental import for updates
- Two-way sync with source platforms
- Conflict resolution for modified content
- Bulk import from multiple sources
- Import scheduling and automation
