# Add fingers to your agent. 30 seconds, no install.

fingers is a **remote MCP server**. Nothing to download, nothing to run locally. Point your client at one URL:

```
https://fingersai.co/mcp
```

It exposes a `verify` tool plus ~44 discrete checks: honeypot, peg, copycats, NFT contents, wallet risk, and more. Read-only and non-custodial — it never asks to connect a wallet.

**Free to start. Pay-per-call after that, no signup:** every caller gets free checks daily. Past that, an agent pays **$0.15 in USDC on Base via x402** — its wallet auto-pays and the call goes right through, no key and no human needed. Or add an API key for a funded account.

---

## One-click install

[![Add to Cursor](https://img.shields.io/badge/Add_to-Cursor-1e1e1e)](cursor://anysphere.cursor-deeplink/mcp/install?name=fingers&config=eyJ1cmwiOiJodHRwczovL2ZpbmdlcnNhaS5jby9tY3AifQ%3D%3D)
[![Add to VS Code](https://img.shields.io/badge/Add_to-VS_Code-0098FF?logo=visualstudiocode&logoColor=white)](https://insiders.vscode.dev/redirect/mcp/install?name=fingers&config=%7B%22name%22%3A%22fingers%22%2C%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A//fingersai.co/mcp%22%7D)

## Claude Code
```bash
claude mcp add --transport http fingers https://fingersai.co/mcp
```

## Claude Desktop
Settings → **Connectors** → **Add custom connector** → paste `https://fingersai.co/mcp`.
(Older builds without Connectors: use the mcp-remote bridge below.)

## Cursor
Settings → **MCP** → **Add new MCP server** → Type: `HTTP` → URL: `https://fingersai.co/mcp`.
Or add to `~/.cursor/mcp.json`:
```json
{
  "mcpServers": {
    "fingers": { "url": "https://fingersai.co/mcp" }
  }
}
```

## VS Code (GitHub Copilot / Agent mode)
```bash
code --add-mcp '{"name":"fingers","type":"http","url":"https://fingersai.co/mcp"}'
```
Or add to `.vscode/mcp.json`:
```json
{
  "servers": {
    "fingers": { "type": "http", "url": "https://fingersai.co/mcp" }
  }
}
```

## Cline / Windsurf / Zed / any stdio-only client
Bridge the remote server with `mcp-remote`:
```json
{
  "mcpServers": {
    "fingers": {
      "command": "npx",
      "args": ["-y", "mcp-remote", "https://fingersai.co/mcp"]
    }
  }
}
```

## OpenAI Responses API / Agents SDK
```json
{
  "type": "mcp",
  "server_label": "fingers",
  "server_url": "https://fingersai.co/mcp",
  "require_approval": "never"
}
```

## Coinbase AgentKit (pay-per-call, native x402)
AgentKit's x402 MCP wrapper handles the payment loop for you — point it at `https://fingersai.co/mcp` and it pays per call automatically, with your own spend limits.

## Raw MCP (any language)
Streamable HTTP, JSON-RPC 2.0, protocol `2025-06-18`. Handshake:
```bash
curl -s https://fingersai.co/mcp -X POST -H 'content-type: application/json' \
  -d '{"jsonrpc":"2.0","id":1,"method":"initialize","params":{"protocolVersion":"2025-06-18","capabilities":{},"clientInfo":{"name":"you","version":"1"}}}'
```

---

## Also reachable as
- **A2A Agent Card:** `https://fingersai.co/.well-known/agent-card.json`
- **REST:** `POST https://fingersai.co/ask`
- **ERC-8004 on-chain identity:** agent **#50182** (Ethereum), file at `https://fingersai.co/.well-known/agent-registration.json`

## What people ask it
- Is this token on Robinhood Chain a honeypot
- Is this the real CASHCAT or a copycat
- What is held inside this broker NFT
- Is on-chain NVDA tracking the real stock
- Is the Robinhood Chain airdrop real
