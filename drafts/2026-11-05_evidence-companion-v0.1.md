# MIRRORNODE Evidence Companion — Product Intent v0.1

Date: 2026-11-05  
Source: Operator–THEIA working session (design direction explicitly locked by Operator)  
Status: **PROPOSED / UNVALIDATED; NOT CANON; NOT IMPLEMENTED**  
Authority: Operator approves investigation and preparation of a team review, not runtime deployment or governance promotion.  
Repository role: Documentation staging; `MIRRORNODE-CORE-HUB` remains the authority for ratified governance.

## 1. Product premise

An opt-in, Grammarly-like contextual knowledge companion that identifies passages where legal, tax, regulatory, scientific, financial, or evidentiary context could materially improve a person's understanding. It offers verifiable sources and qualifiers, **without editing the person's work or substituting for professional judgment**.

North star: *Knowledge available when it matters; agency retained by the person.*

## 2. First bounded use case

- Surface: browser extension with explicitly granted per-site or selected-text access, not blanket surveillance.
- Initial domains: U.S. federal law, Washington state law, and U.S. federal tax guidance.
- Input: user selection or explicitly enabled supported page; no ambient collection across unapproved tabs/apps.
- Output: up to three evidence cards, each with source title, direct URL, issuing authority, publication/effective date when known, applicable jurisdiction, scope, caveat, and the particular assertion supported.
- User actions: dismiss, inspect originals, copy/export citation, optionally attach selected reference. No automatic edits, filing, emailing, or external-system mutation.
- Workflow: `Read → Detect → Retrieve → Verify → Offer → Attach (on user action)`.

## 3. Grounding and uncertainty contract

Record the exact claim span and differentiate **reported allegation, factual assertion, legal rule, interpretation, and normative opinion**. Source ranking should favor authentic current primary materials (statutes, regulations, official agency publications, court opinions); secondary sources may aid discovery but do not silently substitute for primary authority.

Every card must identify: (a) what the evidence says, (b) what it does **not** establish, (c) jurisdiction and time sensitivity, (d) open uncertainty. Potential negative judicial treatment, amendments, superseded guidance, and local exceptions require checking or an explicit unresolved warning.

Proposed display states: **Supported; Qualification needed; Contradicted by retrieved evidence; Unresolved; Relevant context**. These are claims about *checked materials*, not absolute truth or legal conclusions. Never mark a proposition verified solely because an LLM cited it.

## 4. Safety, permissions, and failure behavior

- Treat webpage text, PDFs, and tool output as untrusted data; ignore embedded instructions directing the assistant to exfiltrate, override policy, contact people, or change controls.
- Minimize and redact sensitive text before remote search; prefer local detection. Do not upload a full private document by default.
- Clearly explain when a source cannot be verified or cannot be accessed. Abstain rather than fabricate citations or current-law status.
- No autonomous professional advice, eligibility determination, accusation, or compliance certification.
- Exclude sensitive categories from any default passive monitoring (legal strategy, children, health, financial account information); require additional explicit consent and an appropriate security design.
- Opt-out, source inspection, and deletion/export controls must be designed before user trials.

## 5. v0.1 evaluation plan (proposal)

Build a **synthetic or publicly sourced** benchmark containing straightforward correct statements, outdated statutes, ambiguous jurisdiction, conflicting reporting, misleading quotations, missing sources, and malicious prompt-injection passages. Test accurate citation-to-claim linking, abstention, time/jurisdiction handling, user-controlled attachment, and false-positive interruption burden. Record false negatives too.

Minimum demonstration: a browser proof-of-concept on an allowlisted site, with no real private documents and an auditable trace showing what was sent outside the device. Define numeric acceptance thresholds *after* collecting a measured baseline; do not invent passing rates.

## 6. Non-goals and dependency map

Not a law firm, accountant, fact-checking authority, surveillance service, or substitute for legal/tax advice. Do not promise real-time source coverage until verified. No commercial promise or deployment authority from this draft.

Conceptual interfaces (not observed integration): THOTH source/security review, WITNESS provenance, Proof-or-Stop claim gate, PTAH governed changes/key custody, MirrorMirror user interaction, and MOPCON oversight. Their availability and boundary enforcement must be independently demonstrated.

Related drafts:
- [Case Builder](2026-11-05_case-builder-concept-v0.1.md)
- [Security architecture and integrity gates](2026-11-05_evidence-continuity-security-architecture-v0.1.md)
- [Team review handoff](../protocols/agent-briefings/2026-11-05_evidence-continuity-council-handoff.md)
