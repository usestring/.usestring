<h1 align="center">String</h1>

<p align="center"><strong>Web access for everyone.</strong></p>

<p align="center">
  We build the web data API that doesn't get blocked — one request, any URL, clean content back.
</p>

<p align="center">
  <a href="https://www.usestring.ai">Website</a> ·
  <a href="https://portal.usestring.ai/docs">Docs</a> ·
  <a href="https://portal.usestring.ai/sign-up">Get an API key</a> ·
  <a href="https://www.usestring.ai/blog">Blog</a> ·
  <a href="https://www.usestring.ai/careers">Careers</a>
</p>

---

## The API

Anti-bot handling, CAPTCHA solving, proxy rotation, and JS rendering are our problem, not yours.
Send a URL, get the content back. A block costs you nothing — you're billed only when content is
successfully delivered, and the first 5,000 requests are free.

```bash
curl https://request.usestring.ai/v1/fetch \
  -H "Authorization: Bearer $STRING_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{ "url": "https://example.com", "format": "markdown" }'
```

Agents can skip the HTTP layer entirely — [`@usestring/mcp`](https://github.com/usestring/string-ai-mcp)
is the official MCP server, local or hosted:

```bash
npx @usestring/mcp    # local; STRING_AI_API_KEY in the environment
```

...or point any MCP client at `https://mcp.usestring.ai/YOUR_API_KEY/v1/mcp`.

## What we've open sourced

|  |  |
| --- | --- |
| **[web-data-frontier-benchmark](https://github.com/usestring/web-data-frontier-benchmark)**<br>`TypeScript` | An open, reproducible benchmark for web access APIs: 90 real bot-protected URLs, 15 providers, one shared harness. We built it because [vendor success-rate claims don't survive a fixed test suite](https://www.usestring.ai/blog/web-scraping-benchmark-problem) — ours included, which is why the harness, the URL list, and the raw JSON are all public. |
| **[powhttp-mcp](https://github.com/usestring/powhttp-mcp)**<br>`Go` · `AGPL-3.0` | X-ray vision into captured HTTP traffic for coding agents: TLS (JA3/JA4) and HTTP/2 fingerprinting, browser-vs-program diffing to locate detection vectors, API and GraphQL endpoint mapping, and response-schema inference. |
| **[string-ai-mcp](https://github.com/usestring/string-ai-mcp)**<br>`JavaScript` · `MIT` | The official MCP server for the Web Access API — `web_access_fetch`, `web_access_search`, and quote-then-approve sitemap crawls, in any MCP client. |
| **[utils](https://github.com/usestring/utils)**<br>`Shell` · `MIT` | The scripts and gists we reference in our writing. |
| **[relay-self-hosted](https://github.com/usestring/relay-self-hosted)**<br>`JavaScript` | Fully self-hosted Obsidian live collaboration — CRDT sync, token service, and OAuth, with no relay.md control plane. |

## The benchmark

Official run — **2026-07-15** · 90 targets × 5 attempts × 15 providers = 6,750 requests.

| Rank | Provider | Success rate | Passed |
| ---: | --- | ---: | ---: |
| 1 | **string** | **95.8%** | 431/450 |
| 2 | scrapfly | 83.6% | 376/450 |
| 3 | bright | 80.9% | 364/450 |
| 4 | context_dev | 78.7% | 354/450 |
| 5 | firecrawl | 70.9% | 319/450 |

[Full table, all fifteen providers, and instructions to re-run it yourself →](https://github.com/usestring/web-data-frontier-benchmark)

---

<p align="center">
  Built in New York City. &nbsp;·&nbsp; <a href="https://www.usestring.ai/careers">We're hiring.</a>
</p>
