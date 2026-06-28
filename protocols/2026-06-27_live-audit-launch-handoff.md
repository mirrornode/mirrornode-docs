# Live Audit Launch Handoff Packet

Date: 2026-06-27  
Source: Operator / THEIA session  
Status: Active Launch Packet  
Canonical Relationship: Operational documentation; promote to CORE-HUB only if ratified.  
Primary Surface: Osiris Audit v1 / MIRRORNODE public audit path

---

## 1. Objective

Prepare the live Audit path for launch verification using the active MIRRORNODE node Charges.

This packet does not declare launch complete. It defines the work needed to prove the path is live, safe, honest, and fulfillable.

Primary objective:

```txt
Verify that the Osiris Audit v1 path can accept a real buyer, collect usable intake, preserve runtime truth, protect evidence/security boundaries, and support manual fulfillment without overclaiming automation.
```

---

## 2. Current State

Known state at packet creation:

- `mirrornode-docs` now contains runtime surface and node Charge protocols.
- THEIA, THOTH, PTAH, HERMES, MERLIN, OSIRIS, and LIBRARIAN have active operational Charges.
- A runtime contract issue was identified on the front page / drift detector surface where expected DOM hooks were removed.
- Known hooks include `drift-status-icon` and `drift-findings-list`.
- Known live dependency: `/api/drift/SSE`.
- The Audit offer is Osiris Audit v1: a structural audit of an AI system, one pass, manually fulfilled, priced at $149 unless superseded by current product state.
- Checkout, intake, and fulfillment must be verified before launch claims are strengthened.

---

## 3. Authority Boundary

This packet may coordinate verification.

This packet may not:

- ratify canon,
- approve launch by itself,
- expose secrets,
- declare payment flow live without runtime evidence,
- declare audit fulfillment automated if manual fulfillment is still required,
- treat visual page render as integration proof.

Launch approval remains with the Operator through the declared authority path.

---

## 4. Node Assignments

### THEIA — Coherence / Integration

Task:

- Keep the launch verification sequence coherent.
- Convert findings into documentation updates or action packets.
- Track blockers and next actions.

Return:

```txt
Coherence status:
Docs updated:
Open blockers:
Next action:
```

---

### THOTH — Evidence / Security / Source Boundary

Task:

- Classify evidence state for each launch claim.
- Confirm no secret values enter docs, prompts, commits, or public outputs.
- Mark unknowns as read-only until verified.
- Separate intake, inference, verified runtime behavior, and ratified claims.

Return:

```txt
Evidence state:
Security state:
Risk:
Finding:
Safe next action:
Escalation:
```

---

### PTAH — Governance / Authority

Task:

- Determine whether launch language, docs, and runtime claims are draft, review-needed, or ratification-ready.
- Prevent self-ratification.
- Confirm who must approve launch claims.

Return:

```txt
Governance state:
Authority chain:
Decision required from:
Conflicts/blockers:
Ratification readiness:
Next action:
```

---

### HERMES — Routing / Relay

Task:

- Route each blocker to the correct surface: docs, platform, backend, Stripe, Supabase, or manual fulfillment.
- Preserve handoff packets with authority labels.

Return:

```txt
Route:
Reason:
Packet:
Authority boundary:
Expected return:
Blocker:
```

---

### MERLIN — Orchestration

Task:

- Decompose launch verification into executable lanes.
- Assign provider/model/tool work if needed.
- Compare outputs and identify conflicts.

Return:

```txt
Mission:
Lanes:
Assignments:
Expected returns:
Risks/conflicts:
Synthesis:
Escalation:
```

---

### OSIRIS — Audit / Visible Report Surface

Task:

- Verify the audit product promise is clear and fulfillable.
- Ensure findings/report language separates evidence, interpretation, and recommendation.
- Confirm public copy does not overclaim.

Return:

```txt
Surface/status:
Evidence state:
Findings:
Recommendations:
Risk/impact:
Delivery status:
Follow-up:
```

---

### LIBRARIAN — Ingestion / Integration Memory

Task:

- Track sources, templates, contracts, and integration records used during launch verification.
- Preserve what was checked and where.
- Mark integration status for payment, intake, runtime hooks, and fulfillment artifacts.

Return:

```txt
Item:
Source class:
Integration status:
Freshness:
Allowed use:
Constraints:
Next action:
```

---

## 5. Verification Lanes

### Lane 1 — Public Audit Page

Check:

- Page renders.
- Offer language is clear.
- Manual fulfillment is honest.
- CTA leads to the expected checkout or intake path.
- No unsupported claims are made.

Evidence required:

```txt
route checked
files checked
visible copy checked
CTA behavior checked
```

---

### Lane 2 — Checkout

Check:

- Checkout route exists.
- Stripe environment variable names are present where required.
- Price ID target is correct.
- Success/cancel behavior is understood.
- Buyer email capture is enabled or alternate intake link exists.

Evidence required:

```txt
route checked
request behavior checked
success/cancel path checked
no secret values exposed
```

---

### Lane 3 — Intake

Check:

- Buyer has a way to provide system/context information.
- Intake is associated with buyer identity or email.
- Intake does not require unsupported automation.
- Intake data handling is private and bounded.

Evidence required:

```txt
intake surface checked
identity linkage checked
privacy posture checked
manual fallback checked
```

---

### Lane 4 — Runtime Hooks / Drift Detector

Check:

- Required DOM hooks exist in final markup.
- `initDriftDetector()` or equivalent controller does not exit early.
- `/api/drift/SSE` behavior is verified or properly marked inactive.
- Static fallback copy is honest.

Known required hooks:

```txt
drift-status-icon
drift-findings-list
```

Evidence required:

```txt
hook search result
controller reference checked
network/data path checked
failure mode classified
```

---

### Lane 5 — Fulfillment

Check:

- Manual fulfillment process is defined.
- Audit output format exists.
- Delivery channel is known.
- Refund/test purchase path is understood.
- Operator can complete first paid audit without automation dependency.

Evidence required:

```txt
fulfillment template checked
delivery method checked
manual steps documented
first audit path rehearsed
```

---

### Lane 6 — Public Claim / Governance Review

Check:

- Public language does not overclaim.
- Internal mythic language remains internal unless intentionally surfaced.
- Draft docs are not described as canon.
- Launch claim matches verified runtime state.

Evidence required:

```txt
copy reviewed
claim/evidence pairing checked
governance state assigned
approval requirement named
```

---

## 6. Launch Blocker Definitions

A launch blocker exists if any of the following are true:

- Checkout cannot complete.
- Buyer cannot provide intake.
- Payment succeeds but fulfillment path is undefined.
- Runtime surface appears live but required controller/data path is broken.
- Public copy claims automation or certainty not actually present.
- Secret values are exposed.
- Authority approval is implied but not explicit.

---

## 7. Minimum Launch-Ready State

Minimum acceptable state:

```txt
Audit page renders.
Checkout path works.
Buyer email/intake path works.
Manual fulfillment path is documented.
Public copy is honest.
Secrets are protected.
Runtime hooks are either verified live or clearly marked inactive.
Operator explicitly approves launch posture.
```

---

## 8. First Execution Prompt

Use this to activate the packet with another model, Copilot, Merlin, or terminal companion.

```txt
MIRRORNODE Live Audit Launch Verification

Use the active Charges for THEIA, THOTH, PTAH, HERMES, MERLIN, OSIRIS, and LIBRARIAN.

Objective:
Verify that the Osiris Audit v1 path can accept a real buyer, collect usable intake, preserve runtime truth, protect evidence/security boundaries, and support manual fulfillment without overclaiming automation.

Check these lanes:
1. Public Audit Page
2. Checkout
3. Intake
4. Runtime Hooks / Drift Detector
5. Fulfillment
6. Public Claim / Governance Review

Required return format:
- Lane status: pass / warning / blocker / unknown
- Evidence used
- Files/routes checked
- Findings
- Required fix
- Escalation target

Do not expose secret values.
Do not treat visual render as runtime proof.
Do not declare launch complete without explicit Operator approval.
```

---

## 9. Operating Principle

Launch is not a feeling. Launch is a verified path from public promise to fulfilled deliverable.
