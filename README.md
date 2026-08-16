# fingers

Ask what you can't be sure of. fingers tells you what's actually true about a token, NFT, wallet, contract, or tokenized stock before you act on it.

fingers is read-only and non-custodial. It never asks for your keys or seed phrase, and you can ask about anything without connecting a wallet. The tool that cannot act cannot be the one that drains you.

> **Remote MCP server. Nothing to install.**
> ```
> https://fingersai.co/mcp
> ```

## Add it in 30 seconds

```bash
# Claude Code
claude mcp add --transport http fingers https://fingersai.co/mcp
```

Cursor, VS Code, Claude Desktop, Cline, and raw MCP are all in [INSTALL.md](./INSTALL.md), including one-click "Add to Cursor" and "Add to VS Code" buttons.

## What we check

- **Honeypot and sellability.** Whether you can actually sell it, what the tax is, whether transfers can be paused or your wallet blacklisted.
- **Tokenized stocks.** Whether on-chain NVDA or AAPL is tracking the real share, trading at a premium or a discount, or is a copycat wearing the ticker.
- **Copycats.** Whether this is the real token or one of the many fakes sharing its name.
- **Authenticity.** Whether a site or token is the official one or a phishing lookalike.
- **NFT contents.** The assets held inside an ERC-6551 NFT, so its worth is the floor plus what sits in its wallet.
- **Wallets and transactions.** Whether an agent should pay or interact with an address, and what a transaction will actually do to your funds.

One `verify` call covers the general case. Every check is also its own tool, so an agent can call the exact one it needs and get a structured answer back.

## Robinhood Chain

fingers has the deepest coverage anywhere on Robinhood Chain. It is a top-five chain by volume and the least tracked one. We read honeypots, the tokenized-stock peg, copycats, live launches, NFT safety, and what is held inside a broker NFT. The mainstream scanners cover none of it yet.

## Every flag names its source

fingers reconciles live sources into one answer and shows its work. When it says honeypot, it tells you GoPlus said so. When it says one wallet holds most of the supply, it tells you the chain said so. On a chain full of fake scanners, the tool you can trust is the one that can't touch your funds and shows you where every claim came from.

## Also reachable as

- A2A Agent Card at `/.well-known/agent-card.json`
- REST at `POST /ask`
- ERC-8004 registration at `/.well-known/agent-registration.json`

## Links

- Website: https://fingersai.co
- MCP endpoint: https://fingersai.co/mcp

This repo is the front door. The engine is closed on purpose. Read-only is the security model, and you can't tamper with what you can't see.
