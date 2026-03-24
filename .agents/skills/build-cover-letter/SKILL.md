---
name: build-cover-letter
description: >
  Build a tailored cover letter for a specific application. Use this skill when
  the user wants to create, generate, or draft a cover letter for a job. Also
  use when they mention cover letter, writing to a company, or building a
  cover letter for an application.
---

# Build Cover Letter

Start the response with "Using `build-cover-letter` workflow"

## When to use

The user wants a tailored cover letter for a specific application. The application folder should already exist (via `start-application`) with a job ad in place.

## Required context

Read before starting:
- `config/me.md`
- `config/targets.md`
- The application's `job-ad.md`
- The application's `cv.md` (when it exists)
- The application's `application-notes.md`
- `assets/cover-letter-boilerplate.md`
- `assets/cover-letter-content.md`
- `applications/.../company-research.md` (when it exists)
- Relevant win stories in `wins/` (match via `config/tags.md`)

## Steps

- [ ] Step 1: Choose salutation and sign-off from `assets/cover-letter-boilerplate.md`; tailor when a contact name is known.
- [ ] Step 2: For the opening — prefer reusing an existing opening from `assets/cover-letter-content.md`. If none fits, adapt the closest match. Blend only when two partial matches combine well. Draft fresh as a last resort — explain why existing patterns didn't fit and confirm with the human.
- [ ] Step 3: Build body from `## Body paragraphs` matching role themes and required capabilities. Order for narrative flow.
- [ ] Step 4: Select and lightly adapt a `## Closings` variant.
- [ ] Step 5: Keep evidence links via `ws-refs`; maintain `used-in` references when content is applied.
- [ ] Step 6: If drafting fresh content, state why existing blocks did not fit and get human confirmation before use.
- [ ] Step 7: Write output to `applications/.../cover-letter.md` using the skeleton from `_templates/application/cover-letter.md`.
- [ ] Step 8: Flag blended or newly drafted blocks as candidates for promotion into `assets/cover-letter-content.md`.

## Gotchas

- Every claim must trace to a win story or role file — never invent achievements or metrics.
- Never include `## Reflection` (from win stories) or `## Timeline` (from role files) in cover letter output.
- `application-notes.md` is private — use it to inform decisions, but never quote, paraphrase, or reference it in the cover letter.
- Match tone to `config/me.md` and emphasis to the active track in `config/targets.md`.
