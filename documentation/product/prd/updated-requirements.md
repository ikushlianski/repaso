# Updated Product Requirements

## Core Functionality (Based on User Input)

### AI Flashcard Generation
**Multiple Card Types** (Priority: High)
- Multiple choice questions
- Fill-in-the-blank exercises  
- Simple Q&A pairs
- Code completion challenges
- Concept explanation cards

**Content Sources** (MVP Priority)
1. **Text files** (.txt, .md, .docx)
2. **Web pages** (URL import, browser extension)
3. **Manual input** (quick creation interface)
4. **PDFs** (Phase 2)
5. **API integration** (for language school and other systems)

### AI Control & Configuration
**Configurable Generation** (Subject-Level Control)
- Per-subject AI settings (generation style, difficulty, card types)
- User review/editing workflow (approve, edit, reject cards)
- Batch processing with progress streaming
- Generation time: few seconds to 1 minute with real-time UI updates

## Content Organization Hierarchy

### Suggested Structure (Updated)
Based on your input and general usability:

**Recommended**: `Subjects → Topics → Subtopics → Cards`
- **Subjects**: High-level areas (JavaScript, Data Science, System Design)
- **Topics**: Specific areas within subject (React Hooks, Machine Learning, Load Balancing)  
- **Subtopics**: Focused concepts (useState Hook, Linear Regression, CDN Strategy)
- **Cards**: Individual learning items

**Your Proposed**: `Subjects → Modules → Sections → Lessons`
- More academic/course-like structure
- Good for structured learning paths
- May be too deep for quick reference

**Recommendation**: Start with 3-level hierarchy (Subjects → Topics → Cards), allow nesting within Topics for power users who want deeper structure.

## Platform Strategy

### Multi-Platform Approach (All Priority)
**Phase 1**: Web app (works on all devices)
- Progressive Web App (PWA) for mobile experience
- Responsive design optimized for phone, tablet, desktop
- Offline capability (nice-to-have, not initial)

**Phase 2**: Native mobile apps
- iOS and Android apps for better mobile performance
- Push notifications for study reminders
- Enhanced offline functionality

**Phase 3**: Desktop apps (if needed)
- Electron-based desktop apps
- Better integration with local file systems

## Language School Integration

### API-First Approach
**Implementation**: Repaso receives data via API
- Language schools send vocabulary/content through API
- Repaso automatically generates cards from received data
- No language-specific features initially (language agnostic)
- Built as generic content import system

**Timeline**: Phase 2 feature (after core product proven)

## Technical Architecture Updates

### AI Integration Strategy
**Hybrid Approach** (API + Local)
- **Primary**: Cloud-based AI (OpenAI GPT-4) for complex generation
- **Secondary**: Local smaller models for simple tasks (cost optimization)
- **Streaming**: Real-time UI updates as cards are generated
- **Cost Management**: Usage tracking, optimization, caching

### Data & Privacy
**Cloud-First with Sync**
- User data stored in cloud with robust sync
- Local caching for offline access
- End-to-end encryption for sensitive content
- Export functionality for user data portability

### Sharing Features
**Phase 2 Social Features**
- Public/private deck sharing
- Community marketplace for card decks
- Team/organization sharing
- Not MVP priority

## Business Model (Freemium)

### Free Tier (Severe Limits)
**Purpose**: Let users try their flashcards and see retention value

**Limits**:
- 50 AI-generated cards per month
- 5 subjects maximum
- Basic card types only
- Manual creation unlimited (to hook users)

### Paid Tiers
**Individual Pro** ($39/month)
- Unlimited AI generation
- All card types and features
- Advanced organization tools
- API access for integrations
- Priority support

**Team** ($29/user/month, min 3 users)
- Shared decks and collaboration
- Team analytics and progress tracking
- Admin controls and user management

### Value Proposition vs Free Alternatives
**Why Pay vs Anki**:
1. **AI Generation**: Instant card creation from any content
2. **Knowledge Maintenance**: AI suggests updates and improvements
3. **Smart Nudges**: AI-powered study recommendations
4. **Premium UX**: Professional design vs amateur feel
5. **Integration**: API access and workflow tools
6. **Mobile Optimization**: Code and technical content that actually works

## Competitive Differentiation

### Against Existing Flashcard Apps
**Pain Points We Solve**:
- Manual card creation (we automate with AI)
- Poor hierarchy/organization (we enforce structure)
- Terrible mobile code display (we optimize for technical content)
- No quick input methods (we have multiple import options)

### Against Language Learning Apps
**Different Focus**:
- Professional/technical content vs casual language learning
- Retention of complex concepts vs vocabulary
- Integration with work/study tools vs gamification
- Premium pricing vs freemium mass market

## MVP Feature Priority

### Phase 1 (MVP - 3 months)
1. AI card generation from text and manual input
2. Basic 3-level hierarchy (Subjects → Topics → Cards)
3. Web app with mobile-optimized design
4. Multiple card types (Q&A, multiple choice, fill-in-blank)
5. Basic spaced repetition algorithm
6. Freemium model with usage limits

### Phase 2 (Growth - 6 months)
1. Browser extension and PDF import
2. API integration system
3. Team collaboration features
4. Advanced AI configuration options
5. Native mobile apps
6. Sharing and community features

### Phase 3 (Scale - 12 months)
1. Language school integration
2. Advanced analytics and insights
3. Enterprise features
4. Local AI models for cost optimization
5. Advanced collaboration tools
6. Marketplace for community decks

## Success Metrics (Updated)

### User Engagement
- Cards created per user per week (target: 50+ for paid users)
- Study session frequency (target: 5+ sessions/week)
- Retention improvement (measurable before/after)

### Business Metrics
- Free-to-paid conversion rate (target: 5%)
- Monthly churn rate (target: <3%)
- Average revenue per user (target: $400/year)
- API usage growth (B2B indicator)

### Technical Metrics
- AI generation success rate (target: 95%)
- Mobile performance (target: <2s load time)
- Multi-platform usage distribution
- Content import success rates