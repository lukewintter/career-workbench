# career-workbench — agent instructions

Use this file as the primary instruction file for agents in this repo.

Modifying the system itself — skills, structure, rules, templates? Read the `## Design principles` section in `PRODUCT.md` first. Design specs go in `docs/specs/YYYY-MM-DD-<topic>-design.md`; implementation plans go in `docs/plans/YYYY-MM-DD-<topic>.md`.

---

## Strict rules

### Output location and flow

- Put generated application outputs only in `applications/company-role-yyyy-mm/`.
- Keep content flow one-way during generation: source -> application.
- Source files (`config/`, `roles/`, `wins/`, `assets/`) are edited only when explicitly asked.

### Evidence and privacy

- Achievement and impact claims — especially metrics, outcomes, and causality — must be evidence-backed by a win story or role file.
- Ordinary factual career content (roles held, projects worked on, responsibilities) does not require a win story, but must be true and never invented or embellished.
- Prefer win stories over role files for achievement content.
- Use `config/tags.md` tags to select relevant win stories from `wins/`.
- When working with user-provided company or interview intel, preserve source excerpts verbatim by default. Put agent interpretation and draft phrasing in clearly labeled sections.
- Never quote, paraphrase, or reference private sections in generated outputs:
  - `## Reflection` in win stories
  - `## Timeline` in role files
  - `## Growth edges` in `config/me.md`
  - `application-notes.md` in application folders

### Do not do this

- Do not modify `README.md`, `config/me.md`, or `config/targets.md` unless explicitly asked.
- Do not create new tags outside `config/tags.md`; suggest additions to the user instead.
- Do not promote content to `assets/` automatically; flag candidates, but only promote with explicit approval.
- Do not invent metrics, outcomes, or achievements. If impact is missing, flag it and ask follow up questions to help fill gaps.

### Conventions

#### Parallel work and commits

- Before editing, announce the files you plan to touch.
- Stage files by exact path only. Do not use broad staging commands such as `git add .` or `git add -A` unless the user explicitly asks for a repo-wide commit.
- Before committing, check staged files and report any unrelated dirty or untracked files.
- Treat unrelated dirty or untracked files as work owned by the user or another agent; do not stage, modify, or revert them unless explicitly asked.

#### File naming

- Role files: `company-name-role.md` (lowercase, hyphenated)
- Win stories: `WS-###-company-short-title.md` (zero-padded, company name included, e.g. `WS-001-acme-short-title.md`)
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
| Create or update a role file | `.agents/skills/update-role/` |
| Promote content to assets | `.agents/skills/promote-content/` |
| Start a new application | `.agents/skills/start-application/` |
| Research a company | `.agents/skills/research-company/` |
| Capture interview intel | `.agents/skills/capture-interview-intel/` |
| Build a tailored CV | `.agents/skills/build-cv/` |
| Build a cover letter | `.agents/skills/build-cover-letter/` |
| Prepare for a round | `.agents/skills/prep-round/` |
| Debrief after a round | `.agents/skills/debrief-round/` |
| Critique an interview round | `.agents/skills/critique-round/` |
| Update tracker | `.agents/skills/update-tracker/` |
| Refresh workbench | `.agents/skills/refresh-workbench/` |

The `example/` folder is a synthetic workbench for humans to browse. Agents don't read it: it isn't source content, and it isn't a model for tone, content, or structure — the skills define structure and `config/me.md` defines voice.

---

## Style and framing

- When producing application content, match voice to `config/me.md` and emphasis to the active track in `config/targets.md`.
- The same win story can be framed differently for different tracks (for example, commercial vs platform).
- Avoid generic professional language.
