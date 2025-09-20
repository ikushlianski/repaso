# Technical Requirements

We're building flashcards that work great on phones with code that's actually readable.

## What We Need to Build

### Mobile-First Everything
Code needs to look good on small screens. That means:
- Smart syntax highlighting that scales
- Swipe gestures (left/right for cards, up/down for code scrolling)
- Offline study sessions
- PWA that feels like a native app

### Code That Doesn't Suck on Mobile
- Syntax highlighting for major languages (start with top 20)
- Copy code snippets easily
- Zoom and scroll through long code blocks
- Math notation for algorithms (MathJax)
- Simple diagrams (Mermaid)

### Smart Content Generation
- AI turns documentation into flashcards
- Organizes content into proper hierarchies (no more 200-card dumps)
- Validates content quality before showing users

### Developer Workflow Integration
- Import from GitHub repos
- Browser extension for quick captures
- VS Code extension (later)
- CLI for bulk imports

## Data Architecture

**Database**: PostgreSQL (users, cards, study sessions)
**File Storage**: S3-compatible (images, documents)
**Cache**: Redis (sessions, frequent cards, AI results)

**Core Models**:
- Users, Cards, Decks, Study Sessions, Teams

## Security

**Auth**: OAuth with GitHub/Google, MFA for teams
**Privacy**: GDPR compliant, encrypt sensitive content
**Access**: Role-based permissions for teams

## Performance Targets

- Cards load in < 500ms
- Mobile app starts in < 2s  
- AI generation < 10s
- Support 10K users (Year 1)
- 50K cards per user max

## Tech Stack

**Frontend**: React + TypeScript, Tailwind, PWA
**Backend**: Node.js + TypeScript, Fastify, Prisma
**Database**: PostgreSQL (Supabase), Redis
**Hosting**: Vercel + Railway
**AI**: OpenAI GPT-4, vector search (Pinecone)
**Monitoring**: Sentry

## Development

**Quality**: TypeScript, ESLint, Prettier, Jest, Playwright
**CI/CD**: GitHub Actions, automated deployments
**Monitoring**: Error tracking, performance monitoring

## Success Metrics

**Technical**: 99.9% uptime, < 1s response time, < 0.1% mobile crashes
**User**: < 60s to first card, > 10min daily usage, > 80% completion rate

## Risks

**AI costs** → cache responses, optimize usage
**Mobile performance** → progressive enhancement, test on low-end devices
**Sync conflicts** → user-friendly resolution