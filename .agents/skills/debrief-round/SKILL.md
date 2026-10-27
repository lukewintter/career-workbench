---
name: debrief-round
description: >
  Debrief after an interview round. Use this skill when the user has just
  finished an interview and wants to capture what happened, what was asked,
  company intel, or raw post-interview notes. Also use when they mention
  debriefing, post-interview notes, transcripts, or recording feedback.
---

# Debrief Round

Start the response with "Using `debrief-round` workflow"

## When to use

The user has completed an interview round and wants to capture the source-backed record. This is a collaborative session: gather memory first, then incorporate transcript/summary artifacts when available.

## Read-set

| Source | Load | Selection rule |
|---|---|---|
| round `prep.md` | when it exists | what was planned for this round |
| application `job-ad.md` | full | the opportunity in flight |
| application `cv.md` / `cover-letter.md` | when they exist | what was submitted |
| application `application-notes.md` | full | private — process/contact context, never quoted |
| prior round debriefs | when any exist | continuity across rounds |
| round `transcript.md` / `summary.md` | when they exist | source-backed record of what was said |

## Outputs

- `debrief.md` — source-backed round record
- `questions.md` — extracted interviewer questions, for future question-bank reuse
- `feedback.md` — only when explicit post-round decision communication exists

Do not write performance critique or agent interpretation into `debrief.md`; use the `critique-round` workflow for `critique.md`.

Two optional reference artifacts may also exist in the round folder:
- `summary.md` — AI-generated summary, reference only. Do not treat it as source of truth over the handwritten `debrief.md`.
- `transcript.md` — raw transcript, reference only. Do not treat it as polished summary content.

## Steps

1. Collect memory first with guided questions: gut feel, rapport, what landed, what felt weaker, questions asked, company intel, and open threads.
2. Ask whether a transcript and/or summary is available. If yes, have the user provide it or point to the file. If not, proceed from memory and leave unsupported areas as `tbd`.
3. Review transcript/summary artifacts in full when available.
4. Write `debrief.md` as a source-backed record:
   - Memory debrief should preserve the user's ideas closely; light cleanup is fine, but do not reinterpret.
   - Transcript walkthrough should summarize questions and answers factually.
   - `How it landed` should be filled only from user memory or explicit transcript evidence; otherwise write `tbd`.
   - Company intel should contain only facts stated by the interviewer or explicit process communications.
   - Open threads should be phrased as questions, not conclusions.
5. Write `questions.md` with each interviewer question captured as a structured list. Keep this factual; do not analyze performance here.
6. Update `application-notes.md` `## Timeline and process` to mark the round completed and set the current stage accurately, such as completed awaiting feedback.
7. When feedback arrives:
   - Populate or append to `feedback.md` with the explicit post-round communication.
   - Use multiple dated entries when feedback is interim rather than final.
   - Update `application-notes.md` `## Timeline and process` with the current stage and next known or potential milestone.
   - If the outcome changes application status, update `tracker.md` using the `update-tracker` skill.
8. If feedback or process communication introduces future interviewers or contact details, add or update them in `application-notes.md` `## People / contacts` only when the user asks or confirms. Otherwise flag the candidate people update.

## Gotchas

- Blank spots are acceptable. `tbd` is better than unsupported inference.
- Never make the agent sound insightful by smoothing away uncertainty.
- Keep source-backed record and critique separate: `debrief.md` captures what happened; `critique.md` analyzes it.
- `feedback.md` captures explicit post-round decision communication, not verbal next steps during the interview.
- Interim recruiter signals can be logged in `feedback.md` when clearly labeled as interim and not treated as a final decision.
- Keep `application-notes.md` `## Timeline and process` current whenever a round is completed or post-round feedback/process communication arrives.
- When updating `tracker.md` after feedback, only do so when `feedback.md` records a status-relevant outcome.
