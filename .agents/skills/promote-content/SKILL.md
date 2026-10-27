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

The bank's **single writer and quality gate**. Runs in two ways:
- **Chained** — automatically at the end of a `build-cv` build (the promotion audit), against the finished CV.
- **Standalone** — to mine a CV you loved, graduate a strong block from a win story, or curate the bank (retire/merge).

`build-cv` and other skills never write to `assets/` — only this one does, and only on the user's explicit approval.

## What it does

1. **Detect** — diff the finished CV (or named source) against the current bank. List what is already banked (no action) vs net-new / blended language.
2. **Evaluate** — judge each net-new block against a **conservative bar: default is don't promote**. Promote only clearly canonical-grade or clearly reusable language. "Everything's already banked — nothing to promote" is a normal, common outcome.
3. **Decide in the moment** — present each candidate for a **promote / reject** call. **No deferral** ("deferred = never done"). Being rushed is safe: the zero-energy path is "no."
4. **Write** — for each approved block, add it to `assets/cv-content.md` as a new `#### Variant:` under the role (or the role's single block) with `tags` + `ws-refs`. Update each backing win story's `## Derived assets`.
5. **Curate** (standalone) — retire an outgrown block by **deleting it** from the bank (git keeps the history); merge near-duplicate variants.

## Required context

- The source CV / win story / reference being audited.
- `assets/cv-content.md` (the target bank) and `config/tags.md` (for tagging).

## Sources of promotable content

- **Win stories** — the primary source; `ws-refs` point back to them.
- **A finished or loved CV** — language that proved itself in a real build.
- **Reference CVs in `assets/cv-references/`** — approved phrasing (also the one-time seed source).

## ws-refs rules

`ws-refs` are bidirectional pointers — provenance AND the hook for pulling connected evidence into cover letters / interview prep. They point to win stories ONLY.

- One backing story: `ws-refs: [WS-001]`. Multiple: `ws-refs: [WS-001, WS-002]` (update each one's `## Derived assets`).
- No backing story yet: `ws-refs: []`, and flag the gap in your summary so the user can decide whether to write the win story.

## Gotchas

- This skill is the **only** writer to `assets/`. Never auto-promote — every write needs explicit approval.
- Per-block metadata is `tags` + `ws-refs` only. No `tier`, `source`, or usage fields.
- Retiring = deleting from the bank. There is no graveyard file.
- The old "usable in ≥3 applications" bar is retired — replaced by the conservative default-don't judgment above.
