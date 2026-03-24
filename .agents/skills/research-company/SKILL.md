---
name: research-company
description: >
  Research a company for interview preparation. Use this skill when the user
  wants to research a company they're applying to, fill in company-research.md,
  or prepare background intel before an interview. Also use when they mention
  company research, learning about a company, or interview prep research.
---

# Research Company

Start the response with "Using `research-company` workflow"

## When to use

The user wants to research a company for a specific application. Ideally done early — before interviews — so prep stays grounded in real signals.

## Required context

Read before starting:
- The job ad from the application folder (`applications/.../job-ad.md`)
- The application's `company-research.md` (to populate)

Read when running deep research:
- `config/research-prompt.md` — working copy of the research brief prompt (placeholders and section structure). **Bootstrap source:** `_templates/config/research-prompt.md`; setup copies it into `config/` so you can tailor it without changing the template.

## Steps

1. Read `config/research-prompt.md` for the full prompt template.
2. Substitute `[COMPANY]`, `[ROLE]`, and `[ROLE_TYPE]` with values from the job ad.
3. Append the full job ad text below the prompt.
4. Run the assembled prompt through a deep-research tool (or execute it directly if you have web access).
5. Write the research output into the application's `company-research.md`.

## Gotchas

- Cite sources throughout. Label confidence levels: **Source**, **Estimate**, **Inferred**, **Open question**.
- Do not guess financial figures, org structure, or pricing details — say explicitly when a credible source cannot be found.
- Prioritise signal over completeness. A sharp insight beats a comprehensive list.
