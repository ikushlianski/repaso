# Caching Architecture Overview

## How We Handle Caching

Think of our caching like a smart filing system that gets faster as it learns. We use four layers that work together to make everything feel instant.

**Browser Storage (L1)**: This is where users' data lives locally, so they can work offline and see changes instantly. It's like having a personal filing cabinet that syncs with the cloud.

**Redis Cache (L2)**: This is our smart memory that remembers AI responses and processed content. When someone asks for something similar to what we've seen before, we can respond almost instantly instead of calling expensive AI services.

**File Storage (L3)**: Documents and images live here, with a CDN that delivers them quickly from locations close to users worldwide.

## What We Cache

**AI Responses**: We're clever about this - if someone uploads content that's 85% similar to something we've processed before, we can reuse most of the work instead of starting from scratch.

**User Content**: Processed documents and card collections get cached so they load instantly on repeat visits.

**User Sessions**: Login info and preferences stay cached to avoid repeated authentication calls.

**Static Files**: Images and documents get cached globally so they load fast no matter where the user is.

## When We Clear Cache

We clear cache automatically when content changes, when users upgrade their plans, or after certain time periods. We also have manual controls for when we need to push updates quickly.
