---
name: write-win-story
description: >
  Create or update a win story in wins/. Use this skill when the user wants to
  document a career achievement, add a new STAR-format story, capture a win,
  build their evidence base with a new accomplishment, or reframe an existing
  win story for a specific role or application. Also trigger when the user says
  things like "let's write up that project", "add this to my wins", "capture
  what I did at [company]", or "document this experience".
---

# Write Win Story

Start the response with "Using `write-win-story` workflow"

## When to use

The user wants to add a new career achievement to their evidence base, or update an existing one — whether from a past role or recent work.

## Required context

Read before starting:
- `config/tags.md`
- The relevant role file in `roles/` for this win
- `_templates/win-story.md` for the current template structure

## Source-of-truth rules

The role file in `roles/` is the canonical factual record for each win story. Win stories structure and frame those facts into narratives — they don't add new facts. If a detail isn't in the role file, it doesn't belong in the win story unless the user provides it in conversation.

These rules exist because the win stories are the user's career evidence base. If a story contains details the user didn't actually say, it becomes unreliable — and unreliable evidence is worse than missing evidence, because the user might repeat fabricated details in an interview without realizing it.

1. **The role file is the primary source.** Every factual claim in a win story should trace back to the relevant role file or to details the user explicitly provided in conversation. Do not fill gaps with plausible-sounding content, even if it seems reasonable. This includes context, motivations, cause-and-effect reasoning, and characterizations of situations — not just metrics.
2. **Do not embellish or editorialize.** Stick to what was said. If something needs a "why" or an interpretive frame, ask. A common failure mode is inferring the problem from a stated solution (e.g., if the user says they "improved operational visibility," don't write "the problem was limited visibility" unless they said that).
3. **Flag gaps with `<!-- OPEN Q: ... -->` comments.** When a section has missing information, insert a comment describing what's needed. This is better than leaving the field blank because it tells the user exactly what to fill in. Alternatively, stop and ask the user directly before writing.
4. **Reflections are private.** The `## Reflection` section is the user's personal space. Never fill it in unless the user explicitly asks. Always leave it with empty placeholder fields.
5. **When in doubt, ask.** If you're unsure whether a detail came from the user or from your own inference, stop and check before writing it.
6. **Win story vs role file boundary.** The role file's `Key initiatives` section carries a one-line pointer plus a link to the win story. The win story carries the full narrative shape — situation, scale, actions, results. If a fact materially changes the story (scale numbers, executive visibility, follow-through duration), it goes in the win story; the role file just summarises and links.
7. **When updating, preserve existing sourced facts.** Treat the current win story as source material, not disposable draft copy. New framing should be consolidated with existing facts unless the user explicitly asks to remove, narrow, or replace them. Do not drop audience, scope, impact, constraints, before-state details, or strategic context just because a sharper phrase is introduced.

## Steps

### Step 1: Gather source material

Before writing anything, read the relevant role file in `roles/` — this is the primary factual source. Then collect any additional material:
- Any existing win story file being updated
- Round transcripts in `applications/<app>/<round>/transcript.md` when they exist — these capture how the user told the story live, with quotes and concrete colour the role file does not carry
- Raw notes or excerpts the user has shared
- Details from the current conversation

When updating an existing win story, identify the factual atoms already present before rewriting: audience, before-state, problem, constraints, role/ownership, actions, results, strategic context, and variants. These are facts to preserve unless explicitly superseded.

### Step 2: Identify gaps and ask questions

Review the source material against the template structure. For each section, note what you have and what's missing. Then ask the user targeted questions to fill the gaps — especially around:
- Their specific role and decision rights (don't assume)
- Success criteria (they may not have had formal ones)
- Key trade-offs and why they made them
- Who the users and stakeholders were
- Measurable results (don't invent these — ask)
- **Scale and scope** — team count, customer count, deal count, time elapsed, money on the line. Specific numbers are what give the reader an anchor for how big the work was; without them the story floats.
- **Executive visibility** — who saw the work (CPO/CTO/board readouts, leadership presentations). The most senior audience is often the strongest credibility signal and the easiest detail to forget.
- **Sustaining work and follow-through** — was this a one-off, or did the work continue? For how long, in what form? "Ran a workshop" and "ran a workshop and sustained the standing group for six months" are very different stories.

Do not proceed to drafting until you've asked about the gaps you've identified. It's fine to batch questions rather than asking one at a time.

### Step 3: Draft the win story

1. Copy `_templates/win-story.md` into `wins/`.
2. Name it `WS-###-company-short-title.md` using the next available number (zero-padded, e.g. `WS-001-acme-short-title.md`).
3. Fill frontmatter: tags (2–3 from `config/tags.md`), role pointer, seniority, impact confidence.
4. Complete each section using only sourced details:
   - **One-liner**: outcome-first, plain English, one sentence
   - **Situation**: business/user context, problem/opportunity, why it mattered
   - **Task and my role**: goal, success criteria, constraints, mandate, users/stakeholders, collaboration
   - **Actions**: 3–7 most important moves or decisions with trade-offs
   - **Results and impact**: business outcomes with metrics where possible, confidence flagged inline. Each bullet should carry a fact that only applies to this story — a number, a named audience, a decision that was made, a behaviour that changed, an artifact that exists. Generic outcome language ("generated momentum", "created shared clarity", "established a way of working") fails a simple test: if the bullet would survive being copy-pasted into an unrelated win story, it isn't carrying any information and should be cut or made specific. This is a different failure mode from inventing facts — these bullets are technically true, but they're true of every successful project, so they don't tell the reader anything.
   - **For updates**: prefer consolidation over replacement. If new language is sharper, merge it with the existing facts instead of swapping the old sentence out wholesale. A rewritten line should usually carry at least the same factual load as the original, plus the new framing. Variants can reframe emphasis, but they are not a substitute for preserving core evidence in the main story.
5. Leave `## Reflection` empty with placeholder fields.
6. Leave `## Derived assets` as "None yet." unless the user has already created derived content.

### Step 4: Write variants (if applicable)

If the user is writing this story for a specific application or role type, or asks for variants:

1. Add a `## Variants` section after Results and impact.
2. Each variant is a strategic reframing brief — not polished copy. It contains:
   - Target role type
   - Reframed one-liner
   - Which 2–3 actions to lead with
   - What to downplay or omit
   - Which result to emphasize
   - Strategic notes on why this framing works
3. Variants use the same underlying facts as the main story — they change emphasis, not substance.
4. The user may request variants at the time of writing or add them later.

### Step 5: Verify against sources

After drafting, do a self-audit:
- For each factual claim in the story, can you trace it back to the role file or to something the user said in conversation?
- Flag anything you're not sure about. Present these flags to the user: "I included X — did you say this, or did I infer it?"
- If the user provided new factual details in conversation that aren't in the role file, flag these separately — the user should decide whether to add them back to the role file so it stays the canonical record.
- For updates, compare before vs. after:
  - Did any existing sourced fact disappear?
  - If yes, was it intentionally removed, moved to another main-story section, or explicitly superseded by the user?
  - Do not count moving a fact only into `## Variants` as preserving it unless the user asked for that. Variants change emphasis; the main story remains the canonical evidence.
  - If a rewrite narrows the story's audience, scope, impact, or before-state, stop and ask.
- This step matters. It's the difference between a reliable evidence base and one that subtly drifts from reality.

## Gotchas

- Never fill in `## Reflection` unless the user explicitly asks. This is their private thinking space.
- Do not invent details of any kind — not metrics, not context, not motivations, not characterizations. If impact is missing, flag it with `<!-- OPEN Q -->` and ask.
- Do not create new tags outside `config/tags.md`; suggest additions to the user instead.
- Variants are strategic reframing briefs, not polished copy. Polished copy belongs in derived assets.
- Derived assets are tracked but created separately — don't generate them as part of this workflow unless the user asks.
- If the user shares new facts during the conversation that aren't in the role file, flag them for the user to decide whether to update the role file. The role file should remain the canonical factual record.
