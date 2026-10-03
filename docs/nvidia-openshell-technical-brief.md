# AgentNOMOS × NVIDIA OpenShell

## External authority, governed runtime execution & verifiable evidence

**Technical brief — 2026-10-03**

### One-line architecture

> **AgentNOMOS decides whether an action may run. OpenShell enforces the runtime boundary. AgentNOMOS binds what actually happened into verifiable evidence.**

---

## 1. Why this integration exists

Autonomous agents need more than an execution sandbox.

A secure runtime can constrain what software may do, but an enterprise control plane still needs to answer:

- Who authorized the action?
- Under which policy?
- Was the authority one-shot or replayable?
- What actually executed?
- What runtime state resulted?
- Can the result be bound to a durable evidence chain?
- Can the public claim remain narrower than the underlying implementation?

AgentNOMOS and OpenShell address different parts of that problem.

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

The integration therefore does not replace OpenShell's enforcement model. It places a verifiable external authority and evidence layer around a scoped OpenShell runtime execution.

---

## 2. What is live today

AgentNOMOS has completed and frozen a real OpenShell execution lineage and published it under **S7 — Execution / Delivery** in the live machine-readable Trust Chain.

The current implementation records:

- a scoped `execution_boundary` profile under S7;
- AgentNOMOS as authority owner;
- OpenShell as runtime-enforcement owner;
- AgentNOMOS as evidence-binding owner;
- one-shot authority;
- replay disabled;
- a separate post-execution verification pass;
- cryptographic bindings to the frozen execution evidence;
- explicit negative claims preventing overstatement.

The OpenShell evidence applies only to the frozen **R1_4I** lineage. It is **not** represented as proof that AgentNOMOS's current paid production-route cohort already executes through OpenShell.

### Verification result

- live/public validator: **166/166**
- offline validator: **144/144**
- guards: **55/55**
- S8 assurance: **35/35**
- S8 mutation suite: **18/18**
- human ↔ machine consistency: **40/40**
- OpenShell freeze bindings: **6/6**
- final verification failures: **0**

Current public manifest SHA-256:

`2499cd3d1ecd0baf05d7ae20d427347cab2109f59c6e5cdadfe01565b826e2d8`

Trust Chain S7 final checkpoint anchor:

`d71f0a48951459a862a7bc885b6bf655f068f7c8378e6f348f75bc445a5c4d1e`

---

## 3. Claim boundary

The global AgentNOMOS public claim ceiling remains:

`EXECUTION_BOUND_PROOF`

The OpenShell-specific scoped evidence class is:

`SOFTWARE_ATTESTED_MEDIATED_RUNTIME_ACTION_AND_EFFECT_BINDING`

The integration does **not** claim:

- TPM or TEE attestation;
- measured boot;
- host-independent trust;
- root-adversarial enforcement;
- that every production execution is OpenShell-mediated;
- NVIDIA certification;
- NVIDIA endorsement;
- NVIDIA partnership.

This deliberate claim ceiling is part of the design: evidence should support exactly the public statement being made, not a stronger one.

---

## 4. Why this may be useful to OpenShell

The integration demonstrates one possible boundary between an external governance plane and OpenShell:

1. an external system represents intent and evaluates policy;
2. a bounded authority is issued;
3. OpenShell enforces the runtime boundary;
4. observed execution and resulting state are captured;
5. an external evidence layer binds the execution to authority, policy and outcome;
6. the evidence is exposed through machine-readable and human-readable Trust Chain surfaces.

Potential design discussion areas include:

- external authority inputs;
- bounded or one-shot execution grants;
- evidence export from governed runtime actions;
- stable execution identifiers;
- runtime-event / effect binding;
- lifecycle hooks for receipt generation;
- portable governance-evidence bundles.

AgentNOMOS is not proposing that OpenShell adopt the AgentNOMOS data model. The question is narrower: **is this integration pattern useful as reference integration material, community documentation or design input for future evidence/attestation interfaces?**

---

## 5. Public verification surfaces

- AgentNOMOS: https://agentnomos.com
- Machine-readable Trust Chain:  
  https://agentnomos.com/.well-known/nomos-capabilities.json
- Reproducibility metadata:  
  https://agentnomos.com/.well-known/nomos-reproducibility.json
- Human verification page:  
  https://agentnomos.com/verify.html
- Detailed OpenShell boundary note:  
  [openshell-execution-boundary.md](openshell-execution-boundary.md)

---

## 6. Requested review

We would value review from OpenShell maintainers on three questions:

1. Is the **external authority → governed runtime → external evidence binding** split architecturally useful?
2. Which OpenShell lifecycle or evidence surfaces would make this pattern cleaner and more portable?
3. Would a minimal reference integration or community example be useful to the OpenShell ecosystem?

The implementation is already live and scoped conservatively. The next step is not a broader claim; it is technical review.
