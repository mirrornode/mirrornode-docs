# MIRRORNODE Case Builder — Persistent Analytical Orchestrator v0.1

Date: 2026-11-05  
Source: Operator–THEIA working session (long-term design direction explicitly locked by Operator)  
Status: **PROPOSED / UNVALIDATED; NOT CANON; NOT IMPLEMENTED**  
Classification: Product/architecture concept only; this document contains no case-specific evidence.

## 1. Mission and scope

**Case Builder** is a participant-controlled, long-duration analytical workspace for evidence-based inquiries that unfold over days, months, or years: legal, administrative, public-interest, research, business, or personal record-reconciliation cases. It should preserve originals, provenance, claims, counterevidence, uncertainty, and continuity, **without inventing facts or deciding outcomes**.

The companion detects potentially relevant information at the point of encounter. Case Builder retains an authorized, accountable history of the inquiry. Proof-or-Stop must prevent a persuasive narrative from outrunning its evidence.

## 2. Meaning of “read-only”

**Strictly read-only toward external systems:** no altering source records, sending messages, filing claims, making purchases, contacting subjects, publishing allegations, or modifying third-party accounts. Scheduled research may retrieve only from sources and scopes individually authorized by the participant, under bounded frequency and budget.

**Internally writable only by authorization:** an encrypted case workspace may append immutable source versions, observations, analytical derivatives, annotations, and correction events. “Read-only” is **not** a claim that a persistent system makes no internal writes. Every internal change must have provenance and a visible correction trail. A participant may stop monitoring and revoke future permissions.

## 3. Proposed case object model

- **Case:** opaque case ID, purpose, owner, classification, consent grants, retention choices.
- **Source object:** original bytes or referenced source; locator, acquisition method, observed timestamp, jurisdiction, source publisher, content hash and verification state.
- **Claim:** exact assertion, origin/source offsets, who asserted it, proposition type, asserted event time, confidence *and reason*, supports/contradicts/unknown edges.
- **Event:** interval or uncertain date, participants where legitimately necessary, linked sources, contested status.
- **Finding:** question, candidate explanations, affirmative and disconfirming evidence, caveats, revision history.
- **Review/receipt:** operator or reviewer decision, scope, input versions, changes, limitations, integrity metadata.
- **Monitor grant:** permitted sources and query parameters, frequency, expiry, privacy classification, revocation.

Provenance labels must separate **USER-ASSERTED / EXTERNALLY-OBSERVED / SOURCE-REPORTED / VERIFIED AGAINST ORIGINAL / DERIVED / UNRESOLVED**. A cryptographic hash proves correspondence to retained bytes, not truth, authorship, lawful acquisition, or admissibility. Chain of custody for legal use requires additional procedures and expert review.

## 4. Core user journey

1. Participant opens a case, sets its purpose and permission boundary.
2. Adds a synthetic/public or lawfully possessed source; system preserves the original and logs provenance.
3. System proposes claims, events, and conflicting assertions **as hypotheses for review**.
4. Participant inspects each source and can correct, reject, qualify, or hide derivative interpretations without erasing original audit history.
5. Explicitly authorized recurring checks identify changes, attach versioned references, and notify only about material differences.
6. Review produces an auditable case brief including material counterevidence, missing records, and unresolved questions.

## 5. Long-term orchestration boundaries

- Scheduler is **opt-in, case-scoped, revocable, rate-limited**, and disabled by default.
- Queries must not leak private names, personal identifiers, allegation text, or hidden case premises to third-party services by default.
- No covert tracking, private-account scraping, unauthorized investigation, automated accusations, or unreviewed external escalation.
- A case about a minor, health matter, immigration status, or family allegation is **high sensitivity** and cannot enter initial trials with genuine personal data.
- Distinguish a missing record from proof that an event did not occur. Explicitly solicit disconfirming evidence; do not nudge the participant toward conviction.

## 6. Encryption and participant control

End-to-end encryption is a **requirement, not an achieved property**. A credible design must specify the endpoint identities, trust boundary, key generation/storage, device compromise model, recovery, sharing, revocation, backup, export, lawful process, and what a server can see.

If server-side models receive plaintext, it is dishonest to claim those disclosures are end-to-end encrypted from the provider. Initial concept: local-first analysis, encrypted-at-rest case objects, participant-controlled keys, and tightly minimized public remote retrieval. Formal threat model and independent assessment are launch prerequisites.

## 7. First experiment and stop conditions

Synthetic case: 20+ fabricated records with changed dates, contradictory assertions, duplicate files, a falsely authoritative source, and adversarial injection text. Prove original preservation, source-linked chronology, correction receipt, contradiction handling, permission expiry, encrypted backup/recovery, and a clear **insufficient evidence** result.

**STOP** on fabricated citations, data crossing an unauthorized trust boundary, silent source alteration, insecure key recovery, irrecoverable evidence without disclosed recovery risk, hidden monitoring, or promotional claims of secure production readiness without validation.

Related drafts:
- [Evidence Companion](2026-11-05_evidence-companion-v0.1.md)
- [Security architecture and integrity gates](2026-11-05_evidence-continuity-security-architecture-v0.1.md)
- [Team review handoff](../protocols/agent-briefings/2026-11-05_evidence-continuity-council-handoff.md)
