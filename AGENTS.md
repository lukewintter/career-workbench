# career-workbench — agent instructions

Use this file as the primary instruction file for agents in this repo.

---

## Before doing anything

1. Read `README.md` in full.
2. Read `config/me.md` in full.
3. Read `config/targets.md` in full.
4. Load any extra context files needed for the current workflow.

---

## Strict rules

### Output location and flow

- Put generated application outputs only in `applications/company-role-yyyy-mm/`.
- Keep content flow one-way during generation: source -> application.
- Source files (`config/`, `roles/`, `wins/`, `assets/`) are edited only when explicitly asked.

### Evidence and privacy

- Every CV or cover letter claim must be evidence-backed by a win story or role file.
- Prefer win stories over role files for achievement content.
- Use `config/tags.md` tags to select relevant win stories from `wins/`.
- Never quote, paraphrase, or reference private sections in generated outputs:
  - `## Reflection` in win stories
  - `## Timeline` in role files
  - `application-notes.md` in application folders

### Do not do this

- Do not modify `README.md`, `config/me.md`, or `config/targets.md` unless explicitly asked.
- Do not create new tags outside `config/tags.md`; suggest additions to the human instead.
- Do not promote content to `assets/` automatically; flag candidates, but only promote with explicit approval.
- Do not update `tracker.md` except when explicitly asked, or when reconciling application status after a round's `feedback.md` records an outcome (continuing or closed).
- Do not invent metrics, outcomes, or achievements. If impact is missing, flag it and ask follow up questions to help fill gaps.

### Conventions

#### File naming

- Role files: `company-name-role.md` (lowercase, hyphenated)
- Win stories: `WS-###-short-title.md` (zero-padded, e.g. `WS-001`)
- Application folders: `company-role-yyyy-mm` (lowercase, hyphenated)
- Round folders: `R#-description` (e.g. `R1-talent-screen`, `R2-hiring-manager`)
- All filenames lowercase, hyphenated, no spaces

#### Frontmatter

- Role files and win stories must have complete YAML frontmatter.
- Do not leave frontmatter fields empty; use `tbd` when unknown.

---

## Workflows

Workflow procedures live in `.agents/skills/`. Use the table below to find the right skill.

| Workflow | Skill |
|---|---|
| Setup workbench | `.agents/skills/setup-workbench/` |
| Write a new win story | `.agents/skills/write-win-story/` |
| Update a role file | `.agents/skills/update-role/` |
| Promote content to assets | `.agents/skills/promote-content/` |
| Start a new application | `.agents/skills/start-application/` |
| Research a company | `.agents/skills/research-company/` |
| Build a tailored CV | `.agents/skills/build-cv/` |
| Build a cover letter | `.agents/skills/build-cover-letter/` |
| Prepare for a round | `.agents/skills/prep-round/` |
| Debrief after a round | `.agents/skills/debrief-round/` |
| Update tracker | `.agents/skills/update-tracker/` |
| Refresh workbench | `.agents/skills/refresh-workbench/` |

---

## Style and framing

- Match tone and style to `config/me.md` (avoid generic professional language).
- Match emphasis and vocabulary to the relevant track in `config/targets.md`.
- The same win story can be framed differently for different tracks (for example, commercial vs platform).
