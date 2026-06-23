<h1 align="center">AgentNOMOS</h1>

<p align="center">
  <strong>The governance layer for autonomous AI agents.</strong><br>
  Verification. Risk gates. Replayable decisions. Evidence-ready approvals.
</p>

<p align="center">
  <a href="https://agentnomos.com">Website</a> ·
  <a href="https://clawhub.ai/AgentNOMOS/agentnomos-governance-preflight">ClawHub Skill</a> ·
  <a href="https://github.com/AgentNOMOS/nomos-demo">Governance Kit</a> ·
  <a href="https://agentnomos.network">Network</a>
</p>

---

## What is AgentNOMOS?

AgentNOMOS is the governance and verification layer around autonomous AI-agent systems.

> **Should this agent action be allowed, held for review, or blocked — and can the decision be reconstructed later?**

NOMOS is not another chatbot or agent framework. It evaluates identity, authority, scope, risk, human-review requirements and evidence readiness before a consequential action.

## Install the public OpenClaw skill

```bash
openclaw skills install @agentnomos/agentnomos-governance-preflight
```

The current public skill is read-only and advisory. It never executes the proposed action.

## Why it matters

AI agents are moving from text generation to actions with external effects. AgentNOMOS focuses on the missing layer:

**Governance before action.**

- Who is acting?
- What authority exists for this exact action?
- Is the proposed scope bounded?
- What risk and human review are required?
- What evidence must remain afterward?

## Public decision states

- `ADVISORY_ALLOW` — narrow, low-risk action satisfies the public preflight contract
- `HOLD_FOR_REVIEW` — authority, approval, scope, evidence or risk requires review
- `BLOCK` — explicit policy conflict, secret exposure, safeguard bypass or unauthorized action

Every public result preserves:

```json
{"not_executed": true}
```

`ADVISORY_ALLOW` is not production authorization.

## Public capability boundary

The public AgentNOMOS surfaces are advisory and read-only.

Not publicly enabled:

- autonomous execution
- production deployment
- wallet signing
- payment settlement as execution authority
- destructive mutation
- Phase 8 execution

> **Payment is not permission.**

## Optional MCP discovery

The ToolOracle-hosted NOMOS MCP surface is an external, optional discovery endpoint and is not a hard dependency of the public Governance Kit:

```json
{
  "mcpServers": {
    "agentnomos": {
      "type": "streamable-http",
      "url": "https://tooloracle.io/mcp/nomos"
    }
  }
}
```

Its current public capability families are advisory preflight, scan, discovery, x402 quote and receipt verification. They do not execute payments or consequential actions.

## Design principles

1. Governance before execution
2. Evidence before trust
3. Receipts before claims
4. Replayability before hype
5. Fail-closed by default

---

Website: https://agentnomos.com
