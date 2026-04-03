# Scratchpad

## 2026-04-03 Scan #1

### Board State (project 643, devguyio-agentic Board)

**Actionable items (project/botminter labeled, non-done):**

| Issue | Title | Status |
|-------|-------|--------|
| #106 | Transition BotMinter to Fully Agentic SDLC | po:design-review |
| #104 | Member directory name should not include role prefix | po:plan-review |
| #72 | Workspace git state management is fragile | po:backlog |
| #75 | Add a reopen workflow | po:backlog |
| #89 | bm start defaults to brain mode | po:backlog |
| #97 | Investigate generating profiles | po:backlog |

**PRs at po:accept (need human review):**
- PR #2, #3, #4 (botminter repo), PR #74 (team repo)

**Auto-advance check:** No items at `arch:sign-off` or `po:merge`. Nothing to auto-advance.

### Dispatch Decision

Epic priority table — first match: #106 at `po:design-review` → dispatch `po.review`

This is a human review gate. The po_reviewer hat will check for a human response comment. If found, it acts. If not, it returns control (non-blocking).

### po.review — Issue #106 (po:design-review)

**Human response found:** "rejected, added a comment on the PR" (2026-04-03T21:29:08Z)

**PR #107 feedback (6 points):**
1. Wrong assumption about early planning — `ralph plan` with AgentSOP was used from the start
2. Ambiguous scope — unclear if changes are to a BotMinter profile, scrum-compact divergence, or ad-hoc
3. Existing ADRs not accounted for
4. Planning artifacts are a mess (acknowledged fact)
5. Knowledge artifacts may not be the right place for ADRs/designs — open to rethinking
6. AI slop — suggesting ralph.yml changes is wrong (it's an upstream project)

**Operator guidance:** Think about BotMinter as a tool/framework. Dogfood BotMinter features to reach full agentic SDLC. Consider a new profile (e.g. "agentic team harness").

**Actions taken:**
- Posted rejection feedback comment on #106
- Transitioned #106: po:design-review → arch:design
- Architect must revise the design doc addressing all 6 points before resubmitting

## 2026-04-03 Scan #2 (po.review.done handling)

### Pending Event

`po.review.done` — #106 design review rejected. Status now `arch:design`.

### Dispatch Decision

#106 is at `arch:design` → dispatch `arch.design` to the Designer hat.
The designer must revise the design doc (PR #107) addressing all 6 rejection points:
1. Wrong assumption about early planning
2. Ambiguous scope
3. Existing ADRs not accounted for
4. Planning artifacts are a mess
5. Knowledge artifacts placement for ADRs/designs
6. AI slop (ralph.yml is upstream)

Operator guidance: Think of BotMinter as a tool/framework. Dogfood BotMinter features. Consider a new profile approach.

## 2026-04-03 Scan #3 (arch.design — Designer hat)

### Actions Taken

**Design doc revised (Revision 3)** — complete rewrite addressing all 6 rejection points:

1. Planning history corrected — acknowledged `ralph plan` + AgentSOP from start
2. Scope clarified — all changes are BotMinter product features via profile system
3. Integrated all 11 existing ADRs (ADR-0001, 0002, 0007, 0008 directly referenced)
4. Proposed canonical artifact organization (knowledge/ vs plans/ vs invariants/)
5. Clarified knowledge = on-demand context, designs stay in knowledge/designs/
6. Removed all ralph.yml change proposals; autonomy goes in botminter.yml

**Key reframing:** Entire design structured as BotMinter product features, not team-specific changes. Each gap maps to a profile enhancement. No upstream modifications.

**Committed and pushed** to PR #107 branch (`epic-106-design-doc`)
**Status transitioned:** arch:design → lead:design-review
**Emitting:** `lead.review` for lead_reviewer to review before human gate

## 2026-04-03 Scan #4 (lead.review — Lead Reviewer hat)

### Lead Review of Revision 3

**Design quality invariant:** All 6 required sections present with substantive content.
**6 rejection points:** All addressed — planning history corrected, scope explicit, ADRs integrated, artifact mess addressed, knowledge directory rationale clear, zero upstream changes.

**Key improvement:** Reframing as BotMinter product features shipped through the profile system. Each gap maps to a profile enhancement, not team-specific changes.

**Verdict:** APPROVED. Status: lead:design-review → po:design-review.
**Emitting:** `lead.approved` for coordinator to advance to human review gate.

## 2026-04-03 Scan #5 (lead.approved — Coordinator)

### Pending Event

`lead.approved` — #106 design doc revision 3 approved by lead reviewer. Status now `po:design-review`.

### Dispatch Decision

#106 is at `po:design-review` (human review gate). Dispatch `po.review` to the Review Gater hat.
The reviewer will check for a human response comment on the revised design (Revision 3).
If human has responded → act on approval/rejection.
If no response yet → non-blocking return, will re-check next scan cycle.

## 2026-04-03 Scan #6 (po.review — Review Gater hat)

### Issue #106 at po:design-review (Revision 3)

**Idempotency check:** No `📝 po` review request for revision 3 existed — only revision 2 request was present.

**Action:** Posted revision 3 design review request comment on issue #106.

**Human response check:** No human response found after the review request (just posted).

**Result:** Non-blocking return. Sent progress notification via RObot. Emitting LOOP_COMPLETE — waiting for human review on next scan cycle.
