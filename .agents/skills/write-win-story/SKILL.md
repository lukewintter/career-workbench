---
name: write-win-story
description: >
  Create a new win story in wins/. Use this skill when the user wants to
  document a career achievement, add a new STAR-format story, capture a win,
  or build their evidence base with a new accomplishment.
---

# Write Win Story

Start the response with "Using `write-win-story` workflow"

## When to use

The user wants to add a new career achievement to their evidence base — whether from a past role or recent work.

## Required context

Read before starting:
- `config/tags.md`
- The relevant role file in `roles/` for this win

## Steps

1. Copy `_templates/win-story.md` into `wins/`.
2. Name it `WS-###-short-title.md` using the next available number (zero-padded, e.g. `WS-001`).
3. Fill frontmatter: tags (2–3 from `config/tags.md`), role pointer, seniority, impact confidence.
4. Complete each section with specific facts over polish:
   - **One-liner**: outcome-first, plain English, one sentence
   - **Situation**: business/user context, problem/opportunity, why it mattered
   - **Task and my role**: goal, success criteria, constraints, mandate, collaboration
   - **Actions**: 3–7 most important moves or decisions with trade-offs
   - **Results and impact**: business outcomes with metrics where possible
5. Write `## Reflection` last (private, never exported).
6. Flag strong content for possible promotion into `assets/` (human decision).

## Gotchas

- Never export or quote the `## Reflection` section in any generated output.
- Do not invent metrics, outcomes, or achievements. If impact is missing, flag it and ask follow-up questions.
- Do not create new tags outside `config/tags.md`; suggest additions to the human instead.
