# MIRRORNODE Documentation Sync Checklist

**Purpose:** Ensure all documentation is captured in version-controlled locations.  
**Owner:** Operator (Sean Malm)  
**Last Reviewed:** 2026-06-23  
**Run:** At the start/end of each major work session, or weekly minimum.  
**Next Scheduled Sync:** 2026-06-30

---

## Migration Phases (One-Time)

| Status | Phase | Action |
|--------|-------|--------|
| ⬜ | **Phase 1 — Discovery** | Run `git ls-files` on `canon/api`, `canon/schemas`, `canon/verification`, `prompts/`, `state/`, `codex/symbolic/` in CORE-HUB. List all unenumerated files. |
| ⬜ | **Phase 2 — Phone Export** | Transcribe all voice memos + notes app entries → `session-notes/YYYY-MM-DD_<topic>.md`. Include source header. |
| ⬜ | **Phase 3 — Notion Export** | Export all MIRRORNODE Notion pages as Markdown → `notion-exports/YYYY-MM-DD_<page-title>.md`. |
| ⬜ | **Phase 4 — Local Migration** | Move loose drafts from Computer #1 and #2 → `local-drafts/`. Confirm no file exists only on one machine. |
| ⬜ | **Phase 5 — Cleanup** | Delete/archive local scratchpads once safely committed to Git. |
| ⬜ | **Phase 6 — Map Update** | Update `CORE-HUB/REPO_MAP.md` to June 2026 after migration is complete. |
| ⬜ | **Phase 7 — Verification** | Cross-check `prompts/`, `protocols/`, `state/` across CORE-HUB and mirrornode-docs for duplication or conflict. |

---

## Part 1 — Local Machine Sync (Recurring)

### Computer #1 (Primary)
- [ ] `git status` in CORE-HUB — no untracked doc files
- [ ] `git status` in mirrornode-platform — no untracked doc files
- [ ] Any loose `.md`, `.txt`, `.json` in project dirs? → commit or move to `local-drafts/`
- [ ] `~/.mirrornode/accomplishments.json` backed up? (`track export --all --output all.csv`)
- [ ] `.env.example` current with all active integration keys?

### Computer #2 (Secondary)
- [ ] Git remote confirmed → `github.com/mirrornode/*`
- [ ] `git fetch --all && git status` — identify divergent branches
- [ ] Any files that exist ONLY on Computer #2? → copy and push
- [ ] No conflicting versions of canon files?

---

## Part 2 — Phone / Mobile Notes (Recurring)

- [ ] Voice memos → transcribe into `session-notes/YYYY-MM-DD_<topic>.md`
- [ ] Notes app entries → key decisions captured and committed
- [ ] Architecture or naming decisions from phone? → `session-notes/`
- [ ] Whiteboard photos/sketches? → `session-notes/assets/`

---

## Part 3 — Notion Export (Monthly)

- [ ] Open Notion workspace → identify all MIRRORNODE-related pages
- [ ] Export each page: `... → Export → Markdown & CSV`
- [ ] Rename: `YYYY-MM-DD_<page-title>.md`
- [ ] Commit to `notion-exports/`

**Known pages to export:**
- [ ] Main MIRRORNODE workspace
- [ ] Agent design notes
- [ ] Roadmap / phase planning
- [ ] Integration research notes
- [ ] Any other active pages

---

## Part 4 — GitHub Repo Audit (Recurring)

### Active canonical repos — README current?
- [ ] [MIRRORNODE-CORE-HUB](https://github.com/mirrornode/MIRRORNODE-CORE-HUB)
- [ ] [mirrornode-docs](https://github.com/mirrornode/mirrornode-docs)
- [ ] [mirrornode-platform](https://github.com/mirrornode/mirrornode-platform)
- [ ] [theia-core](https://github.com/mirrornode/theia-core)
- [ ] [mirrornode-py](https://github.com/mirrornode/mirrornode-py)
- [ ] [osiris-audit](https://github.com/mirrornode/osiris-audit)
- [ ] [MirrorNode-HUD-Engine-Interface-Governance-Specification](https://github.com/mirrornode/MirrorNode-HUD-Engine-Interface-Governance-Specification)

### Canon completeness (CORE-HUB)
- [ ] `REPO_MAP.md` updated (stale — last verified 2026-04-28)
- [ ] `canon/status/` — progress report within last 30 days
- [ ] All active charters have `.sig` files
- [ ] Unenumerated dirs audited: `canon/api/`, `canon/checklists/`, `canon/schemas/`, `canon/verification/`, `prompts/`, `state/`, `codex/symbolic/`

### Placeholder repos — activate or archive?
- [ ] `mirrornode-backend`
- [ ] `MIRRORNODE-INFRA`
- [ ] `mirrornode-index`
- [ ] `Mirror_surface`
- [ ] `mirrornode-ring`

---

## Part 5 — Integration Runbooks (Recurring)

- [ ] `integrations/stripe.md` — Osiris/billing (active)
- [ ] `integrations/vercel.md` — deployment (active)
- [ ] `integrations/upstash-redis.md` — Thoth KV (planned)
- [ ] `integrations/supabase.md` — Thoth persistence (planned)
- [ ] `integrations/litellm.md` — AI model layer (gap)
- [ ] `integrations/clerk.md` — IDP/auth (gap)
- [ ] `integrations/langfuse.md` — LLM observability (gap)
- [ ] `integrations/inngest.md` — scheduling/queues (gap)

---

## Part 6 — AI Session Outputs (Recurring)

- [ ] Integration landscape analysis (2026-06-23) → `session-notes/2026-06-23_integration-landscape.md`
- [ ] Documentation inventory (2026-06-23) → `session-notes/2026-06-23_doc-inventory.md`
- [ ] Future Perplexity sessions → `session-notes/YYYY-MM-DD_perplexity-<topic>.md`

---

## Completion Record

| Date | Completed By | Notes |
|------|-------------|-------|
| 2026-06-23 | Sean (computer-assisted) | Initial checklist created; README and checklist pushed to mirrornode-docs |

---

**Policy:** This checklist is itself versioned. Update phase lists as repos are added or archived.
