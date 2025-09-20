# Data Models

## Core Entities

**Cards**: The heart of our system - individual flashcards with content, metadata, and versioning
**Decks**: Collections of cards organized in hierarchical structures
**Users**: Account information, preferences, and subscription details
**Study Sessions**: Tracking when and how users study their cards
**AI Requests**: Logging AI interactions for cost control and improvement

## Card Structure

**Content**: The actual question and answer content with rich text support
**Metadata**: Tags, difficulty, creation date, and last modified
**Versioning**: Track all changes for audit trails and rollback
**Relationships**: Links to decks, study sessions, and AI updates
**Sync Status**: Track what's been synced and what's pending

## Deck Organization

**Hierarchy**: Support for nested decks and sub-decks
**Permissions**: Control who can view and edit each deck
**Settings**: Study preferences and AI update settings per deck
**Statistics**: Track performance and usage across decks
**Sharing**: Support for public and private deck sharing

## User Data

**Profile**: Basic information, preferences, and subscription tier
**Study History**: Complete record of all study sessions and progress
**AI Usage**: Track AI requests and costs per user
**Sync Preferences**: Control what data syncs and when
**Privacy Settings**: Control data sharing and visibility

## AI Integration

**Request Logging**: Track all AI interactions for cost control
**Response Caching**: Store AI responses to avoid duplicate requests
**Update Tracking**: Log when AI updates cards and why
**Cost Attribution**: Track AI costs per user and feature
**Quality Metrics**: Monitor AI response quality and user satisfaction
