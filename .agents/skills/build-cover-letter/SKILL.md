---
name: build-cover-letter
description: >
  Use when the user wants to create, generate, draft, tailor, revise, or
  finalize a cover letter for a job application, or write application form
  fields that sit alongside a cover letter/CV, such as interest, motivation,
  or relevant-experience questions.
---

# Build Cover Letter

Start the response with "Using `build-cover-letter` workflow"

## When to use

The user wants a tailored cover letter for a specific application. The application folder should already exist (via `start-application`) with a job ad in place.

## Read-set

| Source | Load | Selection rule |
|---|---|---|
| `config/me.md` | full | outward framing — voice authority |
| `config/targets.md` | full | outward framing — active track drives emphasis |
| application `job-ad.md` | full | the opportunity in flight |
| application `cv.md` | when it exists | align evidence/claims with the CV |
| application `application-notes.md` | full | private — informs decisions, never quoted |
| `assets/cover-letter-references/*.md` | full | real past letters — the ground truth for voice, tone, structure, and length. Benchmark every draft against these |
| `assets/cover-letter-boilerplate.md` | full | salutations / sign-offs |
| `assets/cover-letter-content.md` | full | promoted openings + body paragraphs; may be sparse — when it is, take voice and structure from `cover-letter-references` and draft fresh rather than forcing a thin block |
| application `company-research.md` | when it exists | grounding signals |
| application form fields / prompts / constraints | when provided | word/sentence limits, required vs optional |
| `wins/*.md` | tag-match | match job-ad themes via `config/tags.md` |

## Output structure

Calibrate voice, rhythm, and length against `assets/cover-letter-references/` — those real letters are the house style. `cover-letter-content.md` supplies promoted reusable blocks when present; treat it as a bonus, not a prerequisite.

Plain prose, minimal formatting. Build in this order:
1. Salutation ← `assets/cover-letter-boilerplate.md`.
2. Opening ← `assets/cover-letter-content.md` `## Openings` (or fresh copy with the user's confirmation).
3. Body ← one or more `## Body paragraphs` from `assets/cover-letter-content.md`, ordered and lightly adapted.
4. Closing ← `assets/cover-letter-content.md` `## Closings` (or fresh copy with the user's confirmation).
5. Sign-off ← `assets/cover-letter-boilerplate.md`.

## Steps

- [ ] Step 1: Decide output mode from the user's instruction and application context:
  - Cover letter only.
  - Application form fields only.
  - Cover letter + application form fields.
- [ ] Step 2: Decide length mode from the user's instruction and the application context.
  - Default target: roughly 200-300 words — match the length and density of `assets/cover-letter-references/`. Don't over-compress: squeezing past a compact note strips out the voice and proof that make these letters work.
  - Go compact (roughly 120-180 words) only when the user asks for a short note or a form constrains length.
  - Lead with the single strongest match; add a second evidence thread only when it answers a distinct high-priority job-ad signal.
- [ ] Step 3: Allocate evidence across the cover letter and application form fields.
  - Form fields should answer their exact prompts directly.
  - When drafting both a cover letter and form fields, the cover letter should add a materially different angle rather than repeat the same proof points.
  - Avoid reusing the same metric or win story across all pieces unless it is the only defensible evidence.
  - Prefer one distinct proof point per section so the application feels additive rather than repetitive.
- [ ] Step 4: For the opening — prefer reusing an existing opening from `assets/cover-letter-content.md`. If none fits, adapt the closest match. Blend only when two partial matches combine well. Draft fresh as a last resort — explain why existing patterns didn't fit and confirm with the user.
  - The opening should lead with the strongest job-relevant evidence, not the candidate's interest first.
  - Avoid presumptive value claims such as "I can help [Company] do X" or "you need X." Do not diagnose the company from the outside unless the job ad directly says it.
  - Prefer candidate-owned evidence patterns:
    - "The part of my background most relevant to this role is..."
    - "The closest match in my experience is..."
    - "A directly adjacent example from my background is..."
  - Avoid weak interest-led openings like "this role stands out to me" unless the user explicitly asks for that tone.
  - When the strongest match is obvious, state it plainly and concretely (e.g. direct domain/system experience) before adding narrative.
  - Avoid stating what the employer "is looking for" unless directly quoting or closely paraphrasing the job ad. Prefer candidate-owned framing such as "One angle I wanted to add is..." or "This is where I tend to do my best work..."
  - Make the case for fit from your own side, hedged — e.g. "I believe…" — and hold that register through the whole letter, not just the opening. Never assert what the role or company needs. The `cover-letter-references` model this voice.
  - When form answers already cover the obvious evidence, a useful cover-letter pattern is: "Beyond my CV and the answers above, I wanted to add one perspective on..."
- [ ] Step 5: Build body from `## Body paragraphs` matching role themes and required capabilities. Order for narrative flow.
  - In short mode, use one strong evidence story rather than a survey of the full CV.
  - For the primary evidence story, include:
    - Context/scope.
    - One concrete sentence on what the candidate actually did.
    - Measurable or observable result.
    - Brief transfer back to the role.
  - Keep the letter claim-light and evidence-heavy: the opening claim should never be the heaviest paragraph. Weight belongs in the proof.
  - End every evidence paragraph on an outcome, not a self-description. "I'm used to configuration where the details matter" is a claim wearing a proof costume; "it unblocked customers stuck in onboarding and opened larger accounts" is proof. A proof paragraph with no result is just a second claim — fix it or cut it.
  - State each relevance link once, where it lands hardest. Don't assert the same connection twice (e.g. a preview line in the intro and a "same shape" line in the body).
  - Frame the work by its impact, not its failure mode ("trade-offs that carry real weight for users," not "when a trade-off is wrong").
- [ ] Step 6: Draft application form field answers when requested.
  - Respect each field's word count, sentence count, and required/optional constraints.
  - Keep answers direct; do not use a cover-letter-style intro when the field asks a specific question.
  - If a field asks for relevant experience in 2-5 sentences, lead with evidence rather than a generic profile sentence.
- [ ] Step 7: If output includes a cover letter, choose salutation and sign-off from `assets/cover-letter-boilerplate.md`, tailor when a contact name is known, and select/lightly adapt a `## Closings` variant.
- [ ] Step 8: Keep evidence links via `ws-refs`; maintain `used-in` references when content is applied.
- [ ] Step 9: If drafting fresh content, state why existing blocks did not fit when presenting the draft.
- [ ] Step 10: Write output to `applications/.../cover-letter.md`. Follow the `## Output structure` above, writing final outward-facing prose (not scaffold headings) unless the user wants a structured working document. When writing both a cover letter and application form fields, keep them clearly separated in the file.
- [ ] Step 11: Flag blended or newly drafted blocks as candidates for promotion into `assets/cover-letter-content.md`.

## Drafting and revision cadence

- Prefer writing a complete first draft to `cover-letter.md` early, then iterate in the file so diffs and line comments can drive revisions.
- If the user iterates on wording, preserve approved wording exactly unless there is a claim-strength or grammar issue.
- If the user asks for alternatives to a sentence or paragraph, provide focused variants for that unit only instead of rewriting the whole letter.
- Do not leave template headings or instructions in the final letter.
- Final check: word count, no placeholders, no private-section leakage.
- Senior-tone final check:
  - First paragraph is evidence-led rather than interest-led or presumptive.
  - Proof paragraphs outweigh the opening claim, and each one lands an outcome rather than restating a claim.
  - One main proof point carries the letter unless the role clearly requires more.
  - Connection to the role is hedged and candidate-owned, never a claim about what the employer needs.
  - Generic phrases like "strong fit," "excited," "I can help," and "what you need" are removed or justified.
  - Voice, length, and structure read as consistent with `assets/cover-letter-references/`.
  - The letter reads like a senior note, not a broad career summary.
- For application form fields, final check each field separately: answers the prompt, respects constraints, avoids unsupported claims, and avoids duplicating cover-letter proof points unless intentional.
