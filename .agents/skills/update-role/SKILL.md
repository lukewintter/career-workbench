---
name: update-role
description: >
  Create or update a role file in roles/. Use this skill when the user wants
  to add a job they've held, add timeline entries, refresh key initiatives, or
  link new win stories to a role. Also use when they mention a job record or
  role history, and when setup-workbench creates role files.
---

# Create or Update a Role

Start the response with "Using `update-role` workflow"

## When to use

The user wants to create a role file for a job they've held, or update an existing one — adding timeline entries, refreshing initiatives, or linking new win stories.

## Required context

Read before starting:
- The role file in `roles/` being updated, or `_templates/role.md` when creating one
- Related win stories in `wins/`

## Steps

**Creating a role file:**

1. Copy `_templates/role.md` to `roles/company-name-role.md` (naming per `AGENTS.md`).
2. Fill the frontmatter and each section below from the user's answers or reference material they've confirmed. Ask about gaps, show the draft, and write it once the user approves.
3. Leave `## Timeline` empty unless the user gives entries, and list only win stories that already exist.

**Updating a role file:**

1. Add a dated entry to `## Timeline` (private, never exported).
2. Update `## Key initiatives` when work starts or concludes.
3. If new win material appears, create a win story (using the `write-win-story` skill) and add a pointer in `## Win stories`.

## Role file structure

Each role file carries these sections:

- **Company context** — stage, size, product area, market. What the company was.
- **Mandate** — what I was hired to do, what I owned, decision rights.
- **Scope** — product surface area, team size, reporting line, budget. Where this role began and ended.
- **Environment** — org shape and reporting line, team composition, culture, pace, constraints (org and technical). What made this place distinctive.
- **Key initiatives** — major initiatives and outcomes at a headline level: 1–3 bullets acting as a table of contents for win stories (see format below).
- **Signature themes** — 2–3 sentences on what this role best demonstrates overall. The frame, not the detailed achievements.
- **Win stories** — pointers only; links to relevant files in `wins/`.
- **Timeline** — private (never exported or quoted). Brief dated entries added while memory is fresh.

## Initiative bullet format

`## Key initiatives` bullets follow a consistent shape:

- **With a backing win story:** `- [Title] — [short description] → \`wins/WS-###-short-title.md\``
- **Without a win story yet:** `- [Title] — [short description]` (no arrow, no link). Use this for initiatives that are real and worth recording but don't have a polished win story written yet.

Both shapes are valid. The arrow + backtick link is the only difference. Don't invent filenames — if no file exists in `wins/`, use the bare-bullet form and (optionally) flag it as a candidate for `write-win-story`.

## One file per role, even within the same company

If multiple roles were held at the same company over time (e.g. a promotion, or a move between business units), each role gets its own file using the standard `company-name-role.md` convention. Don't fold multiple roles into one file as a multi-role timeline. Separate files keep frontmatter periods clean and let CV generation select a single role-block per role.

## Gotchas

- The `## Timeline` section is private — never export or quote it in generated outputs.
- Prefer `tbd` over invented context in body sections when a fact isn't sourced from a win story, reference CV, or the user.
