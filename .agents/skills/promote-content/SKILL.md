---
name: promote-content
description: >
  Promote proven content into the reusable assets library. Use this skill when
  the user wants to save a strong CV bullet, cover letter paragraph, or
  interview answer from a win story or application into assets/ for reuse
  across future applications. Also use when they mention graduating, promoting,
  or banking content.
---

# Promote Content

Start the response with "Using `promote-content` workflow"

## When to use

The user has identified a strong bullet, paragraph, or interview answer — from a win story or a generated application — and wants to promote it into `assets/` for reuse. This is a deliberate, approval-gated action: only promote content that's polished and tested.

## Required context

Read before starting:
- The source win story or application containing the content
- The target file in `assets/` where the content will go

## Steps

1. Identify the strong bullet, paragraph, or interview answer to promote.
2. Flag it for human review — explain why it's a good candidate for promotion.
3. If approved, add it to the correct `assets/` file with appropriate `tags` and `ws-refs`.
4. Update `## Derived assets` in the source win story to record the promotion.

## Gotchas

- Never promote content to `assets/` without explicit human approval.
- Always include `tags` and `ws-refs` when adding to an assets file — traceability is required.
- The bar for promotion: would you use this nearly verbatim in at least three different applications?
