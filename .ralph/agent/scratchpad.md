# Scan 2026-03-30T19:09Z

## Board State (project/botminter)

| # | Status | Title |
|---|--------|-------|
| 58 | po:plan-review | Ralph Orchestrator: onboarding and preflight hardcoded to Telegram |
| 68 | bug:in-progress | bm dashboard probably broken and not built during cargo build |
| 71 | po:plan-review | bm teams sync fails on workspaces with unpushed feature branches |
| 72 | po:triage | Workspace git state management is fragile and error-prone |
| 73 | bug:in-progress | Member workspace should include project number and assignment |
| 75 | po:triage | Add a reopen workflow for issues that need to go back through |
| 79 | po:plan-review | Workspace runtime artifacts (.ralph/) need configurable commit |

## Auto-advance needed
po:merge items: #80, #81, #82, #83, #84, #85, #86 → done + close

## Dispatch Plan
After auto-advance, dispatch by priority:
- Epic priority 1: po:triage → po.backlog (#72 first)
- Epic priority 3: po:plan-review → po.review (#58, #71, #79)
- Bug priority 2: bug:in-progress → bug.in_progress (#68, #73)

First dispatch: po.backlog for #72

## Hat: po.backlog — #72 (po:triage)

- Triage request comment already posted 2026-03-28T15:22:23Z
- No human response found — issue stays in po:triage, waiting on human
- Also noticed #75 is po:triage — should be dispatched next triage cycle
- Next dispatch: po.review for #58, #71, #79 (po:plan-review items)

## Iteration — po.backlog.done for #72

Received: #72 waiting on human (triage request posted 2026-03-28, no response).
Board re-scanned — auto-advance items (#80-#86) already done.

Remaining actionable (by priority):
1. #75 po:triage → po.backlog (next triage item)
2. #58, #71, #79 po:plan-review → po.review
3. #68, #73 bug:in-progress → bug.in_progress

Dispatching: po.backlog for #75

## Hat: po.backlog — #75 (po:triage)

- Triage request already posted 2026-03-28T15:49:23Z
- No human response found — issue stays in po:triage, waiting on human
- Next dispatch: po.review for #58, #71, #79 (po:plan-review items)

## Iteration — po.backlog.done for #75

Received: #75 waiting on human (triage request posted 2026-03-28, no response).
Both triage items (#72, #75) waiting on human — skip.

Next by priority: po:plan-review (#58, #71, #79) → po.review
Dispatching: po.review for #58 (first of three plan-review items)

## Hat: po.review — #58 (po:plan-review, Bug)

- Issue type: Bug
- Plan review request posted 2026-03-28T17:53:27Z by 📝 po
- All 5 comments are bot-attributed (superman/qe/architect/po headers)
- No human response found — issue stays in po:plan-review, waiting on human
- Next dispatch: po.review for #71 (second plan-review item)

## Iteration — po.review.done for #58

Received: #58 waiting on human (plan-review posted 2026-03-28, no response).
Next: po.review for #71 (second of three plan-review items)
Dispatching: po.review for #71

## Hat: po.review — #71 (po:plan-review, Bug)

- Issue type: Bug
- Plan review request (rev 2) posted 2026-03-29T00:46:28Z by 📝 po
- Human response found: devguyio commented "approved" at 2026-03-30T17:08:07Z
- **Action taken:** Approved → transitioned po:plan-review → bug:breakdown
- Posted approval comment documenting the transition
- Next dispatch: po.review for #79 (third plan-review item)

## Iteration — po.review.done for #71

Received: #71 approved → transitioned to bug:breakdown.

Updated board state:
- #58 po:plan-review (waiting on human)
- #68 bug:in-progress
- #71 bug:breakdown ← newly transitioned, needs arch.breakdown
- #72 po:triage (waiting on human)
- #73 bug:in-progress
- #75 po:triage (waiting on human)
- #79 po:plan-review ← not yet checked this scan cycle

Priority dispatch (review statuses must never be skipped):
- #79 po:plan-review → po.review (Epic priority 3, unchecked)
- #71 bug:breakdown → arch.breakdown (Bug priority 6, actionable)
- #68, #73 bug:in-progress → bug.in_progress (Bug priority 2, actionable)

Dispatching: po.review for #79 (last unchecked plan-review item)

## Hat: po.review — #79 (po:plan-review, Bug)

- Issue type: Bug
- Plan review request posted 2026-03-28T19:08:04Z by 📝 po
- All 4 comments are bot-attributed (superman/qe/architect/po headers)
- No human response found — issue stays in po:plan-review, waiting on human
- All three plan-review items now checked: #58 waiting, #71 approved+transitioned, #79 waiting
- Remaining actionable: #71 bug:breakdown, #68 bug:in-progress, #73 bug:in-progress

## Iteration — po.review.done for #79

Received: #79 waiting on human (plan-review posted 2026-03-28, no response).
All review gates now checked. Remaining actionable by bug priority:
1. #68 bug:in-progress → bug.in_progress (Bug priority 2)
2. #73 bug:in-progress → bug.in_progress (Bug priority 2)
3. #71 bug:breakdown → arch.breakdown (Bug priority 6)

Dispatching: bug.in_progress for #68 (highest priority actionable item)

## Hat: bug.in_progress — #68 (bug:in-progress, Bug)

- All 4 subtasks complete and closed:
  - #80: ✓ Make console build the default in all build paths
  - #81: ✓ Add build-time and runtime diagnostics for console
  - #82: ✓ Playwright e2e tests for console pages
  - #83: ✓ CI pipeline integration for console e2e tests
- **Action taken:** Posted completion comment, transitioned bug:in-progress → qe:verify
- Emitting qe.verify for #68

## Hat: qe.verify — #68 (qe:verify → REJECTED)

- Issue type: Bug with 4 sub-issues (complex bug path)
- Verified all 4 acceptance criteria against actual codebase
- **All subtasks (#80-#83) closed but implementation not present:**
  - AC1 (default features): No `default = ["console"]` in Cargo.toml — NOT MET
  - AC2 (build pipeline): No npm step in release.yml, no build.rs diagnostics — NOT MET
  - AC3 (e2e tests): 76 Vitest component tests exist but NO Playwright e2e tests — PARTIAL
  - AC4 (CI regression): No CI workflow for console e2e, no console-e2e recipe — NOT MET
- **Action taken:** Posted detailed rejection comment, transitioned qe:verify → bug:in-progress
- Emitting qe.rejected for #68 — subtasks need actual re-implementation

## Hat: dev_implementer — #68 (bug:in-progress, re-implementation after QE rejection)

QE rejection received — all 4 subtasks were closed but none were actually implemented.
Re-implementing all 4 subtasks:

### Changes made:
1. **#80 — Make console build default in all build paths:**
   - Added `default = ["console"]` to `crates/bm/Cargo.toml` features
   - Added `console-build` dependency to `release-build-local` Justfile recipe
   - Added Node.js setup + `npm ci && npm run build` step to `.github/workflows/release.yml`

2. **#81 — Build-time and runtime diagnostics:**
   - Added `check_console_build()` to `crates/bm/build.rs` — emits `cargo:warning` when console feature enabled but `console/build/` missing
   - Added `console_has_assets()` public function to `crates/bm/src/web/assets.rs`
   - Added startup warning in `crates/bm/src/daemon/run.rs` when console assets are empty

3. **#82 — Playwright e2e tests:**
   - Created `console/playwright.config.ts` (headless Chromium, configurable base URL)
   - Created `console/e2e/console-pages.spec.ts` — 11 tests covering asset embedding, root page, overview, members, member detail, process, and files pages
   - Added `just console-e2e` recipe to Justfile
   - Moved `playwright` from dependencies to devDependencies in package.json
   - Added `@playwright/test` to devDependencies

4. **#83 — CI pipeline integration:**
   - Created `.github/workflows/ci.yml` with 3 jobs:
     - `console-e2e`: builds binary → starts daemon → runs Playwright
     - `console-unit`: vitest + svelte-check
     - `clippy`: cargo clippy with console feature

### Verification:
- `cargo build -p bm` — compiles clean (console now default)
- `cargo build -p bm --no-default-features` — compiles clean (opt-out works)
- `cargo clippy -p bm --features console -- -D warnings` — clean
- `cargo test -p bm --features console` — 121 tests pass
- `npm test` (vitest) — 78 tests pass
- Branch + commit + transition to dev:code-review needed
