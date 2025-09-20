# Payment Infrastructure Overview

Stripe-based subscription billing system that integrates with both the marketing website and main application.

## Core Requirements

**Subscription Management**
- Multiple pricing tiers (Free, Standard, Premium, Professional)
- Monthly and annual billing cycles
- Automatic prorations for plan changes
- Grace periods for failed payments
- Subscription pause/resume functionality

**Payment Processing**
- Credit card processing via Stripe
- Support for international payments
- PCI compliance through Stripe
- Automatic retry logic for failed payments
- Subscription lifecycle webhooks

**Integration Points**
- Marketing website: Pricing pages and checkout flows
- Main application: Feature gates and usage limits
- Customer portal: Self-service subscription management
- Admin dashboard: Customer support and analytics

## Technical Implementation

**Stripe Products Setup**
- Free Tier: $0/month (250 cards, basic features)
- Standard Tier: $8/month (5,000 cards, mobile app)
- Premium Tier: $15/month (unlimited cards, AI features)
- Professional Tier: $30/month (team features, API access)

**Webhook Handling**
- Payment succeeded/failed events
- Subscription created/updated/cancelled
- Customer portal sessions
- Invoice generation and payment

**Security Considerations**
- Never store payment details directly
- Use Stripe Customer Portal for subscription changes
- Implement proper webhook signature verification
- Secure API key management and rotation

## Business Logic

**Feature Gates**
- Card limits enforced at creation time
- AI generation quotas per billing cycle
- Team collaboration features by plan tier
- API rate limiting by subscription level

**Billing Edge Cases**
- Failed payment recovery sequences
- Subscription cancellation and data retention
- Refund processing and prorations
- Plan downgrade data migration