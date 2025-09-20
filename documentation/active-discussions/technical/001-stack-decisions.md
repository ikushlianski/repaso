# Technical: Stack Decisions

## Core Architecture

### Q1: Deployment approach?
For fastest iteration:

**Options:**
- [ ] Vercel + Serverless (your current plan)
- [ ] Railway/Render (simpler)
- [ ] AWS/Google Cloud (complex)
- [ ] Supabase (all-in-one)

**My recommendation:** Stick with Vercel + Serverless - you know it, it scales

*Your answer:*

---

### Q2: Database for MVP?
Given AI-first approach:

**What we need to store:**
- User accounts
- Generated cards (lots of text)
- Study progress
- Payment status

**Options:**
- [ ] PostgreSQL (Neon/Supabase)
- [ ] MongoDB (better for documents?)
- [ ] SQLite (simple but limited)
- [ ] Firestore (NoSQL, easy)

**My recommendation:** PostgreSQL with Neon - reliable, you know it, JSONB for flexibility

*Your answer:*

---

## AI Integration

### Q3: AI provider strategy?
Cost vs quality tradeoff:

**Options:**
- [ ] OpenAI only (GPT-4o-mini for everything)
- [ ] Anthropic Claude Haiku (cheaper, good quality)
- [ ] Mix: Claude for generation, GPT for embeddings
- [ ] Google Gemini Flash (very cheap)

**My recommendation:** Start with GPT-4o-mini only. Switch later if needed. Keep it simple.

*Your answer:*

---

### Q4: AI cost management?
At scale, AI costs will kill you:

**Strategies:**
- [ ] Cache generated cards by content hash
- [ ] Batch similar requests
- [ ] Use cheaper models for simple tasks
- [ ] Rate limit aggressively

**My recommendation:** Cache by content hash + aggressive rate limits

*Your answer:*

---

## Frontend Stack

### Q5: UI framework?
For rapid development:

**Options:**
- [ ] Next.js + Tailwind + shadcn/ui
- [ ] Next.js + MUI
- [ ] Remix + Tailwind
- [ ] SvelteKit (different but fast)

**My recommendation:** Next.js + Tailwind + shadcn/ui - lots of components ready

*Your answer:*

---

### Q6: Code highlighting?
Critical for our differentiator:

**Options:**
- [ ] Shiki (VSCode themes)
- [ ] Prism.js (lighter)
- [ ] Highlight.js (most compatible)
- [ ] CodeMirror (overkill?)

**My recommendation:** Shiki - best looking, worth the bundle size

*Your answer:*

---

## Authentication & Payments

### Q7: Auth solution?
Quick and secure:

**Options:**
- [ ] Clerk (your doc mentions it)
- [ ] NextAuth/Auth.js
- [ ] Supabase Auth
- [ ] Auth0

**My recommendation:** Clerk - expensive but saves weeks of work

*Your answer:*

---

### Q8: Payment processor?
For fastest integration:

**Options:**
- [ ] Stripe (build checkout yourself)
- [ ] Stripe Checkout (hosted)
- [ ] Lemon Squeezy (simpler)
- [ ] Paddle (handles tax)

**My recommendation:** Stripe Checkout - trusted, quick setup

*Your answer:*