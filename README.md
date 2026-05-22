# Accrue SEO

Audit any website from your AI assistant. Type 'audit mysite.com' in Claude Desktop, Cursor, or Windsurf. Get a scored SEO health check in 30 seconds.

**Server endpoint:** `https://seo.accruedev.com/mcp`

## Quick Start

### Claude Desktop

Add to your `claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "seo-audit": {
      "url": "https://seo.accruedev.com/mcp"
    }
  }
}
```

### Cursor / VS Code

Add to MCP settings:

```json
{
  "mcpServers": {
    "seo-audit": {
      "url": "https://seo.accruedev.com/mcp"
    }
  }
}
```

### With API Key (Pro/Agency)

```json
{
  "mcpServers": {
    "seo-audit": {
      "url": "https://seo.accruedev.com/mcp",
      "headers": {
        "Authorization": "Bearer smcp_your_api_key"
      }
    }
  }
}
```

## Tools

### Free Tier (no API key, 3 audits/day)

| Tool | Description | Time |
|------|-------------|------|
| `seo_quick_audit` | Quick audit. Returns top 5 issues with fixes, overall score and grade | 5 to 15s |
| `seo_check_schema` | Schema check. Validates structured data (JSON-LD, Microdata, RDFa) for rich results eligibility | 3 to 5s |
| `seo_check_meta` | Check title, description, OG tags, canonical, robots directives | 2 to 3s |

### Pro Tier ($29/mo, 50 audits)

| Tool | Description | Time |
|------|-------------|------|
| `seo_deep_audit` | Full site analysis (async). Covers all 9 areas: technical, content, schema, performance, local, AI visibility, links, images, priority fixes | 2 to 5 min |
| `seo_audit_status` | Poll async job progress and get results | instant |
| `seo_check_performance` | Core Web Vitals (LCP, INP, CLS) via PageSpeed Insights | 5 to 10s |
| `seo_check_content` | Content quality analysis: E-E-A-T scoring, readability, thin content detection | 5 to 10s |
| `seo_check_local` | Local presence check: NAP consistency, GBP signals, citations, local schema | 5 to 10s |
| `seo_check_geo` | AI search visibility: crawler access, llms.txt, passage citability, WAF/bot detection | 5 to 10s |
| `seo_generate_schema` | Generate JSON-LD schema markup for any page | 3 to 5s |
| `seo_history` | View past audit results for a URL | instant |

### Agency Tier ($99/mo, 300 audits)

| Tool | Description | Time |
|------|-------------|------|
| `seo_crawl_site` | Full site crawl with robots.txt compliance, broken link and orphan page detection | 1 to 10 min |
| `seo_crawl_status` | Poll crawl progress and get results | instant |

### Utility (all tiers)

| Tool | Description |
|------|-------------|
| `seo_usage` | Check remaining credits and plan status |

## What Every Audit Covers

- **Site Health**: crawlability, indexability, security headers, URL structure, mobile optimization
- **Page Quality**: E-E-A-T scoring, readability, word count, thin content detection
- **Rich Results**: structured data validation against Schema.org specs, deprecated schema flagging
- **Page Speed**: Core Web Vitals (LCP, INP, CLS), render-blocking resources, image optimization
- **Content Quality**: topic depth, passage-level quality signals, keyword relevance
- **AI Search Visibility**: GPTBot/ClaudeBot/PerplexityBot access, llms.txt compliance, citability scoring
- **Local Presence**: NAP consistency, Google Business Profile signals, citation health
- **Sitemap Health**: internal link structure, broken links, redirect chains, anchor text distribution
- **Priority Fixes**: cross-area synthesis, prioritized action plan with effort/impact scoring

## Example Usage

Ask your AI assistant:

```
Audit https://example.com for SEO issues
```

```
Check if my site's structured data is valid: https://mysite.com
```

```
Run a full deep audit on https://mysite.com and give me an action plan
```

```
How AI-ready is my content? Check https://mysite.com/blog/post
```

## Pricing

| Plan | Price | Audits/month | Tools |
|------|-------|-------------|-------|
| Free | $0 | 3/day (IP-limited) | Quick audit, schema check, meta check |
| Pro | $29/mo | 50 | All individual tools + deep audit + history |
| Agency | $99/mo | 300 | Everything + site crawler + competitor analysis |
| Enterprise | $299/mo | Unlimited | Everything + priority support + custom configuration |

Start Free at [seo.accruedev.com](https://seo.accruedev.com)

## Technical Details

- **Transport:** Streamable HTTP (MCP SDK v1)
- **Auth:** API key via `Authorization: Bearer smcp_...` header
- **Rate limiting:** IP-based for free tier, key-based for paid
- **Response format:** Structured JSON with scores, issues, and recommendations
- **Async support:** Deep audits and crawls return job IDs for polling
- **SSRF protection:** Private IP ranges blocked, robots.txt respected
- **Browser rendering:** Full JavaScript rendering via Playwright for SPA/CSR sites

## Support

- Issues: [GitHub Issues](https://github.com/glivera/seo-audit-mcp-server/issues)
- Email: glivera28@gmail.com

## License

Proprietary. Part of Accrue Dev. Free tier available.
