---
name: update-tracker
description: >-
  Update the cross-application tracker. Use this skill when the user wants
  to sync tracker.md with application status changes, record a new status,
  or view and update the application pipeline. Also use when they mention
  updating the tracker, changing application status, or recording an outcome.
---

# Update Tracker

Start the response with "Using `update-tracker` workflow"

## When to use

The user explicitly asks to update `tracker.md`, or a round's `feedback.md` has recorded a conclusion that should be reflected in the cross-application view.

## Required context

Read before starting:
- `tracker.md`
- The relevant application's `feedback.md` (when triggered by a round outcome)

## Steps

1. Read `tracker.md` to see current application statuses.
2. Update the relevant application row to match the new status.
3. Use the controlled vocabulary for status values: applied, interview scheduled, round completed, offer, rejected, withdrawn, continuing, closed.

## Gotchas

- Do not update `tracker.md` unless explicitly asked, or when reconciling status after a round's `feedback.md` records an outcome.
- Use the status vocabulary consistently — don't invent new status labels.
- This is the single cross-application view in the repo; keep it accurate and current.
