# Ultra-Thin Milestone Roadmap

## Philosophy: Ship Something Usable Every 2-3 Weeks

Each milestone delivers a complete, usable increment. No half-finished features.

## Milestone 0001: Foundation (Weeks 1-3)
**Goal**: User can create account, manually create basic cards, and study them
**Usable Outcome**: Working flashcard app (manual creation only)

**User Stories**:
- Simple email/password auth (no social login yet)
- Basic card CRUD (question/answer only)
- Single "General" subject (hardcoded)
- Basic study session (show card, reveal answer, mark easy/hard)
- Simple spaced repetition (basic algorithm)
- Web app only, mobile-responsive design

## Milestone 0002: Content Organization (Weeks 4-5) 
**Goal**: Users can organize cards into subjects and basic hierarchy
**Usable Outcome**: Organized learning with multiple topics

**User Stories**:
- Create/edit/delete subjects (up to 5 for free tier)
- Basic topics within subjects (one level deep)
- Move cards between subjects/topics
- Subject-based study sessions
- Card counter per subject/topic

## Milestone 0003: AI Card Generation MVP (Weeks 6-8)
**Goal**: AI can create cards from text input
**Usable Outcome**: Automated card creation that actually works

**User Stories**:
- Paste text → AI generates Q&A cards
- User reviews/edits generated cards before saving
- Simple generation (no code highlighting yet)
- Usage tracking (100 cards/month limit for free)
- Basic error handling and user feedback

## Milestone 0004: Mobile Experience (Weeks 9-10)
**Goal**: Great mobile study experience
**Usable Outcome**: Mobile-optimized study sessions

**User Stories**:
- Swipe gestures (left/right for cards, up/down for answers)
- Touch-optimized card interface
- Offline study (basic caching)
- Mobile navigation optimized for one hand
- Fast loading (<2s per card)

## Milestone 0005: Code Support (Weeks 11-13)
**Goal**: Technical content displays properly
**Usable Outcome**: Developers can study code effectively

**User Stories**:
- Syntax highlighting for top 10 languages
- Code formatting preservation
- Copy code snippets
- Auto-detect programming language
- Mobile-optimized code display

## Milestone 0006: Import & Export (Weeks 14-15)
**Goal**: Users can import content from external sources
**Usable Outcome**: Easy content migration and backup

**User Stories**:
- URL import (basic web scraping)
- Text file upload (.txt, .md)
- Export cards to JSON/CSV
- Anki import (basic compatibility)
- Bulk operations (delete/move multiple cards)

## Milestone 0007: Enhanced Study Experience (Weeks 16-17)
**Goal**: Better study algorithms and user experience
**Usable Outcome**: Improved retention and engagement

**User Stories**:
- Multiple card types (multiple choice, fill-in-blank)
- Study statistics and progress tracking
- Streak tracking and basic gamification
- Customizable study session length
- Review overdue cards functionality

## Milestone 0008: Team Features MVP (Weeks 18-20)
**Goal**: Basic team collaboration
**Usable Outcome**: Teams can share and study together

**User Stories**:
- Invite team members
- Shared subjects/decks
- Team member progress overview
- Basic permission system (admin/member)
- Team billing and subscription management

## Milestone 0009: Advanced AI Features (Weeks 21-23)
**Goal**: AI that creates better, more organized content
**Usable Outcome**: Smart content processing and organization

**User Stories**:
- AI content organization (proper hierarchies)
- Multiple content sources (PDF, GitHub repos)
- AI suggests improvements to existing cards
- Configurable AI generation settings
- Batch AI processing with progress tracking

## Milestone 0010: Mobile Apps (Weeks 24-28)
**Goal**: Native mobile experience
**Usable Outcome**: App store presence and native performance

**User Stories**:
- iOS and Android native apps
- Push notifications for study reminders
- Offline sync with conflict resolution
- Native sharing capabilities
- App store optimization and publishing

## Key Design Decisions

### Subject vs Module Hierarchy
**Problem**: 1 subject limit can be gamed by using modules as subjects

**Solution**: Enforce hierarchy semantically
- **Subject**: Broad area (JavaScript, Machine Learning, System Design)
- **Topic**: Specific area within subject (React Hooks, Neural Networks, Load Balancing) 
- **Cards**: Individual learning items

**Free Tier Limit**: 1 subject, unlimited topics within it
**Why**: Forces users to focus, but gives flexibility within their chosen area

### URL Import Scope
**Supported URLs**:
- Documentation sites (GitHub wikis, GitBook, Notion public pages)
- Blog posts and articles
- Stack Overflow questions/answers
- Simple web pages with readable content

**Not Supported Initially**:
- Complex SPAs or JavaScript-heavy sites
- Video content or interactive materials
- Password-protected or login-required content

### Measuring Learning Effectiveness

**Retention Statistics**:
- Before: Track failed attempts per card
- After: Compare success rate over time
- Simple metric: "You got 73% right this week vs 45% when you started"

**Learning Speed**:
- Track time from first seeing card to "mastering" it (3 consecutive correct answers)
- Compare AI-generated cards vs manually created cards
- Simple metric: "AI cards: 2.3 reviews to master, Manual cards: 4.1 reviews to master"

## Success Criteria per Milestone

**Milestone 0001**: 100 users create account and study cards
**Milestone 0002**: Users organize >50 cards into subjects/topics  
**Milestone 0003**: AI generates 1000+ cards with >80% user approval
**Milestone 0004**: >70% of study sessions happen on mobile
**Milestone 0005**: Developers use code highlighting features regularly
**Milestone 0006**: Users import content from external sources successfully
**Milestone 0007**: Improved retention metrics vs basic algorithm
**Milestone 0008**: First 10 paying team customers
**Milestone 0009**: AI organization reduces manual card editing by 60%
**Milestone 0010**: Mobile app reaches >1000 downloads

## Risk Mitigation

**Technical Risks**:
- AI costs too high → Start with simple models, optimize later
- Mobile performance poor → Progressive enhancement approach
- Sync conflicts → Start with simple last-write-wins

**Business Risks**:
- Users don't convert → Focus on demonstrating clear value early
- Competition copies features → Build community and workflow integration
- Technical complexity underestimated → Keep milestones small and shippable

## Next Steps

1. Detail user stories for Milestone 0001
2. Set up technical architecture for MVP
3. Begin development with simple auth and card creation
4. Test with early users after each milestone

Each milestone should feel like a complete product upgrade, not a half-finished feature dump.