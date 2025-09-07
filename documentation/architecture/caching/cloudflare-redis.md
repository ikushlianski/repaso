# Cloudflare Redis Caching

## Setting Up Redis

We're using Cloudflare's managed Redis service, which gives us 256MB of memory on the free tier. It automatically takes snapshots every 15 minutes so we don't lose data, and we have master-slave replication for reliability. Everything's encrypted and isolated for security.

## How We Organize Cache Keys

We use a smart naming system that makes it easy to find what we need. AI responses get keys like `ai:abc123:premium:gpt4` so we know exactly what model processed what content for which user tier. User sessions get their own keys, and we even cache similar content lookups to speed up searches.

## Managing Memory Wisely

Redis automatically removes the least recently used items when memory gets full, and we set different time limits for different types of content. AI responses expire after 24-48 hours, while user content can stay cached for up to 7 days. We compress large objects to save space and clean up expired items in the background.

## Making It Fast

We batch Redis commands together instead of making individual calls, which is much faster. We keep 10-20 connections ready to go so we don't waste time establishing new ones. When we need data, we load it on-demand but always have a fallback ready. We also monitor everything closely to catch any performance issues before they become problems.
