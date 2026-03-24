---
name: setup-workbench
description: >
  Bootstrap a new career-workbench repo from templates. Use this skill when
  setting up the workbench for the first time, initializing config files, or
  when core source files are missing and need to be created. Also use when
  the user mentions first-time setup, onboarding, or getting started.
---

# Setup Workbench

Start the response with "Using `setup-workbench` workflow"

## When to use

The human is new to the repo or source files (`config/me.md`, `config/targets.md`, role files, win stories, assets) are missing and need to be bootstrapped from `_templates/`.

## Required context

Read the relevant template under `_templates/` before each copy step. As `config/` fills in, read those files for tone and constraints.

## Steps

Work in order — later steps depend on earlier ones.

- [ ] Step 1: Write `config/me.md` — copy from `_templates/config/me.md`. Identity, positioning, strengths, career narrative, voice.
- [ ] Step 2: Write `config/targets.md` — copy from `_templates/config/targets.md`. Role tracks, seniority targets, decision filters.
- [ ] Step 3: Define the tag taxonomy — copy `_templates/config/tags.md` to `config/tags.md`. Aim for 6–10 tags covering career themes.
- [ ] Step 4: Add the company research prompt — copy `_templates/config/research-prompt.md` to `config/research-prompt.md`. Domain-neutral baseline; customize if your searches need different framing (the `research-company` skill reads `config/research-prompt.md`).
- [ ] Step 5: Write role files — copy `_templates/role.md` into `roles/` for each job held (one file per role). Context and framing only; achievements go in win stories.
- [ ] Step 6: Write win stories — copy `_templates/win-story.md` into `wins/`. Start with the strongest 4–6 stories. Use the `write-win-story` skill for naming, frontmatter, and sections. Tag each with 2–3 tags from `config/tags.md`.
- [ ] Step 7: Populate boilerplate assets — copy `_templates/assets/cv-boilerplate.md` and `_templates/assets/cover-letter-boilerplate.md` into `assets/`. Fill fixed details: name, contact, education, salutations, sign-offs.
- [ ] Step 8: Populate content assets — copy `_templates/assets/cv-content.md`, `_templates/assets/cover-letter-content.md`, and `_templates/assets/interview-answers.md` into `assets/`. Replace example entries with the human's material (draft from win stories where needed; confirm before treating as final).
- [ ] Step 9: Create `tracker.md` — copy from `_templates/tracker.md` to the repo root.

## Gotchas

- Do not leave frontmatter fields empty; use `tbd` when unknown.
- Do not create new tags outside `config/tags.md`; suggest additions to the human instead.
- Never include first drafts in `assets/` — content must be polished and confirmed before treating as promoted.
