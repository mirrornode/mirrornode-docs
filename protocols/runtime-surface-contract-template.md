# Runtime Surface Contract Template

Date: YYYY-MM-DD  
Source: Operator / Theia / Engineering Review  
Status: Draft / Active / Locked / Retired  
Surface Owner: <node / repo / maintainer>  
Canonical Relationship: Operational contract; promote to CORE-HUB only if ratified.

---

## 1. Purpose

This document defines the runtime contract for a live UI or service surface.

Use this template whenever a page, component, route, HUD, audit panel, checkout surface, drift review surface, or other published interface depends on JavaScript controllers, backend routes, SSE streams, webhooks, DOM hooks, selectors, or integration state.

A visual redesign is not complete until this contract still passes.

---

## 2. Surface Identity

| Field | Value |
|---|---|
| Surface name | `<name>` |
| Public route / entry point | `<route or URL>` |
| Repo | `<owner/repo>` |
| Primary files | `<page/component/controller files>` |
| Runtime owner | `<node/person/team>` |
| Launch status | `draft / local / staging / production / blocked` |
| Last verified | `YYYY-MM-DD` |

---

## 3. Runtime Controller

List the file/function that attaches live behavior.

| Controller file | Function / behavior | Required for launch? |
|---|---|---|
| `<path/to/file>` | `<function name or behavior>` | `yes/no` |

Example:

| Controller file | Function / behavior | Required for launch? |
|---|---|---|
| `main.js` | `initDriftDetector()` attaches drift review behavior | yes |

---

## 4. Required DOM Hooks

List every ID, selector, data attribute, or element expected by the controller.

| Hook | Type | Used by | Required? | Failure if missing |
|---|---|---|---|---|
| `<hook>` | `id / class / data-attr / selector` | `<controller/function>` | `yes/no` | `<failure mode>` |

Example:

| Hook | Type | Used by | Required? | Failure if missing |
|---|---|---|---|---|
| `drift-status-icon` | id | `initDriftDetector()` | yes | Controller exits early; no live drift polling |
| `drift-findings-list` | id | `initDriftDetector()` | yes | Findings cannot render |

### Rule

Do not remove, rename, or hide required hooks during redesign unless the controller is updated in the same patch and verified.

---

## 5. Backend / Integration Dependencies

| Dependency | Type | Path / name | Required? | Expected behavior |
|---|---|---|---|---|
| `<dependency>` | `API / SSE / webhook / env / DB / auth / external service` | `<path/name>` | `yes/no` | `<expected result>` |

Example:

| Dependency | Type | Path / name | Required? | Expected behavior |
|---|---|---|---|---|
| Drift stream | SSE | `/api/drift/SSE` | yes | Streams drift findings into the review surface |

---

## 6. Environment Variables

List only variable names, never secret values.

| Variable | Required? | Surface behavior if absent |
|---|---|---|
| `<ENV_NAME>` | `yes/no` | `<behavior>` |

---

## 7. Failure Modes

Document the expected degraded states clearly.

| Failure | Visible symptom | Severity | Required response |
|---|---|---|---|
| Missing DOM hook | `<symptom>` | `warning / blocker` | `<repair>` |
| Missing backend endpoint | `<symptom>` | `warning / blocker` | `<repair>` |
| Missing env var | `<symptom>` | `warning / blocker` | `<repair>` |
| Auth failure | `<symptom>` | `warning / blocker` | `<repair>` |
| Empty data state | `<symptom>` | `acceptable / warning / blocker` | `<repair or message>` |

### Severity Guide

| Severity | Meaning |
|---|---|
| acceptable | Intended empty or fallback state |
| warning | Surface works, but degraded or misleading |
| blocker | Surface appears functional but live behavior is broken, unsafe, or unverifiable |

---

## 8. Verification Checklist

Before merge or launch, verify:

- [ ] Page/component renders.
- [ ] Required DOM hooks exist in the final markup.
- [ ] Runtime controller does not exit early.
- [ ] Required endpoint returns expected response.
- [ ] Empty state is honest and not misleading.
- [ ] Live data path has been tested.
- [ ] Console has no launch-blocking runtime errors.
- [ ] Build/lint/test pass, where applicable.
- [ ] If redesigned, old controller contract was preserved or deliberately updated.

---

## 9. Suggested Manual Checks

Use commands appropriate to the repo.

```bash
# Confirm hooks exist in source
grep -R "<required-hook>" .

# Confirm controller still references expected hooks
grep -R "getElementById\|querySelector\|data-" .

# Confirm route/API exists
grep -R "<api-route-or-endpoint>" .
```

For browser verification:

```txt
1. Open the surface.
2. Confirm the live region renders.
3. Confirm network activity reaches the required endpoint.
4. Confirm the displayed state changes when data is present.
5. Confirm fallback copy is truthful when no data is present.
```

---

## 10. Review Disposition

Use this section during PR review.

```txt
Runtime contract reviewed: yes/no
Required hooks preserved: yes/no
Controller updated in same patch: yes/no/not applicable
Backend dependency verified: yes/no/not applicable
Failure mode acceptable: yes/no
Launch blocker present: yes/no
Reviewer disposition: accept / request changes / block launch
```

---

## 11. Example: Drift Detector Surface

| Field | Value |
|---|---|
| Surface name | Drift Detector Review Surface |
| Runtime controller | `main.js` / `initDriftDetector()` |
| Required hook | `drift-status-icon` |
| Required hook | `drift-findings-list` |
| Backend dependency | `/api/drift/SSE` |
| Known blocker | Controller exits early if `drift-status-icon` is missing |
| Correct repair | Restore DOM hooks unless controller is deliberately updated in same patch |

### Drift Detector Launch Rule

The published page must not remain as static “evidence sources not connected” copy when configured evidence sources are available. If the live review surface does not poll or render findings, launch is blocked.

---

## 12. Operating Principle

A surface that looks alive but cannot connect to its runtime is worse than an honest placeholder.

Preserve the contract, or declare the surface inactive.
