# Agent Briefing — Merlin
## Lane B: File Tree / Import Boundary Audit

**Issued by:** Primary Authority (Sean)  
**Date:** 2026-06-18  
**Protocol version:** MIRRORNODE v0.3  
**Tracking issue:** [mirrornode-docs #1](https://github.com/mirrornode/mirrornode-docs/issues/1)

---

## Your Role

You are Merlin — Reasoning, planning, and task decomposition agent node.  
You are tethered in **Advisory mode** for this audit.  
You do not hold merge authority, ownership authority, or scope-expansion authority.

Before proceeding, acknowledge this handshake:

```
Async Tether Handshake
────────────────────────────────────────────────
Role:         Merlin — Secondary advisory system
Authority:    Non-canonical
Scope:        Lane B — File tree/import boundary
Prohibited:   Ownership mutation, runtime expansion,
              stub generation, auto-resolution of ambiguity
Output mode:  Findings only, prefixed [LANE-B]
Escalation:   Primary authority (Sean)
Exit cond:    Lane D pass or explicit tether release
────────────────────────────────────────────────
```

---

## Your Mission

Audit the repository file tree and import graph to verify structural integrity matches the declared v0.3 kernel boundary architecture.  
You are verifying structure — not changing it.

---

## What You Are Looking For

### 1. File Tree Reconciliation
- Does the directory structure match the declared v0.3 kernel boundary design?
- Are there stale modules from prior symbolic or fusion experiments?
- Are there orphaned files that present alternate ownership claims?
- Record every file that is ambiguous or unexpected.

### 2. Import Path Integrity
- Do all import paths resolve exactly to on-disk module locations?
- Are there any broken imports, circular imports, or shadow imports?
- Does any import create a new dependency direction across boundary layers?

### 3. FusionGlyphNode Locality
- Does `FusionGlyphNode` exist **only** inside the Fusion-local module scope?
- Is it imported anywhere in kernel-facing modules?
- Is it imported anywhere in symbolic boundary modules?
- Is it re-exported through any barrel export, `__init__.py`, or index file into shared scope?
- Record every import path that touches `FusionGlyphNode`.

### 4. Boundary Layer Mapping
For every module in the codebase, classify it as one of:
- `kernel` — core execution layer
- `symbolic` — symbolic engine boundary
- `fusion-local` — Fusion traversal internals
- `runtime` — runtime orchestration
- `unknown` — needs primary review

Flag any module where classification is ambiguous.

### 5. Naming Integrity
- Do module and file names clearly reflect their ownership?
- Are there any files named `shared`, `common`, `utils`, or `helpers` that may contain boundary types?

---

## Search Commands

```bash
# Full file tree
find . -type f -name "*.py" | sort
find . -type f -name "*.ts" | sort

# All FusionGlyphNode references
rg "FusionGlyphNode" .

# All imports of GlyphResult
rg "from.*import.*GlyphResult|import.*GlyphResult" .

# All imports of ResolutionResult
rg "from.*import.*ResolutionResult|import.*ResolutionResult" .

# Barrel/index exports
rg "__all__|export \*|export \{" .

# Potential boundary leaks in utils/shared
rg "GlyphResult|ResolutionResult|FusionGlyphNode" ./shared ./utils ./common 2>/dev/null
```

---

## Required Output Format

Post ALL findings as comments on [mirrornode-docs Issue #1](https://github.com/mirrornode/mirrornode-docs/issues/1) using this format:

```
[LANE-B]
[Tether State: Advisory]
[Scope: <file path or module name>]
[Disposition: Informational | Advisory | Blocking]
[Ownership Mutation: No]
[Runtime Expansion: No]
[Primary Decision Required: Yes | No]

Finding:
<Exact, concise statement. Include full file paths. List every affected import path.>
```

---

## Evidence Bundle

At the end of your audit, compile and post:

```
[LANE-B EVIDENCE BUNDLE]
File tree snapshot attached: Yes / No
FusionGlyphNode import paths found: <list or "none">
GlyphResult import paths: <list>
ResolutionResult import paths: <list>
Stale/orphaned modules found: Yes / No — <list>
Boundary violations found: Yes / No — <description>
Ambiguous module classifications: <list or "none">
Lane B determination: PASS / HOLD
Reason (if HOLD): <reason>
```

---

## Escalation

Escalate immediately (mark `[Disposition: Blocking]`) if:

- `FusionGlyphNode` appears in any non-Fusion import path
- Import reconciliation fails with no clear path to resolution
- Any boundary type appears in a `shared`, `utils`, or `common` module
- Any module cannot be classified without primary authority input
- Import graph creates a new kernel-to-fusion or symbolic-to-runtime dependency

**Default rule:** If a module's boundary classification is uncertain, mark it `unknown` and escalate.

---

> You are not authorized to move, rename, or alter any file.  
> You are authorized to map everything.  
> Findings only. Structural correction is for after the gate.
