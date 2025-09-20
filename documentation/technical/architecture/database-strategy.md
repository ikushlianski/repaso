# Database Strategy

## Cloud Database (Postgres)

**Primary Storage**: Cloudflare D1 (Postgres-compatible) for all user data
**Per-User Isolation**: Each user gets their own database for security and scaling
**Backup Strategy**: Daily snapshots to R2 storage for disaster recovery
**Scaling**: Databases scale automatically based on user activity

## Local Database (PGlite)

**User Device Storage**: PGlite (SQLite in browser) for local data
**Complete Replication**: Full copy of user data on each device
**Offline Functionality**: Works completely without internet connection
**Performance**: Instant queries and updates on local data
**Storage Management**: Automatic cleanup of old data when needed

## Electric SQL Sync

**Real-time Sync**: Changes sync instantly between devices and cloud
**Partial Replication**: Only sync data the user actually needs
**Conflict Resolution**: Smart handling of simultaneous changes
**Bandwidth Optimization**: Only sync changes, not entire datasets
**Network Awareness**: Adapts to connection quality and speed

## Data Flow

**User Action**: User creates or updates a card locally
**Local Save**: Change is saved to PGlite immediately
**Background Sync**: Electric SQL syncs change to cloud Postgres
**Cross-Device**: Other devices receive the update via Electric SQL
**Conflict Handling**: Smart resolution if changes conflict

## Security and Privacy

**Data Encryption**: All data encrypted in transit and at rest
**User Control**: Users control what data is synced and when
**Privacy by Default**: Data stays on user's device first
**Audit Trail**: Complete history of all data changes
**Compliance**: Meets data protection requirements
