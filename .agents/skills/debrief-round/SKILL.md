---
name: debrief-round
description: >
  Debrief after an interview round. Use this skill when the user has just
  finished an interview and wants to capture what happened, what landed,
  and what didn't. Also use when they mention debriefing, post-interview
  notes, or recording feedback from a round.
---

# Debrief Round

Start the response with "Using `debrief-round` workflow"

## When to use

The user has completed an interview round and wants to capture the debrief while it's fresh. This is a collaborative **session** — work through it together with the human.

## Required context

Read before starting:
- The relevant `prep.md` for this round
- The application's `job-ad.md`
- The application's `cv.md` (when it exists)
- The application's `cover-letter.md` (when it exists)
- The application's `application-notes.md`
- Prior round debriefs in the application folder (if any)
- The round's `transcript.md` (when it exists)
- The round's `summary.md` (when it exists)

## Steps

1. **Collect artifacts first.** Ask whether a transcript and/or summary are available. If yes, have the human provide or point you to them (e.g. paste, file path, or add `transcript.md` / `summary.md` in the round folder). If not, proceed without them — do not assume a recording exists.
2. **Review artifacts.** If `transcript.md` and/or `summary.md` are now available, read them in full so they are loaded in context before continuing.
3. **Fill in `debrief.md` together** — synthesize what was asked, what landed, what did not, company intel gathered, and gut feel. Use transcript/summary when available and the human's recall when not.
3. When feedback arrives, populate `feedback.md` and record whether the process is continuing or closed. If that outcome changes the application's status, update `tracker.md` (using the `update-tracker` skill).

## Gotchas

- Do not assume a transcript exists — always ask first.
- `debrief.md` should capture honest signal, not polish — what actually happened matters more than how it sounds.
- When updating `tracker.md` after feedback, only do so when `feedback.md` records a conclusion (continuing, closed, offer, rejected).
