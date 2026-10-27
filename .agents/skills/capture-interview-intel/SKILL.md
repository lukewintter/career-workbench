---
name: capture-interview-intel
description: >
  Use when the user provides or asks to gather hiring-process, recruiter
  guidance, culture, values, interview-stage, or candidate-evaluation
  material for a specific application.
---

# Capture Interview Intel

Start the response with "Using `capture-interview-intel` workflow"

## When to use

The user has interview-process, recruiter FAQ, hiring-stage, culture/value, or evaluation-signal material for a specific application. The material may be pasted by the user, linked from company pages, or gathered by the agent when explicitly requested.

Use this for cross-round interview intelligence source capture. Do not use it for company/product/market research; that belongs in `company-research.md`.

## Required context

Read before starting:
- The application's `job-ad.md`
- The application's `interview-intel.md` (create from `_templates/application/interview-intel.md` if missing)
- The application's `application-notes.md`
- The application's `company-research.md` (when it exists)
- `config/me.md`
- `config/targets.md`

## Output

- `applications/.../interview-intel.md`

## Steps

1. Identify the source material and source URLs/titles when available.
2. Preserve user-provided excerpts verbatim under `## Source excerpts` unless the user explicitly asks for summarization.
3. Keep `interview-intel.md` factual and source-backed. Do not add agent interpretation, prep advice, evidence recommendations, or answer phrasing.
4. When source material changes hiring timeline, process stage, next-step timing, or likely future stages, update `application-notes.md` `## Timeline and process` accordingly.
5. When source material introduces recruiters, hiring managers, interviewers, or likely future interviewers, add or update them in `application-notes.md` `## People / contacts` only when the user asks or confirms. Otherwise flag the candidate people update.

## Gotchas

- Source capture only.
- Preserve exact wording for pasted company/recruiter material by default.
- Label any unavoidable normalization clearly, such as corrected spellings or inferred titles, and keep it separate from source excerpts.
- Put subjective reactions, worries, and private gut checks in `application-notes.md`, not in `interview-intel.md`.
- Do not use `application-notes.md` as source material for outward-facing prep.
- Keep `application-notes.md` `## Timeline and process` current when interview intel includes process timing, stage changes, or next-step signals.
- Do not invent hiring stages, values, evaluation criteria, or interviewer expectations.
- If browsing or external research is requested, cite sources and keep quotes short enough for copyright compliance.
