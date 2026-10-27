---
name: critique-round
description: >
  Critique interview performance after a round debrief exists. Use this skill
  when the user wants analysis of what worked, what did not, how to improve,
  or how to prepare differently for the next interview round.
---

# Critique Round

Start the response with "Using `critique-round` workflow"

## When to use

The user wants interpretation or performance analysis after an interview round. This can happen immediately after `debrief-round` or later when preparing for the next round.

## Required context

Read before starting:
- The round's `debrief.md`
- The round's `questions.md` (when it exists)
- The round's `transcript.md` or `summary.md` (when they exist)
- The round's `feedback.md` (when it exists)
- Prior round debriefs/critiques in the application folder (if useful)
- The next round's `prep.md` (when using critique to support prep)

## Output

- `critique.md` — agent-assisted performance analysis for review

## Steps

1. Confirm there is a source-backed `debrief.md`. If not, run `debrief-round` first or ask the user for the missing memory/transcript context.
2. Analyze performance separately from the source record:
   - What likely worked
   - What likely did not work
   - Repeated patterns or missed opportunities
   - Improvements for the next round
   - Prep implications based on feedback or process signals
3. Write `critique.md` and mark it clearly as analysis for review, not canonical source truth.
4. Keep recommendations actionable and tied back to evidence from `debrief.md`, `questions.md`, transcript/summary, or feedback.

## Gotchas

- Do not rewrite the user's experience into false certainty.
- Use careful language for inference: "likely", "appears", "worth testing", or "for review".
- Do not put critique back into `debrief.md`.
- Treat `critique.md` as disposable agent synthesis: the canonical source record lives in `debrief.md`, and a point here that feels wrong, too strong, or not useful can be discarded.
- If source evidence is thin, say so and ask follow-up questions rather than filling gaps.
