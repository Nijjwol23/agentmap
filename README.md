# AgentMap

> The open standard for agent-readable websites.  
> `agents.json` — like `robots.txt`, but for AI agents.

## The problem

Every AI agent that visits a website today crawls it blind.
40–50 page loads just to understand what a site does.
No standard. No declaration. Pure waste.

## The solution

A single file at `/.well-known/agents.json` that tells any 
AI agent exactly what a website can do — without crawling.

```json
{
  "agentmap": "1.0",
  "site": { "name": "Acme Store", "type": "ecommerce" },
  "capabilities": [
    {
      "id": "search_products",
      "intent": "find products by query or category",
      "action": "GET /api/search",
      "input": { "q": "string", "category": "string?" },
      "output": { "items": "Product[]" },
      "auth": "none"
    }
  ]
}
```

## Relationship to A2A

AgentMap is the **web layer** of the Agent2Agent ecosystem.

| Protocol | Solves |
|----------|--------|
| MCP (Anthropic) | Agent ↔ Tools |
| A2A (Google / Linux Foundation) | Agent ↔ Agent |
| AgentMap | Agent ↔ Website |

`agents.json` is a valid A2A AgentCard profile — any A2A 
client can read it without modification.

## Install in 30 seconds

```bash
npx agentmap@latest init
```

Or add one DNS record. Or paste one script tag.  
[See install options →](docs/install.md)

## Status

- [x] Spec v0.1 draft
- [ ] Reference validator
- [ ] CLI generator
- [ ] WordPress plugin
- [ ] Next.js middleware

## Contributing

This is an open standard. PRs, issues, and discussion welcome.  
See [CONTRIBUTING.md](CONTRIBUTING.md)

## License

Apache 2.0 — same as A2A.
