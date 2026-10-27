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

## Read-set

| Source | Load | Selection rule |
|---|---|---|
| `config/me.md` | full | outward framing — voice |
| `config/targets.md` | full | outward framing — active track |
| application `job-ad.md` | full | the opportunity in flight |
| application `application-notes.md` | full | private — pull `## People / contacts` facts, never quoted in output |
| application `company-research.md` | when it exists | grounding signals |
| application `interview-intel.md` | when it exists | cross-round source signals |
| `assets/interview-answers.md` | full | reusable answer material |
| application `cv.md` / `cover-letter.md` | when they exist | align prep with submitted materials |
| prior round debriefs | when any exist | avoid repeating evidence; build on prior rounds |
| `wins/*.md` | tag-match | evidence selection for anticipated questions |

## prep.md structure

Build `prep.md` with these sections:
- **Round strategy** — round type, duration, the primary job of this round, depth to aim for, what to save for later rounds.
- **Signals to send (must-land)** — the few signals this round must leave behind.
- **Most relevant win stories** — one block per story. Lead each with a fenced `yaml` record carrying `ws-ref` (the `wins/WS-###-short-title.md` pointer) and `why-relevant-tags`, then the STAR detail and framing note.
- **Expected questions and answer scaffolding** — treat answers as scaffolding until calibrated in the user's voice. Split into "Most likely for this round" and "Backup if they probe deeper".
- **Questions to ask them** — split into "Priority for this round" and "Save for later rounds".

## Steps

1. Create the round folder in the application folder as `R#-description/` (e.g. `R1-talent-screen`, `R2-hiring-manager`).
2. Copy only `_templates/round/prep.md` into the new round folder.
3. Pull relevant interviewer/contact facts from `application-notes.md` `## People / contacts` into `prep.md`, then research the interviewer and populate `prep.md` with background, role, and likely focus areas.
4. Update `application-notes.md` `## Timeline and process` to reflect the scheduled/confirmed round, including date, stage, interviewer(s), and current stage when known.
5. Generate prep tailored to the specific round, duration, stage, and person — anticipated questions, signals to send, and relevant evidence from win stories.
   - For each selected win story, start with a short framing note before the STAR details that explains how the story matches the role, round, or interviewer concern (for example: `> How to frame it: This matches the role because...`). Then include situation, task, actions, impact, and usage guidance.
   - For expected questions, write answer scaffolding / calibration notes, not polished final wording, unless the user explicitly asks for final wording. Prefer cue-card bullets, answer spine, evidence to use, cautions, and optional phrases over complete speakable paragraphs. Label these sections `Answer scaffolding:` or equivalent.
6. Use `interview-intel.md` as cross-round source material when it exists. Preserve the distinction between source-backed interview signals, agent interpretation, and draft phrasing.

## Gotchas

- When starting a round, create only `prep.md`. Do not pre-create `debrief.md`, `feedback.md`, `summary.md`, or `transcript.md`; add those later only when those artifacts exist or the relevant workflow needs them.
- Use prior debriefs to avoid repeating the same evidence and to build on what's already been discussed.
- If interviewer details are discovered or corrected during prep, update `application-notes.md` `## People / contacts` only when the user asks or confirms; otherwise flag the suggested update.
- Keep `application-notes.md` `## Timeline and process` current whenever prep creates or confirms a round.
- Tailor prep to `round_type`, `duration_minutes`, interviewer role, and stage. A 30-minute recruiter screen should prioritize motivation, background, broad fit, values signals, logistics, compensation/package, process, and next steps.
- Save detailed product, team, system, and roadmap questions for hiring manager or team rounds unless the recruiter opens that door.
- Treat prepared answers as scaffolding or calibration drafts unless the user explicitly asks for final wording. Do not write answers as polished scripts by default; the prep should help the user choose the answer shape in the moment.
- Questions the user should ask interviewers may be polished and directly usable, but keep the distinction clear: interviewer questions can be exact wording, candidate answers should be scaffolding by default.
