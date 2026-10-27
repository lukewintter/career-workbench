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
- The relevant application's `application-notes.md` when an application folder exists
- The relevant application's `feedback.md` (when triggered by a round outcome)

## Steps

1. Read `tracker.md` to see current application statuses.
2. Identify the corresponding application folder from the tracker row or user request.
3. Update the relevant application row to match the new status.
4. Check the corresponding `application-notes.md` and add a new entry to `## Timeline and process` for the same status change.
5. Use the controlled vocabulary from `tracker.md`:
   - Stage: `applied`, `screening`, `interviewing`, `offer`
   - Status: `awaiting-reply`, `action-needed`, `scheduled`, `closed`
   - Outcome: `accepted`, `rejected`, `withdrawn`, `ghosted`

## Gotchas

- Use the status vocabulary consistently — don't invent new status labels.
- `Stage` is the furthest point reached and should only move forward.
- `Status` is the current operational state.
- `Outcome` is blank until the process ends.
- This is the single cross-application view in the repo — the HQ view of all active and closed applications, answering "what's happening right now, and what do I need to do next?".
- Update whenever something changes — a reply received, a round scheduled, a decision made. Keep `last-updated` current so `awaiting-reply` status stays meaningful.
- Keep `application-notes.md` as the durable per-application history. If the matching notes file is missing, say so and still update `tracker.md`.
