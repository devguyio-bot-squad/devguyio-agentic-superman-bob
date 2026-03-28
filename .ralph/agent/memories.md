# Memories

## Patterns

## Decisions

## Fixes

### mem-1774691669-6e77
> status-transition.sh pagination bug: gh project item-list defaults to 30 items, so issues beyond that are not found. Workaround: use --limit 100 or resolve item ID separately with gh project item-list --limit 100. Fix: add --limit to the script's item-list call.
<!-- tags: github-project, tooling, pagination | created: 2026-03-28 -->

## Context
