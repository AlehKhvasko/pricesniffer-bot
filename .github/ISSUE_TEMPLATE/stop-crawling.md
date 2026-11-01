---
name: Stop crawling my site
about: Ask PriceSnifferBot to stop visiting your domain
title: "Stop crawling: <your domain>"
labels: stop-request
---

**Domain:** <!-- for example shop.example -->

**Anything else we should know (optional):**

The fastest way to block the bot is `robots.txt`:

```
User-agent: PriceSnifferBot
Disallow: /
```
