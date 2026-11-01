# PriceSnifferBot

PriceSnifferBot is a small, personal crawler. One person runs it for private use.
It is not a commercial service. It does not resell or publish your data.

## What it does
- It reads public product pages from online shops in the United States.
- It reads the product name, price, currency, condition and availability.
- It uses structured data on the page (JSON-LD, microdata, Open Graph) and your sitemaps.
- It does not log in, add items to a cart, place orders or submit forms.

## How it behaves
- It obeys `robots.txt` (RFC 9309), including `Crawl-delay`.
- It sends at most 1 request to your site at a time.
- It waits at least 5 seconds between requests to your site, or longer if your `Crawl-delay` says so.
- It fetches at most 20 pages and 100 requests per site per day. This count includes `robots.txt`,
  sitemaps and redirects.
- It slows down on HTTP 429 and 503 and honors `Retry-After`.
- If it cannot read your `robots.txt` (server error, timeout), it does not crawl your site in that run.
- It stops when it sees a CAPTCHA or bot check. It never tries to bypass one.
- It uses GET requests only. It does not use proxies and does not hide its identity.

## How it identifies itself
User-Agent: `PriceSnifferBot/0.1 (+https://github.com/AlehKhvasko/pricesniffer-bot)`

## How to block it
Add this to your `robots.txt`:

```
User-agent: PriceSnifferBot
Disallow: /
```

The bot reads `robots.txt` again before it crawls your site. After that it does not fetch your pages.

## Contact
To ask a question or to ask the bot to stop:
[open an issue](https://github.com/AlehKhvasko/pricesniffer-bot/issues/new/choose).
Please name your domain. Requests to stop are handled first.
