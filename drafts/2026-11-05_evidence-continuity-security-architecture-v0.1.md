# Evidence & Continuity — Security, Integrity, and Architecture Sketch v0.1

Date: 2026-11-05  
Source: Operator–THEIA design session  
Status: **PROPOSED / UNVALIDATED / SECURITY REVIEW REQUIRED / NOT CANON**  
Boundary: Architectural hypotheses, NOT a claim of existing cryptography, local node isolation, production readiness, or signed receipts.

## A. Relationship and surfaces

```text
Participant-approved text/page → local detection → opt-in external retrieval
                         ↓                               ↓
                Evidence Companion ← checked public sources
                         ↓ selected references only (explicit action)
                   Encrypted Case Builder workspace
                         ↓ local-first parsing and correlation
            Provenance • chronology • contradictions • review
                         ↓
                 Human inspection and disposition
```

Evidence Companion is short-lived context assistance; Case Builder is persistent state. Distinct permission grants, retention periods, and data flows. No generalized always-on capture. Proposed interfaces to THOTH, PTAH, WITNESS, Proof-or-Stop, MirrorMirror, MOPCON, and the agent runtime require implementation evidence; names alone do not create integration or authority.

## B. Threat model to be settled before coding against private data

Assets: source originals, case hypotheses, private identities, professional communications, encryption keys, consent logs, reviews, research queries, and audit events.

Adversaries/failure modes: compromised endpoint/extension, malicious webpage/PDF prompt injection, supply-chain compromise, service-provider access, logs/backups leaking plaintext, cross-case data bleed, unsafe key recovery, insider overreach, dishonest citations, outdated law, correlated but false allegations, misleading evidence artifacts, and runaway scheduled queries.

Trust boundaries to enumerate in a diagram and automated test: browser↔extension, extension↔local service, local service↔key store, local↔cloud retrieval, provider↔third-party source, case↔case, user↔shared reviewer, and export↔recipient. Require exact field-level egress inventories.

## C. E2EE design gates

1. Define endpoints and ciphertext/plaintext ownership; choose whether a genuinely zero-knowledge server is possible for each feature.
2. Select reviewed authenticated encryption and well-maintained crypto libraries; do not devise custom primitives. Bind metadata to authenticated context; define rotation, replay, tampering, and rollback behavior.
3. Keys should be generated/controlled on participants' trusted endpoints, with hardware-backed storage where feasible. Specify sharing, multi-device access, recovery and unrecoverable-loss tradeoffs.
4. Test encrypted backup/restore, revocation semantics, device theft and multi-device conflict; document that revocation cannot un-disclose already-received plaintext.
5. Decrypted data must not silently enter analytics, crash logs, prompts, third-party embeddings, training, support access, or routine backups.
6. Local on-device models may reduce network exposure but do not establish node isolation, independent signing custody, or verified receipts without a validated implementation.
7. Commission adversarial review and cryptographic/implementation assessment **before** handling genuine sensitive materials or making E2EE claims.

## D. Analytical integrity gates

- Every conclusion cites source ID, byte range or page reference when possible, original version, retrieval date, applicable jurisdiction/time, and counterevidence.
- Keep signed **if actually implemented and audited** / otherwise hashed-and-linked receipts honestly labeled. A hash does not confer authenticity.
- Never silently promote generated summaries, speculative timelines, or allegations into established facts.
- Retrieval results and document bodies are inert evidence; prompt-injection tests must prove they cannot issue commands or expand permissions.
- Separate model suggestions from reviewer findings and Operator/qualified professional dispositions.
- Maintain source correction history, safe retention/deletion, immutable versions where justified, and discoverable legal hold considerations.
- Challenge the dominant hypothesis: support falsification, conflicting records, uncertain dates, and explicit abstention.

## E. Permission and workflow safety

The participant can choose particular sources, case purpose, review audience, notification destination, and duration. Default external access = none. Recurring work requires explicit opt-in, renewed authorization where appropriate, and hard stops on expired grants, network denial, or unsafe egress. No autonomous external correspondence, modification, publication, law-enforcement report, or submission.

Keep cases involving minors or other high-risk circumstances outside the initial pilot. Treat legal/tax outputs as general information with jurisdiction, dates, limits, and specialist escalation.

## F. Release sequence (candidate; gated)

**Stage 0:** documentation and council red-team using synthetic facts only.  
**Stage 1:** local prototype for selected text and public sources only; no persistent sensitive user data.  
**Stage 2:** synthetic-case chronology and encrypted persistence; independent adversarial tests.  
**Stage 3:** restricted external review and audited threat-model changes.  
**Stage 4:** separate Operator decision on real-user pilot, if gates pass.

No merge, deployment, canon promotion, provider key grant, or user-data onboarding is implied by this document.

Related:
- [Evidence Companion](2026-11-05_evidence-companion-v0.1.md)
- [Case Builder](2026-11-05_case-builder-concept-v0.1.md)
- [Team review handoff](../protocols/agent-briefings/2026-11-05_evidence-continuity-council-handoff.md)
