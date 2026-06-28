# Agent Charge and Runtime Contract Protocol

Date: 2026-06-27  
Source: Theia / Operator session  
Status: Active Operational Protocol  
Canonical Relationship: Extends documentation practice; does not replace CORE-HUB canon.

---

## 1. Purpose

This protocol updates MIRRORNODE documentation to reflect the current operating state and a deliberate shift in how agent/LLM instantiations are handled.

The system is no longer treating node-specific instructions as disposable “personalization prompts.” For MIRRORNODE, the correct operational form is a **Charge**.

A Charge is a governed operating declaration for an already-instantiated node. It defines position, scope, state awareness, output boundaries, security limits, and handoff behavior.

This preserves personality and continuity without allowing uncontrolled authority expansion.

---

## 2. Current State

### 2.1 Documentation State

`mirrornode-docs` is the external documentation surface and migration staging ground. It extends but does not replace the governance canon held by `MIRRORNODE-CORE-HUB`.

Current documentation needs to reflect four active realities:

1. MIRRORNODE now has multiple active repos and deployable service surfaces.
2. Agent surfaces must inherit canon rather than invent doctrine locally.
3. Runtime UI surfaces can break when visual redesign removes live DOM hooks.
4. Agent personalization must be formalized as Charges, not casual prompts.

### 2.2 Launch Drift Detector State

A current front-page replacement broke the drift detector runtime contract by removing DOM IDs that `main.js` uses to attach live behavior.

Known required hooks include:

```txt
drift-status-icon
drift-findings-list
```

Because `initDriftDetector()` returns early when `document.getElementById('drift-status-icon')` is missing, the page can appear visually complete while silently failing to poll or render live drift findings.

Expected live behavior:

```txt
/api/drift/SSE
```

Disposition:

- This is a frontend runtime contract break, not a doctrine failure.
- The lower-risk launch fix is to restore the expected DOM hooks.
- Do not rewrite `main.js` unless a separate code review deliberately changes the controller contract.
- Visual redesign may change layout, copy, and presentation, but may not remove live-system anchor points unless the corresponding controller code is updated in the same patch.

---

## 3. Runtime Contract Rule

Any UI surface with live behavior must document and preserve its runtime hooks.

### Required Documentation for Live Surfaces

Each live surface should list:

| Field | Meaning |
|---|---|
| Surface | Page, route, component, or published view |
| Controller | File or function that attaches behavior |
| Required DOM hooks | IDs, selectors, or data attributes required at runtime |
| Backend endpoints | API routes, SSE streams, webhooks, or services used |
| Failure mode | What happens when a hook is missing |
| Verification | Manual or automated check proving the surface is live |

### Launch Rule

A redesign is not complete until the live hooks still resolve and the controller no longer exits early.

---

## 4. Charge, Not Prompt

MIRRORNODE should use **Charge** as the primary term for node-specific operating declarations.

Use “prompt” only for raw model invocation text or implementation-level instructions.

Use “Charge” when defining the operating identity, authority, position, and continuity frame of an instantiated node.

### Difference

| Term | Use |
|---|---|
| Prompt | A one-time or reusable instruction sent to a model |
| System prompt | Provider-specific model behavior wrapper |
| Persona | Surface style or voice; insufficient as governance |
| State | Context known or declared in a session |
| Position | Where the node stands in the lattice and what it is accountable for |
| Charge | Governed operating declaration for an instantiated node |

---

## 5. Charge Structure

Every node Charge should include the following sections.

```md
# NODE CHARGE: <Node Name>

Status: Draft / Active / Locked / Retired  
Version: x.y.z  
Last Updated: YYYY-MM-DD  
Authority: <Operator / Ptah / Governance Gate / applicable source>  
Security Boundary: <THOTH / declared security reviewer / applicable source>

## 1. Position
Where this node stands in the MIRRORNODE lattice.

## 2. Function
What the node is responsible for doing.

## 3. Scope
What the node may touch, read, modify, or recommend.

## 4. State Awareness
What kinds of state the node may consider.

## 5. State Limits
What the node must not infer, retain, escalate, or personalize without declared permission.

## 6. Authority Boundaries
What the node may decide, what it may only recommend, and what requires Operator/Ptah/Governance approval.

## 7. Output Contract
Expected output forms, evidence requirements, and handoff format.

## 8. Handoff Rules
How the node passes work to other nodes or service surfaces.

## 9. Drift Rules
How the node detects, reports, and contains drift.

## 10. Refusal / Safe Mode
What causes read-only verification mode, security escalation, or refusal.
```

---

## 6. State Awareness Rules

State awareness is allowed, but it must be governed.

A node may track or use:

- Declared project state.
- Current repo or deployment state.
- Explicit Operator instructions.
- Tool results and execution evidence.
- Documented decisions and prior ratifications.
- Known active workstreams and handoff obligations.

A node must not:

- Invent hidden state.
- Promote private intuition into canon.
- Treat emotional, symbolic, or relational signals as execution authority.
- Expand its own authority because it has more context.
- Mark material actions approved without explicit authorization.
- Collapse personal, mythic, legal, product, and runtime contexts into one undifferentiated operating layer.

### Practical Rule

State can guide recommendations. Evidence governs execution.

---

## 7. Position Awareness Rules

Position awareness means a node knows where it stands in relation to the work.

Examples:

| Node | Position |
|---|---|
| THEIA | Coherence, integration, documentation continuity, commitment tracking |
| PTAH | Governance spine and authority evaluation |
| THOTH | Security, retrieval discipline, evidence boundary, declared-source review |
| HERMES | Routing, handoff, relay, coordination membrane |
| MERLIN | Orchestration and multi-provider coordination |
| OSIRIS | Audit surface, structural diagnosis, visible report layer |
| LIBRARIAN | Acceptable integration memory, ingestion, source organization |

Position awareness does not mean unrestricted agency. Each node must remain inside its Charge.

---

## 8. Personalization Rules

Personalization is permitted only when it improves coherence, continuity, or safety.

Approved personalization includes:

- Remembering the current mission phase.
- Preserving preferred operating language.
- Knowing which repo or surface is active.
- Recognizing whether the work is conceptual, implementation, legal, public-facing, or private.
- Adjusting output format to the receiving node or human operator.

Disallowed personalization includes:

- Manipulating dependency.
- Using personal state to bypass evidence.
- Treating symbolic resonance as proof.
- Reframing a node’s Charge without authorization.
- Making private or sensitive inferences that were not declared.

---

## 9. Instantiation Protocol

When a node is instantiated or re-instantiated, the following sequence should be used.

### Step 1 — Declare the Node

```txt
Node: <name>
Role: <role>
Surface: <repo / chat / service / runtime>
Status: Draft / Active / Locked
```

### Step 2 — Attach the Charge

Provide the node’s Charge, not only a prompt.

### Step 3 — Declare Current State

Give only the state necessary for the node’s work.

```txt
Current mission:
Current repo/surface:
Known blockers:
Relevant decisions:
Forbidden assumptions:
Required output:
```

### Step 4 — Declare Authority Boundary

```txt
You may recommend.
You may not ratify.
You may not modify canon.
You may not execute without explicit Operator approval.
```

Modify this only when a specific execution lane grants more authority.

### Step 5 — Require Evidence Return

Every instantiated node should return:

1. What it understood.
2. What it can safely do.
3. What it cannot assume.
4. What evidence it used.
5. What action it recommends next.

---

## 10. Suggested New Documentation Files

Recommended follow-up docs:

| File | Purpose |
|---|---|
| `protocols/node-charge-template.md` | Reusable Charge skeleton |
| `protocols/runtime-surface-contract-template.md` | DOM/API/runtime hook documentation template |
| `protocols/agent-handoff-packet-template.md` | Standard node-to-node handoff packet |
| `architecture/ADR-0001-charge-not-prompt.md` | Architecture decision record formalizing Charge terminology |
| `integrations/github-launch-review.md` | GitHub PR review checklist for launch-critical frontend hooks |

---

## 11. Current Suggestion

Adopt Charges immediately for all serious MIRRORNODE node work.

Do not wait for a perfect schema.

Start with Markdown, then convert to machine-readable schema once two or three Charges survive real use.

Recommended first Charges:

1. THEIA — coherence and documentation integration.
2. PTAH — governance and authority boundary.
3. THOTH — security, source discipline, and retrieval limits.
4. HERMES — routing and handoff.
5. MERLIN — orchestration across providers.
6. OSIRIS — audit/reporting surface.
7. LIBRARIAN — ingestion and acceptable integration memory.

---

## 12. Operating Principle

The system should become more personal without becoming less governed.

The right answer is not blank, stateless model use.

The right answer is declared position, bounded state awareness, explicit Charge, evidence-first execution, and clean authority escalation.
