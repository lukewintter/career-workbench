---
name: prep-round
description: >
  Prepare for an upcoming interview round. Use this skill when the user has
  an interview coming up and wants to create a prep folder, research the
  interviewer, or generate tailored preparation. Also use when they mention
  interview prep, getting ready for a round, or preparing for a call.
---

# Prep Round

Start the response with "Using `prep-round` workflow"

## When to use

The user has an interview round coming up and wants to set up the round folder, research the interviewer, and generate tailored prep.

## Required context

Read before starting:
- `config/me.md`
- `config/targets.md`
- The application's `job-ad.md`
- The application's `application-notes.md`
- `applications/.../company-research.md` (when it exists)
- `assets/interview-answers.md`
- The application's `cv.md` (if it exists)
- The application's `cover-letter.md` (if it exists)
- Prior round debriefs in the application folder (if any)

## Steps

1. Copy `_templates/round/` into the application folder.
2. Rename to `R#-description/` (e.g. `R1-talent-screen`, `R2-hiring-manager`).
3. Research the interviewer and populate `prep.md` with background, role, and likely focus areas.
4. Generate prep tailored to the specific round and person — anticipated questions, signals to send, and relevant evidence from win stories.

## Gotchas

- Never include `## Reflection` (from win stories) or `## Timeline` (from role files) in prep output.
- Round folders follow the naming convention `R#-description` (e.g. `R1-talent-screen`).
- Use prior debriefs to avoid repeating the same evidence and to build on what's already been discussed.
