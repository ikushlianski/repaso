# Cache Invalidation Strategy

## When We Clear Cache

We clear cache automatically when users update their cards or documents, when we update our AI models or prompts, or when users change their subscription tiers. We also do scheduled maintenance clears when we push updates to the system.

## How We Clear Cache

Most of the time, cache clears itself based on time limits we set for different types of content. When content changes, we get notified via webhooks and clear the relevant cache entries immediately. For emergencies, we have admin controls to clear cache manually, and we can be selective about which parts of the cache to clear.

## Keeping Cache Warm

We're proactive about keeping frequently accessed content ready to go. During off-peak hours, we pre-load popular content based on what users actually study. We prioritize caching trending content and make sure caches in different geographic regions stay warm for local users.

## Watching Performance

We keep a close eye on our cache performance. We want to see 80% or better cache hit rates, which means most requests are served from cache instead of expensive AI calls. We get alerts when Redis memory usage gets too high, and we track how often we're clearing cache to make sure we're not doing it unnecessarily. We also monitor response times to catch any performance issues early.
