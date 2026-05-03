# opencore-mos15

OpenCore fork carrying patches we hope to upstream for the **mos**
project. Per the 2026-04-20 OpenCore pivot: this repo is now
**PR-staging only** — mos-docker switched to vanilla acidanthera 1.0.7
because our System KC patches are not on the M5 critical path.

This repo is one of several mos satellites. **Project context, current
state, mental model, build/deploy, and don't-do-this list all live in
the parent project's CLAUDE.md and library:**

- Airport map + working mode + current state: `../mos/CLAUDE.md`
- Standing rules: `../mos/memory/MEMORY.md`
- Pivot decision context: `../mos/memory/history/project_opencore_pivot_2026_04_20.md`

## Scope of this repo

Stages PRs against acidanthera/OpenCorePkg. Edits here must be
**upstream-clean** so commits can go upstream unchanged:

- Subsystem prefix in commit titles
- No personal paths
- No `Co-Authored-By: Claude` trailers (don't push attribution
  fixes to acidanthera-tracking remotes — ask first if you find any)
- Match OpenCore's debug-log prefix style

See `../mos/memory/feedback_upstream_submission.md` for the full
checklist.

PR #600 was already filed (memory of that lives in
`../mos/memory/history/feedback_pr_600_external.md`).
