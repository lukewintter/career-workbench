# What career-workbench is, and why

This is the why and the mental model — **read this first.** It explains what the workbench is for, the concepts it's built on, how you and AI agents divide the work, and the principles that shape the system itself. `README.md` covers how to stand it up and run it; `AGENTS.md` holds the rules agents follow.

career-workbench is a personal system for managing your professional narrative — from raw career evidence through tailored CVs, cover letters, interview prep, and application tracking. Built for one person and the AI agents that help them.

You write the source material (who you are, what you've done, what you're targeting). Agents assemble it into tailored outputs for each opportunity. Every claim stays traceable to real evidence. Nothing is invented.

---

## What you can do with this

- **Build your evidence base** — write win stories, update role files, promote reusable content
- **Apply for jobs** — start applications, research companies, build tailored CVs and cover letters
- **Run interview rounds** — prepare before, debrief after, capture feedback
- **Maintain and refine** — track applications, refresh your positioning as you learn what lands

Workflow procedures live in `.agents/skills/`; `AGENTS.md` holds the rules and conventions agents follow. `README.md` indexes each workflow with a short description.

---

## Key concepts

Understanding five things will orient you to the whole repo:

**Config** (`config/`) defines who you are (`me.md`), what you're targeting (`targets.md`), and the tag taxonomy (`tags.md`). Tags are how agents match your win stories to job ads — when generating a CV, the agent identifies themes in the job ad and retrieves win stories with matching tags. These files shape how agents frame every output.

**Role files** (`roles/`) provide context and framing for each job you've held. They describe what the company was, what you were hired to do, and what your scope looked like — but they don't duplicate achievement content. They point to win stories instead.

**Win stories** (`wins/`) are the foundation of all generated content. Each is a structured STAR account of something you achieved — situation, task, actions, results — tagged for retrieval. They are the primary source of truth for every claim in a CV or cover letter.

**Assets** (`assets/`) are promoted, reusable language blocks — CV paragraphs, cover letter body sections, interview answers. Content is promoted here deliberately, with your approval, once it's polished. Assets also hold **references**: past CVs and cover letters you'd still send. They set the style of new outputs (length, density, voice) but never supply claims.

**Applications** (`applications/`) contain one folder per opportunity — the job ad, tailored CV, cover letter, company research, interview intel, and round-by-round interview records. Generated outputs live here. Strong new content can be promoted back into `assets/` with your approval.

The flow: **config** shapes framing → **roles** provide context → **win stories** supply evidence → **assets** store reusable blocks → **applications** receive tailored outputs.

This flow is one-way during generation: source files feed applications, never the reverse. Application outputs never write back into your source evidence except through a deliberate, approved promotion step.

---

## Working with agents

This repo is designed so that you direct AI agents (in Cursor, Claude, Codex, Gemini, or any tool that reads `AGENTS.md`) and they do the assembly work. The system uses three layers: `AGENTS.md` defines rules and conventions, `.agents/skills/` contains workflow procedures, and `_templates/` provides output skeletons.

**Building evidence** is human-led — you write config, role files, and win stories. Agents can help draft and refine, but the voice and approval are yours.

**Applying and interviewing** is agent-driven — agents build tailored CVs, cover letters, and prep docs by assembling your evidence base against the job ad. You review everything before it's used.

**Invoking workflows** — agents will pick up the right skill automatically from context. In tools that support slash commands you can also invoke any skill explicitly via `/skill-name` (e.g. `/write-win-story`, `/build-cv`). You can also direct agents with natural language; `AGENTS.md` ensures they follow the same rules either way.

**What agents will never do** (enforced by `AGENTS.md`):

- Write application outputs back into source files — generated content always goes in `applications/`
- Invent achievements or metrics not in your evidence base
- Include private sections (`## Reflection`, `## Timeline`, `## Growth edges`) or anything from `application-notes.md` in any output
- Promote content to `assets/` without your approval

---

## Design principles

The lens for *modifying the system itself* — skills, structure, rules, templates. These are framing for meta-work (designing and refactoring the workbench), not rules for producing application content. Routine workflows don't load this section; it's read on demand via the trigger line in `AGENTS.md`.

1. **Atomic evidence, composable outputs.** Small truth units — win stories, role context, promoted assets — assembled into different narratives depending on the target.
2. **Separate facts from framing.** Facts live in source files. Framing varies by target and lives in config and generated outputs.
3. **Every claim backed by a pointer.** CV bullets and cover letter paragraphs trace back to a win story or role file. No hallucination.
4. **Targets are lenses, not separate repositories.** Different role tracks are different emphases over the same base material.
5. **Promoted assets, not derived assets.** Content in `assets/` is promoted deliberately once polished. Never first drafts.
6. **Role files frame the story, win stories tell it.** Role files hold context, win stories hold achievements. No duplication.
7. **Don't build for problems that don't exist yet.** Start lean, add complexity when needed.
8. **Consistent structure over flexible structure.** Especially important for agent navigation.
