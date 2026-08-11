<h1 align="center">AgentNOMOS</h1>

<p align="center">
  <strong>The governance layer for autonomous AI agents.</strong><br>
  Verification. Receipts. Risk gates. Replayable decisions. Controlled execution.
</p>

<p align="center">
  <a href="https://agentnomos.com">Website</a> ·
  <a href="https://agentnomos.network">Network</a> ·
  <a href="https://smithery.ai/servers/contact-xskl/nomos-crossborder-broker">MCP on Smithery</a>
</p>

---

## What is AgentNOMOS?

AgentNOMOS is the governance and verification layer for autonomous AI agents.

> **Should this agent action be allowed, blocked, or recorded — and can the decision be proven later?**

NOMOS is not another chatbot or agent framework. It is the control layer *around* agentic systems.

---

## Why It Matters

AI agents are moving from text generation to real actions. AgentNOMOS focuses on the missing layer:

**Governance before action.**

- *Should it do it?*
- *What evidence supports it?*
- *Who authorized it?*
- *Can the decision be replayed?*

---

## Live paid capability — verify it yourself

Since 2026-08-10 one paid capability is live end-to-end:

- `POST https://tooloracle.io/v2/nomos_full_chain_verification` — $0.001 USDC via x402, settled on Base Mainnet (`eip155:8453`)
- Every execution is bound from represented intent through authorization to an **Ed25519-signed receipt** and outcome
- **Free offline verification** — no wallet needed: reference evidence (a real production ALLOW and a real production DENY) plus a stateless 21-check verifier are published at [agentnomos.com/proof/full-chain](https://agentnomos.com/proof/full-chain/verify.md), indexed at [`/.well-known/nomos-reproducibility.json`](https://agentnomos.com/.well-known/nomos-reproducibility.json)

Boundary, stated plainly: NOMOS proves continuity from the represented intent onward. It does not prove that the represented intent was the correct interpretation of the human's underlying meaning.

---

## MCP Server

```json
{
  "mcpServers": {
    "nomos-broker": {
      "type": "streamable-http",
      "url": "https://tooloracle.io/mcp/nomos"
    }
  }
}
```

[![smithery badge](https://smithery.ai/badge/contact-xskl/nomos-crossborder-broker)](https://smithery.ai/servers/contact-xskl/nomos-crossborder-broker)

---

## Design Principles

1. Governance before execution
2. Evidence before trust
3. Receipts before claims
4. Replayability before hype
5. Fail-closed by default

---

> Inbound x402 settlement is live on the one paid capability above. NOMOS holds **no autonomous outbound-wallet authority**: it never spends, signs or holds caller funds. The MCP surface is metadata only — payment happens exclusively on the x402 HTTP route.

Website: https://agentnomos.com
