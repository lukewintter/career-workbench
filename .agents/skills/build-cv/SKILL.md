---
name: build-cv
description: >
  Build a tailored CV for a specific application. Use this skill when the user
  wants to create, generate, or draft a CV for a job they're applying to.
  Also use when they mention CV, resume, tailoring a CV, building a CV
  for an application, or revising/comparing existing CV versions.
---

# Build CV

Start the response with "Using `build-cv` workflow"

## When to use

The user wants a tailored CV for a specific application. The application folder should already exist (via `start-application`) with a job ad in place.

## Read-set

Load these before drafting. Each row states *what to load* and *the selection rule* — follow the rule, don't over-read.

| Source | Load | Selection rule |
|---|---|---|
| `config/me.md` | full | Voice + positioning; authority for `New:` drafting. Do **not** output the `## Growth edges` section (interview-prep only). |
| `config/targets.md` | full | Active track + cross-track filters; drives which framing/variant to select. |
| application `job-ad.md` | full | The opportunity in flight. |
| application `application-notes.md` | full | Private — informs decisions, never quoted (see AGENTS invariants). |
| `assets/cv-boilerplate.md` | full | Fixed facts (header, education, languages). |
| `assets/cv-content.md` | full | **Primary content source** — a variant menu. Per role: one paragraph variant → use it; several → select by tag-match to the job ad. Pull matching bullets from the role's `### Bullet pool`. |
| `wins/*.md` | all | Source-of-truth + fallback when `cv-content.md` lacks a block. Load all at current scale; switch to tag-matched loading once `wins/` exceeds ~25–30 files. |
| `assets/cv-references/*.md` | the 2 most recent (by filename date) | **Benchmark only** — style/length/density of the assembled whole. Not a content source. The user may name specific references instead. The user may instead name any prior CV — a `cv-references/*` file or a past `applications/*/cv.md` — as a baseline to adapt ("adapt a known-good CV"); the output still goes through variant selection, the rationale labels, and the Step 13–14 audits. |
| `roles/*.md` | selective | Only roles needing date/initiative gap-fill. |

## Drafting cadence

Draft and present sections sequentially — summary first, then each role newest-first — pausing for the user's approval between sections. This keeps rework local and lets the user redirect framing early, rather than discovering structural issues only after a finished doc lands.

For each drafted section, briefly state:
- source files used
- which job-ad signals the section answers
- language origin, using explicit labels:
  - `Reused:` copied or near-verbatim from `assets/cv-content.md`
  - `Blended:` adapted from multiple existing `assets/cv-content.md` blocks
  - `New:` newly drafted CV prose from win stories, role files, or job-ad fit reasoning

Any `New:` language must be called out before asking for approval so the user can inspect it deliberately.

This cadence is **never collapsed** — not for quick, validation, or clone-baseline builds. Batching sections into one "lean review" is the failure mode that lets unapproved language ship.

When the user approves a section, write it into the application `cv.md` immediately so the CV is locked incrementally.

## Output structure

Assemble the CV in this order; this is the canonical output shape (the old `cv.md` template held it):

1. **Header** — from `assets/cv-boilerplate.md` → `## Header`.
2. **Professional summary** — from `assets/cv-content.md` → `## Professional Summary`.
3. **Experience** — one block per role, **newest first**. Role heading style is `## **[Role] — [Company]**` (bold, matching every shipped CV and the `cv-references/` benchmarks). Under each: dates line, then prose from the matching `### Paragraph variants` block (when several variants exist, select by tag-match), then optional bullets selected from the role's `### Bullet pool`.
4. **Education** — from `assets/cv-boilerplate.md` → `## Education`.
5. **Languages** — from `assets/cv-boilerplate.md` → `## Languages`. Render as colon-separated sentences while preserving the boilerplate proficiency values exactly, e.g. `English: Native. Spanish: Professional working proficiency.`

Header, education, and languages must reproduce the `cv-boilerplate.md` facts **exactly** — no softening or omission (e.g. keep "Limited working proficiency", don't shorten to "working proficiency").

## Steps

- [ ] Step 1: Start with `assets/cv-boilerplate.md` for fixed sections (header, education, languages).
- [ ] Step 2: Calibrate against the **2 most recent** reference CVs in `assets/cv-references/` (by filename date) before drafting — unless the user names specific ones. Use them as **benchmarks only** (tone, density, role-section length, approximate word count of the assembled whole), not as a content source. Do not read all references.
- [ ] Step 3: Build a role signal map. Extract 5-8 important signals from the job ad, then map each to evidence from a win story, role file, asset block, or an explicit gap.
- [ ] Step 4: Infer dominant themes from the role signal map and match them to tags in `config/tags.md`.
- [ ] Step 5: Choose the best-fitting `## Professional Summary` variant(s) from `assets/cv-content.md`, or draft a compact summary when no suitable variant exists.
  - The summary should read like positioning, not a win-story preview. Avoid named case studies, metrics, or obvious evidence signals unless the user asks for them.
- [ ] Step 6: For each role, select the matching `### Paragraph variants` block. When a role has one variant, use it; when it has several, choose by tag-match to the job ad. Prefer reusing an existing variant; interrogate whether it genuinely fits before defaulting to it. If blending variants or drafting a meaningfully-better honest variant, label it and get approval (see drafting cadence).
- [ ] Step 7: From the role's `### Bullet pool`, select the subset whose tags match the job ad. Also create bullets when a single role spans multiple distinct engagements (e.g., a consultancy with several named client projects) — collapsing them hides credibility-building breadth.
- [ ] Step 8: If no suitable block exists, draft from `wins/` only, keep claims traceable via `ws-refs`, and confirm new language with the user.
- [ ] Step 9: Write output to the application folder following the `## Output structure` above. If the user asks for a new version, create `cv-vN.md`; only overwrite `cv.md` or an existing version when explicitly asked.
- [ ] Step 10: Run a style and length check against the 2 selected benchmark reference CVs. Prefer plain, confident language over job-ad-shaped keyword stuffing. Keep summaries compact: identity, strengths, tailored relevance. Default to the shorter end of the reference range — it's cheaper to expand on request than to defend verbosity.
  - Style/length tailoring must **not** silently reword a banked block. If a block needs different wording for this job, that is a `New:`/`Blended:` variant requiring approval (and a Step 14 promotion candidate) — never an inline edit to `Reused:` text.
  - Keep prose factual and concise, not conversational or prosaic. Cut metaphor and evocative framing (e.g. avoid "the messy intersection of…") and state plainly what was done.
  - Preserve ownership signals from source material. Do not compress away scope by turning "led the team" or "led product development" into wording that implies the user merely did the work individually.
  - Avoid vague responsibility nouns such as "business strategy" when a more concrete responsibility, action, or outcome is available.
- [ ] Step 11: Run a claim-strength audit. Check strong claims against their sources and soften wording when evidence is qualitative, indirect, or causality is uncertain.
- [ ] Step 12: Surface **evidence gaps** — claims in this CV that don't trace cleanly to a win story or role-file initiative. Recommend `write-win-story` or a `## Key initiatives` entry via `update-role`. (Reuse/promotion candidates are handled by the promotion audit in Step 14, not here.) Also flag taxonomy gaps in `config/tags.md` — agents must not add tags unilaterally.
- [ ] Step 13: Run the **provenance audit** — mechanically confirm every Summary/Experience block reproduces a `cv-content.md` block **verbatim**, and header/education/languages match `cv-boilerplate.md` facts exactly. Quick check: extract each block and `grep -F` it against `assets/cv-content.md`. Any deviation must be relabeled `New:`/`Blended:` and explicitly approved, or reverted to source. A "structurally identical" CV is not the bar — zero unapproved language is.
- [ ] Step 14: Run the **promotion audit** — invoke `promote-content` against the finished CV to reconcile it with the bank. This is the only path that writes to `assets/`. "Everything's already banked — nothing to promote" is a normal outcome.

## Revision workflow

When revising or comparing CV versions:
- Treat review/comparison as separate from editing unless the user asks for changes.
- Convert requested changes or review recommendations into an explicit checklist before editing.
- Preserve prior versions by creating the next `cv-vN.md` unless the user explicitly asks to modify an existing file.
- After editing, verify each checklist item with targeted readback or search.
- Report which items were applied, changed, or intentionally skipped.

## Gotchas

Repo-wide invariants (evidence-backing/no-invention, privacy of `## Reflection` / `## Timeline` / `application-notes.md`, tone-to-`me.md` / emphasis-to-`targets.md`) live in `AGENTS.md` and are always loaded — they are not restated here. This skill adds one sharpening:

- Be especially careful with AI depth, financial-system ownership, metrics, and causality — soften claims when evidence is qualitative, indirect, or causality is uncertain.
