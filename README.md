# MIRRORNODE Documentation Hub

**Authority:** Operator (Sean Malm)  
**Status:** Active  
**Last Updated:** 2026-06-23  
**Canonical Source:** [MIRRORNODE-CORE-HUB](https://github.com/mirrornode/MIRRORNODE-CORE-HUB)

---

## What This Repo Is

`mirrornode-docs` is the **external documentation surface and migration staging ground** for the MIRRORNODE ecosystem — the home for:

- Operational protocols and agent briefings
- Notion exports (Markdown-converted, datestamped)
- Phone/voice memo transcriptions migrated to version control
- Local machine drafts awaiting canon integration
- In-progress documentation not yet ready for CORE-HUB canon
- Integration runbooks and setup references
- Architecture decision records (ADRs)

Constitutional governance (charters, contracts, audit SDKs) lives in
[`MIRRORNODE-CORE-HUB/canon/`](https://github.com/mirrornode/MIRRORNODE-CORE-HUB/tree/main/canon).
This repo **extends** — it does not replace — that canon.

---

## Directory Structure

```
mirrornode-docs/
├── README.md                    # This file
├── DOC_SYNC_CHECKLIST.md        # Cross-surface documentation audit checklist
│
├── protocols/                   # Operational protocols (active)
│   ├── agent-briefings/
│   ├── async-tethering-lock-in.md
│   └── v0.3-audit-checklist.md
│
├── notion-exports/              # Notion → Markdown exports (raw, datestamped)
│   └── YYYY-MM-DD_<page-title>.md
│
├── session-notes/               # Phone/voice memo transcriptions + session logs
│   ├── assets/                  # Whiteboard photos, sketches
│   └── YYYY-MM-DD_<topic>.md
│
├── local-drafts/                # Raw content migrated from local machines
│   └── YYYY-MM-DD_<topic>.md
│
├── drafts/                      # In-progress writing not yet canon-ready
│   └── YYYY-MM-DD_<topic>.md
│
├── integrations/                # Integration runbooks
│   └── <integration-name>.md
│
└── architecture/                # Architecture decision records (ADRs)
    └── ADR-NNNN-<title>.md
```

---

## File Conventions

**Naming:** `YYYY-MM-DD_Topic.md` for all new files.

**Required header block** on every migrated file:
```
Date: YYYY-MM-DD
Source: [Phone / Notion / Computer-1 / Computer-2 / Perplexity-session]
Status: [Draft / Archived / Pending-Integration]
```

**Format:** All files must be `.md` (Markdown).

---

## Source-of-Truth Map

| Document Type | Canonical Location |
|---------------|--------------------|
| Agent charters | `CORE-HUB/canon/charters/` |
| Audit contracts & SDKs | `CORE-HUB/canon/contracts/` |
| Phase status & metrics | `CORE-HUB/canon/status/` |
| Repo org map | `CORE-HUB/REPO_MAP.md` |
| System contract | `CORE-HUB/SYSTEM_CONTRACT.md` |
| Operational protocols | **This repo** — `protocols/` |
| Notion exports | **This repo** — `notion-exports/` |
| Phone/session notes | **This repo** — `session-notes/` |
| Local machine drafts | **This repo** — `local-drafts/` |
| In-progress drafts | **This repo** — `drafts/` |
| Integration runbooks | **This repo** — `integrations/` |
| Architecture decisions | **This repo** — `architecture/` |

---

## Sync Status

| Source | Last Synced | Notes |
|--------|-------------|-------|
| Notion | ⬜ Never | Export pending |
| Phone / Voice memos | ⬜ Never | Transcription pending |
| Computer #1 | ⬜ Unknown | Verify git status |
| Computer #2 | ⬜ Unknown | Verify git status |

*Update this table after each sync run. See `DOC_SYNC_CHECKLIST.md`.*

---

## Related Repos

| Repo | Role |
|------|------|
| [MIRRORNODE-CORE-HUB](https://github.com/mirrornode/MIRRORNODE-CORE-HUB) | Root of truth, canon, agents |
| [mirrornode-platform](https://github.com/mirrornode/mirrornode-platform) | Next.js frontend |
| [theia-core](https://github.com/mirrornode/theia-core) | Flagship Python architecture |
| [mirrornode-py](https://github.com/mirrornode/mirrornode-py) | Python utilities |
| [osiris-audit](https://github.com/mirrornode/osiris-audit) | OSIRIS audit library |
| [MirrorNode-HUD-Engine-Interface-Governance-Specification](https://github.com/mirrornode/MirrorNode-HUD-Engine-Interface-Governance-Specification) | HUD/Engine governance spec |

---

*This repo is part of the MIRRORNODE governance structure. All updates subject to `emit_audit()` contract.*
