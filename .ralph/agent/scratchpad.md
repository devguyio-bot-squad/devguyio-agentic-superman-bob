# Scratchpad

## 2026-04-07T14:38Z — Fresh iteration (task.start)

### Objective
Advance all actionable issues. TOP PRIORITY: issue #122 (backport controlPlaneVersion to release-4.21 and release-4.20).

### Board scan results
Issue #122 is at `dev:implement`. It's a hypershift project issue.

**Issue #122 state:**
- Backport branches exist: `backport-controlplaneversion-release-4.21` and `backport-controlplaneversion-release-4.20`
- Both pushed to origin with multiple commits (cherry-pick + fixes)
- NO PRs created yet
- The implementation work looks complete — branches have version gate fixes, test coverage, import fixes
- Next step: developer hat should verify tests pass, create PRs, then advance to `dev:code-review`

**Other actionable items (lower priority):**
- #121 at `bug:investigate` — bm fire bug
- #2, #3, #4, #74 at `po:accept` — waiting human review (skip)
- #104 at `po:plan-review` — waiting human review (skip)
- #106, #116, #118 at `po:design-review` — waiting human review (skip)  
- #114, #117, #119, #120 at `lead:design-review` — need lead review
- Various at `po:backlog` — lower priority

### Decision
Dispatch #122 to dev.implement first — it's top priority and closest to done.

## 2026-04-07T14:45Z — dev.implement for #122 COMPLETE

### Verification results
- **4.21 branch**: build ✓, CPO tests (23 pkgs) ✓, API tests ✓
- **4.20 branch**: build ✓, go vet ✓, CPO tests (23 pkgs) ✓, API tests ✓

### PRs (already existed)
- PR #2: backport to release-4.21 (OPEN, properly configured)
- PR #3: backport to release-4.20 (OPEN, properly configured)

### Status transition
- dev:implement → dev:code-review (verified via GraphQL)
- Emitting dev.code_review event for code reviewer hat

## 2026-04-07T15:00Z — Code review for #122 COMPLETE

### Review scope
- PR #2 (release-4.21): 52 files, +5099/-31
- PR #3 (release-4.20): 52 files, +5102/-29

### Findings
- API types: clean, proper markers, consistent patterns
- CPO reconciliation: CVO-ported semantics, clock injection, correct state machine
- Pruning: exact CVO constants, deterministic
- Propagation: DeepCopy, nil-safe
- E2E: properly version-gated per branch
- Tests: comprehensive coverage (8 CPO, 7 propagation, pruning, API)
- No issues found

### Status transition
- dev:code-review → qe:verify (verified)
- Emitting dev.approved event for QE verifier hat
