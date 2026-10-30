---
name: setup-workbench
description: >
  Bootstrap a new career-workbench repo from templates. Use this skill when
  setting up the workbench for the first time, initializing config files, or
  when core source files are missing and need to be created. Also use when
  the user mentions first-time setup, onboarding, or getting started, or wants
  to start from an existing CV, cover letters, or LinkedIn export.
---

# Setup Workbench

Start the response with "Using `setup-workbench` workflow"

## When to use

The user is new to the repo or source files (`config/me.md`, `config/targets.md`, role files, win stories, assets) are missing and need to be bootstrapped from `_templates/`.

## Required context

- Read the relevant template under `_templates/` before each copy step. As `config/` fills in, read those files for tone and constraints.

## How each step works

Work through the steps one at a time with the user, and get the user's approval on each step before starting the next. Later steps depend on earlier ones: win stories need tags and role files, and assets need win stories.

For each step, or each section of a config file:

1. **Gather.** Start from the reference materials sorted in Step 1, if any, and ask targeted questions about anything they don't cover. Treat any metric, outcome, or cause-and-effect claim in the materials as a question for the user, not a fact.
2. **Draft and refine.** Show a draft and revise it with the user. Expect several rounds. Fill only what the user said or confirmed; leave the rest `tbd` and ask, rather than filling gaps with plausible inferences (a motive, a preference, a philosophy).
3. **Approve and move on.** Write the file only after the user approves it, then tell the user what the next step is.

Never copy the raw documents into source folders; the approved reference copies in Step 10 are the only exception. Setup often spans several sessions: when resuming, check which steps' files already exist and confirm with the user where to pick up.

## Steps

- [ ] Step 0: Scaffold the runtime directories. Create any of `config/`, `roles/`, `wins/`, `assets/`, `applications/` that don't already exist, each with an empty `.gitkeep` so the structure survives a commit and clone. A fresh template ships none of these.
- [ ] Step 1: Read the reference materials. If `reference-materials/` holds documents, read each one (prefer `.md`/`.txt`; read PDF/`.docx` only if your tool can, otherwise ask the user to paste the text) and sort what you find, writing nothing yet: positioning and target themes (Steps 2–4), roles held (Step 6), achievements (Step 7), reusable phrasing (Step 9), and CVs or cover letters the user might keep as references (Step 10). If the folder is empty, ask once whether the user has an existing CV, cover letters, or a LinkedIn export to drop there first; if not, continue from scratch.
- [ ] Step 2: Write `config/me.md` — copy from `_templates/config/me.md`. Identity, positioning, strengths, career narrative, voice.
- [ ] Step 3: Write `config/targets.md` — copy from `_templates/config/targets.md`. Role tracks, seniority targets, decision filters.
- [ ] Step 4: Define the tag taxonomy — copy `_templates/config/tags.md` to `config/tags.md`. Aim for 6–10 tags covering career themes.
- [ ] Step 5: Add the company research prompt — copy `_templates/config/research-prompt.md` to `config/research-prompt.md`. Domain-neutral baseline; customize if your searches need different framing (the `research-company` skill reads `config/research-prompt.md`).
- [ ] Step 6: Write role files — for each job held, follow the `update-role` skill to create its file. One file per role. Context and framing only; achievements go in win stories.
- [ ] Step 7: Write win stories — for each story, follow the `write-win-story` skill end-to-end (template copy, `WS-###-company-short-title.md` naming, frontmatter, sections). Start with the strongest 4–6 stories. Tag each with 2–3 tags from `config/tags.md`.
- [ ] Step 8: Populate boilerplate assets — copy `_templates/assets/cv-boilerplate.md` and `_templates/assets/cover-letter-boilerplate.md` into `assets/`. Fill fixed details: name, contact, education, salutations, sign-offs.
- [ ] Step 9: Populate content assets — copy `_templates/assets/cv-content.md`, `_templates/assets/cover-letter-content.md`, and `_templates/assets/interview-answers.md` into `assets/`, replacing their example entries. Add blocks through the `promote-content` skill (the only writer to the bank), drawing on win stories and the phrasing sorted in Step 1.
- [ ] Step 10: Save reference CVs and cover letters. For each CV or cover letter from Step 1 that the user would still send, save a markdown copy of its text to `assets/cv-references/` or `assets/cover-letter-references/`, named `YYYY-MM-DD-company-cv.md` or `YYYY-MM-DD-company-cover-letter.md` (the date it was sent; ask if unknown). `build-cv` and `build-cover-letter` use these as their model for length, density, and voice, and `promote-content` may lift wording from them — so save only documents whose claims were settled in Steps 6–7. If some of a document's claims weren't, name them to the user and save it once they are.
- [ ] Step 11: Create `tracker.md` — copy from `_templates/tracker.md` to the repo root.
- [ ] Step 12: Offer to delete `example/`. It exists for browsing before setup; afterwards it only adds noise to searches.

## Gotchas

- Never fabricate config content. Positioning, strengths, narrative, voice, targets, and tags come only from the user's answers or reference material they've confirmed; prefer `tbd` over a plausible guess.
- Never include first drafts in `assets/` — content must be polished and confirmed before treating as promoted.
