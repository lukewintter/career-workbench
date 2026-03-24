---
name: build-cv
description: >
  Build a tailored CV for a specific application. Use this skill when the user
  wants to create, generate, or draft a CV for a job they're applying to.
  Also use when they mention CV, resume, tailoring a CV, or building a CV
  for an application.
---

# Build CV

Start the response with "Using `build-cv` workflow"

## When to use

The user wants a tailored CV for a specific application. The application folder should already exist (via `start-application`) with a job ad in place.

## Required context

Read before starting:
- `config/me.md`
- `config/targets.md`
- The application's `job-ad.md`
- The application's `application-notes.md`
- `assets/cv-boilerplate.md`
- `assets/cv-content.md`
- Relevant win stories in `wins/` (match via `config/tags.md`)

## Steps

- [ ] Step 1: Start with `assets/cv-boilerplate.md` for fixed sections (header, education, languages).
- [ ] Step 2: Infer dominant themes from `job-ad.md` and match them to tags in `config/tags.md`.
- [ ] Step 3: Choose the best-fitting `## Professional Summary` variant(s) from `assets/cv-content.md`.
- [ ] Step 4: For each role, select matching `### Paragraphs` blocks. Prefer reusing existing blocks. If blending is needed, notify the human and get approval before proceeding.
- [ ] Step 5: Include `### Bullets` only when they exist in the library and sharpen the CV.
- [ ] Step 6: If no suitable block exists, draft from `wins/` only, keep claims traceable via `ws-refs`, and confirm new language with the human.
- [ ] Step 7: Write output to `applications/.../cv.md` using the skeleton from `_templates/application/cv.md`.
- [ ] Step 8: Flag blended or newly drafted blocks as candidates for promotion into `assets/cv-content.md`.

## Gotchas

- Every claim must trace to a win story or role file — never invent achievements or metrics.
- Never include `## Reflection` (from win stories) or `## Timeline` (from role files) in the CV output.
- `application-notes.md` is private — use it to inform decisions, but never quote, paraphrase, or reference it in the CV.
- Match tone to `config/me.md` and emphasis to the active track in `config/targets.md`.
