---
name: update-role
description: >
  Update an existing role file in roles/. Use this skill when the user wants
  to add timeline entries, refresh key initiatives, or link new win stories
  to a role. Also use when they mention updating a job record or role history.
---

# Update Role

Start the response with "Using `update-role` workflow"

## When to use

The user wants to update an existing role file — adding timeline entries, refreshing initiatives, or linking new win stories.

## Required context

Read before starting:
- The role file in `roles/` being updated
- Related win stories in `wins/`

## Steps

1. Add a dated entry to `## Timeline` (private, never exported).
2. Update `## Key initiatives` when work starts or concludes.
3. If new win material appears, create a win story (using the `write-win-story` skill) and add a pointer in `## Win stories`.

## Gotchas

- The `## Timeline` section is private — never export or quote it in generated outputs.
- Do not leave frontmatter fields empty; use `tbd` when unknown.
- Source files in `roles/` are edited only when explicitly asked.
