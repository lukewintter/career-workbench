---
name: refresh-workbench
description: >
  Review and refresh the workbench system. Use this skill when the user wants
  to audit their career materials, check for gaps, update positioning, or
  do a periodic review of targets and assets. Also use when they mention
  refreshing, auditing, reviewing the system, or checking what needs updating.
---

# Refresh Workbench

Start the response with "Using `refresh-workbench` workflow"

## When to use

The user wants a periodic review of their career materials — checking for patterns, gaps, and drift. Run on a rhythm that fits the user's job search activity.

## Required context

Read before starting:
- `tracker.md`
- `config/targets.md`
- `config/me.md`
- All files in `assets/`

## Steps

- [ ] Step 1: Review `tracker.md` for patterns — what's landing, what's not, any trends in outcomes.
- [ ] Step 2: Update `config/targets.md` to reflect focus shifts based on tracker patterns.
- [ ] Step 3: Audit `assets/` — identify content to promote, retire, or rewrite. Flag candidates for the user.
- [ ] Step 4: Identify missing win stories — look for achievements referenced in applications but not yet captured in `wins/`.
- [ ] Step 5: Check if `config/me.md` still reflects current positioning. Flag any drift.

## Gotchas

- Do not modify `config/me.md` or `config/targets.md` unless explicitly asked — flag recommendations instead.
- Do not promote content to `assets/` automatically; flag candidates for the user's approval.
