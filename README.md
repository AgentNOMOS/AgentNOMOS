<h1 align="center">AgentNOMOS</h1>

<p align="center">
  <strong>The governance and evidence layer for autonomous AI agents.</strong><br>
  Intent. Policy. Authority. Controlled execution. Verifiable evidence. Receipts. Outcomes.
</p>

<p align="center">
  <a href="https://agentnomos.com">Website</a> ·
  <a href="https://agentnomos.network">Network</a> ·
  <a href="https://agentnomos.com/.well-known/nomos-capabilities.json">Machine-readable Trust Chain</a> ·
  <a href="https://smithery.ai/servers/contact-xskl/nomos-crossborder-broker">MCP on Smithery</a>
</p>

---

## What is AgentNOMOS?

AgentNOMOS is a governance, authorization and evidence layer around autonomous agent systems.

It answers a different question from an agent framework:

> **May this action run, under which authority and policy, and can the resulting execution be proven later?**

The core design principle is simple:

**Governance before action. Evidence before trust. Receipts before claims.**

---

## Trust Chain

The canonical machine model contains exactly **11 stages, S0–S10**. The public human-readable shorthand is:

**Discovery → Identity → Capability → Intent → Offer → Authorization → Execution → Proof → Outcome → Governance**

The current machine-readable manifest is published at:

`https://agentnomos.com/.well-known/nomos-capabilities.json`

Current public manifest SHA-256:

`2499cd3d1ecd0baf05d7ae20d427347cab2109f59c6e5cdadfe01565b826e2d8`

Global public claim ceiling:

`EXECUTION_BOUND_PROOF`

---

## NVIDIA OpenShell execution boundary

AgentNOMOS now publishes a scoped OpenShell execution-boundary profile under **S7 — Execution / Delivery**.

The responsibility split is:

```text
AgentNOMOS
Intent / Policy / Admission / Authority
        ↓
NVIDIA OpenShell
Runtime / Sandbox / Enforcement
        ↓
AgentNOMOS
Evidence Binding / Receipt / Outcome / Governance
```

In short:

> **AgentNOMOS decides whether an action may run.  
> OpenShell enforces the runtime boundary.  
> AgentNOMOS binds what actually happened into verifiable evidence.**

The current OpenShell evidence applies **only to the frozen AgentNOMOS OpenShell R1_4I lineage**. It is **not** a claim that the current paid production route cohort is mediated by OpenShell.

Verified post-deploy state:

- validator: **144/144 offline**
- validator: **166/166 live/public**
- guard suite: **55/55**
- S8 assurance: **35/35**
- S8 mutation suite: **18/18**
- human ↔ machine consistency: **40/40**
- OpenShell freeze bindings: **6/6**
- post-deploy verification failures: **0**

Technical detail:

- [OpenShell execution-boundary evidence](docs/openshell-execution-boundary.md)
- [NVIDIA OpenShell technical brief](docs/nvidia-openshell-technical-brief.md)

**Scope note:** NVIDIA OpenShell is referenced here as runtime technology used by the integration. This repository does not claim NVIDIA certification, endorsement or partnership.

---

## Live paid capability

A paid capability is live end-to-end:

- `POST https://tooloracle.io/v2/nomos_full_chain_verification`
- **$0.001 USDC via x402**
- Base Mainnet: `eip155:8453`
- execution is bound from represented intent through authorization to an **Ed25519-signed receipt** and outcome
- free offline verification is available without a wallet

Reference verification:

`https://agentnomos.com/proof/full-chain/verify.md`

Reproducibility index:

`https://agentnomos.com/.well-known/nomos-reproducibility.json`

Boundary, stated plainly: AgentNOMOS proves continuity from the represented intent onward. It does not prove that the represented intent was the correct interpretation of the human's underlying meaning.

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

## Design principles

1. Governance before execution
2. Evidence before trust
3. Receipts before claims
4. Replayability before hype
5. Fail-closed by default
6. Checked bytes must equal executed bytes
7. Authorization, execution and proof are separate facts

---

## Payment boundary

Inbound x402 settlement is live on the paid capability above.

AgentNOMOS does **not** imply that payment validity alone grants execution authority. Payment, authorization, execution and evidence remain separate stages of the control model.

---

Website: https://agentnomos.com
