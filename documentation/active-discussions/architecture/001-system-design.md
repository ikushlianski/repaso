# Architecture: System Design

## High-Level Architecture

### Q1: System topology?
Overall structure:

**Architecture style:**
- [ ] Monolithic Next.js app
- [ ] Microservices (overkill?)
- [ ] Serverless functions + DB
- [ ] Static front + API backend
- [ ] Full-stack framework (Rails/Django)

**My recommendation:** Monolithic Next.js - fastest to build and deploy

*Your answer:*

---

### Q2: Data flow design?
How data moves through system:

**AI generation flow:**
```
User input → API → AI Provider → Process → Store → Return
```

**Caching layer?**
- [ ] Redis for everything
- [ ] Database caching only
- [ ] CDN for static
- [ ] No caching initially

**My recommendation:** Database caching for generated cards only

*Your answer:*

---

## Scalability Planning

### Q3: Scale bottlenecks?
What breaks first at 10K users?

**Potential issues:**
- [ ] AI API rate limits
- [ ] Database connections
- [ ] File storage
- [ ] Bandwidth costs
- [ ] Server memory

**My recommendation:** AI API rate limits will hit first

**Mitigation?**

*Your answer:*

---

### Q4: Database scaling?
When we need to scale:

**Strategy:**
- [ ] Vertical scaling (bigger server)
- [ ] Read replicas
- [ ] Sharding
- [ ] Switch to NoSQL
- [ ] Database per service

**My recommendation:** Vertical scaling until $50K MRR

*Your answer:*

---

## Infrastructure Decisions

### Q5: Deployment infrastructure?
Where everything runs:

**Platform:**
- [ ] Vercel (frontend) + Railway (backend)
- [ ] Everything on Vercel
- [ ] Everything on AWS
- [ ] Everything on Google Cloud
- [ ] Hybrid approach

**My recommendation:** Everything on Vercel - one platform, less complexity

*Your answer:*

---

### Q6: File storage?
For user content, images:

**Storage solution:**
- [ ] Database BLOB (bad idea)
- [ ] AWS S3
- [ ] Cloudflare R2
- [ ] Vercel Blob
- [ ] No files initially

**My recommendation:** Cloudflare R2 - S3 compatible, cheaper

*Your answer:*

---

## Security Architecture

### Q7: API security?
Protecting endpoints:

**Security measures:**
- [ ] API keys
- [ ] JWT tokens
- [ ] Rate limiting
- [ ] CORS properly configured
- [ ] All of above

**My recommendation:** JWT + rate limiting minimum

*Your answer:*

---

### Q8: Data isolation?
Multi-tenancy approach:

**Strategy:**
- [ ] Shared everything (filtered by user_id)
- [ ] Schema per user
- [ ] Database per user
- [ ] Row-level security

**My recommendation:** Shared everything with row-level security

*Your answer:*