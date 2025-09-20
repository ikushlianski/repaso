# Data Architecture

## Database Strategy
- **Per-User Databases**: Each user gets isolated D1 database for data security and individual scaling
- **Cloudflare D1**: SQLite-compatible, 5GB free tier, $0.75/GB after
- **R2 Storage**: File storage for documents and images, 10GB free, $0.015/GB after

## Data Models
- **Cards**: ID, content, metadata, version, last_updated
- **Decks**: ID, name, description, card_count, user_id
- **AI_Requests**: ID, user_id, content_hash, response, cached_until
- **Sync_Log**: ID, user_id, operation, timestamp, conflict_resolution

## Data Isolation
- **User Data**: Completely isolated per D1 database
- **Marketplace**: Separate D1 database for public content
- **AI Cache**: Shared Redis cache with user-tier isolation
- **Backups**: Per-user snapshots to R2 storage

## Sync Strategy
- **Local-First**: IndexedDB for offline-first experience
- **Conflict Resolution**: Last-write-wins for simple conflicts, user approval for AI updates
- **Versioning**: Semantic versioning for card content evolution
