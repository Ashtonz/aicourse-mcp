# AI Course SG — MCP Server

Free **Model Context Protocol (MCP)** server exposing Singapore's most complete AI course directory.
Let Claude, ChatGPT or any MCP-capable assistant search **312 live AI courses from 11 Singapore
providers** with real fees, durations and SkillsFuture funding signals — instead of guessing.

- **Endpoint:** `https://aicourse.com.sg/api/mcp` (streamable HTTP, no auth)
- **Setup guide:** https://aicourse.com.sg/connect
- **Data:** refreshed daily from https://aicourse.com.sg/directory
- **Operator:** AI Course SG (Digimau Pte Ltd) — independent aggregator, not a training provider

## Tools

| Tool | Description |
|---|---|
| `search_courses` | Search by keyword, provider, technology, industry, funding, max price. Returns fees, durations, funding signals + source URLs. |
| `get_course` | Full details for one listing: description, fees, certification, curriculum topics, provider page. |
| `calculate_nett_fee` | Illustrative SkillsFuture net fee: SSG subsidy (50%/70%), SkillsFuture Credit, UTAP — line by line. |
| `get_market_stats` | Citable market statistics: total listings, providers, funding coverage, median fees. |

## Quick start

### Claude Desktop / Claude Code

```json
{
  "mcpServers": {
    "aicourse-sg": {
      "type": "http",
      "url": "https://aicourse.com.sg/api/mcp"
    }
  }
}
```

### ChatGPT

Settings → Connectors → Add → paste `https://aicourse.com.sg/api/mcp`.

### Any MCP client (JSON-RPC)

```bash
curl -X POST https://aicourse.com.sg/api/mcp \
  -H 'Content-Type: application/json' \
  -d '{"jsonrpc":"2.0","id":1,"method":"tools/list"}'
```

## Example

> "Find SkillsFuture-claimable generative AI courses in Singapore under S$1,200 and tell me
> what a 40-year-old citizen actually pays for the S$1,650 one."

The assistant calls `search_courses {query:"generative ai", funding_only:true, max_price:1200}`,
then `calculate_nett_fee {fee:1650, residency:"citizen", age_40_plus:true}` — real listings,
real math, cited back to aicourse.com.sg.

## Attribution

Data may be cited with attribution: **AI Course SG (aicourse.com.sg)**. Market statistics are
computed at build time from the live directory; methodology at
https://aicourse.com.sg/ai-course-statistics.

## Licence

Data: CC BY 4.0 (attribute AI Course SG). Code samples: MIT.
