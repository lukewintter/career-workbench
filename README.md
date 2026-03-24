# career-workbench

A personal system for managing your professional narrative — from raw career evidence through tailored CVs, cover letters, interview prep, and application tracking. Built for one human and the AI agents that help them.

You write the source material (who you are, what you've done, what you're targeting). Agents assemble it into tailored outputs for each opportunity. Every claim stays traceable to real evidence. Nothing is invented.

**If you are an AI agent working in this repo:** read `AGENTS.md` first. It is the source of truth for instructions.

---

## What you can do with this

- **Build your evidence base** — write win stories, update role files, promote reusable content
- **Apply for jobs** — start applications, research companies, build tailored CVs and cover letters
- **Run interview rounds** — prepare before, debrief after, capture feedback
- **Maintain and refine** — track applications, refresh your positioning as you learn what lands

The [Workflows](#workflows) section indexes each workflow with a short description. Workflow procedures live in `.agents/skills/`; `AGENTS.md` holds the rules and conventions agents follow.

---

## Key concepts

Understanding five things will orient you to the whole repo:

**Config** (`config/`) defines who you are (`me.md`), what you're targeting (`targets.md`), and the tag taxonomy (`tags.md`). Tags are how agents match your win stories to job ads — when generating a CV, the agent identifies themes in the job ad and retrieves win stories with matching tags. These files shape how agents frame every output.

**Role files** (`roles/`) provide context and framing for each job you've held. They describe what the company was, what you were hired to do, and what your scope looked like — but they don't duplicate achievement content. They point to win stories instead.

**Win stories** (`wins/`) are the foundation of all generated content. Each is a structured STAR account of something you achieved — situation, task, actions, results — tagged for retrieval. They are the primary source of truth for every claim in a CV or cover letter.

**Assets** (`assets/`) are promoted, reusable language blocks — CV paragraphs, cover letter body sections, interview answers. Content is promoted here deliberately once it's been polished and tested across applications. The bar: would you use it nearly verbatim in at least three different applications?

**Applications** (`applications/`) contain one folder per opportunity — the job ad, tailored CV, cover letter, company research, and round-by-round interview records. Generated outputs live here. Strong new content can be promoted back into `assets/` with your approval.

The flow: **config** shapes framing → **roles** provide context → **win stories** supply evidence → **assets** store reusable blocks → **applications** receive tailored outputs.

---

## Repo structure

```
career-workbench/
├── README.md              # Human orientation
├── AGENTS.md              # Agent instructions and strict rules
├── ROADMAP.md             # Build status and planned work for the repo (temporary)
├── tracker.md             # Cross-application status table
│
├── .agents/skills/        # Workflow skills (one folder per workflow)
│
├── config/
│   ├── me.md              # Identity, narrative, voice
│   ├── targets.md         # Role tracks, emphasis, filters
│   ├── tags.md            # Tag taxonomy for win stories
│   └── research-prompt.md # Canonical deep research prompt for company research
│
├── roles/                 # One file per job — context and framing only
├── wins/                  # One file per win story (STAR format, tagged)
│
├── assets/                # Promoted, reusable language blocks
│   ├── cv-boilerplate.md          # Fixed facts: name, contact, education
│   ├── cv-content.md              # Modular paragraphs and bullets, by role
│   ├── cover-letter-boilerplate.md   # Salutations and sign-offs
│   ├── cover-letter-content.md       # Openings, body blocks, closings
│   └── interview-answers.md          # Core narratives + track variants
│
├── applications/          # One folder per opportunity
│   └── company-role-yyyy-mm/
│       ├── job-ad.md              # Raw job description, preserved exactly
│       ├── application-notes.md   # Private: motivation, gut feel, red flags
│       ├── company-research.md    # Strategy, product, culture, key people
│       ├── cv.md                  # Tailored CV for this application
│       ├── cover-letter.md        # Tailored cover letter
│       └── R#-description/        # One folder per interview round
│           ├── prep.md            # Who, signals to send, prepped answers
│           ├── debrief.md         # What landed, what didn't, intel gathered
│           ├── feedback.md        # Decision: continuing or closed
│           ├── transcript.md      # Raw call transcript (optional)
│           └── summary.md         # AI-generated call summary (optional)
│
└── _templates/            # Copy from here to start anything new (for agents or humans)
```

---

## Getting started

### First-time setup

Think of setup in three phases:

1. **Define the frame** — create `config/me.md`, `config/targets.md`, `config/tags.md`, and `config/research-prompt.md` from `_templates/config/`.
2. **Build the evidence base** — add role files in `roles/` and win stories in `wins/`.
3. **Set up reusable outputs** — fill `assets/` and create `tracker.md`.

Everything starts from `_templates/`, and the order matters: tags should exist before you tag win stories, and win stories should exist before you turn them into reusable content. If you're using an agent, invoke `/setup-workbench` to walk through the full bootstrap sequence; you provide the substance and approve the results.

### After setup

Your evidence base is never truly done — continue to [build your evidence base](#build-your-evidence-base) as you uncover new win stories from past roles or gain new experience. When you're ready to pursue an opportunity, follow [apply for jobs](#apply-for-jobs).

---

## Working with agents

This repo is designed so that you direct AI agents (in Cursor, Claude, or any tool that reads `AGENTS.md`) and they do the assembly work. The system uses three layers: `AGENTS.md` defines rules and conventions, `.agents/skills/` contains workflow procedures, and `_templates/` provides output skeletons.

**Building evidence** is human-led — you write config, role files, and win stories. Agents can help draft and refine, but the voice and approval are yours.

**Applying and interviewing** is agent-driven — agents build tailored CVs, cover letters, and prep docs by assembling your evidence base against the job ad. You review everything before it's used.

**Invoking workflows** — agents will pick up the right skill automatically from context. In Cursor, you can also invoke any skill explicitly via `/skill-name` (e.g. `/write-win-story`, `/build-cv`). You can also direct agents with natural language; `AGENTS.md` ensures they follow the same rules either way.

**What agents will never do** (enforced by `AGENTS.md`):

- Write application outputs back into source files — generated content always goes in `applications/`
- Invent achievements or metrics not in your evidence base
- Include private sections (`## Reflection`, `## Timeline`) in any output
- Promote content to `assets/` without your approval

---

## Workflows

You can run the following workflows with natural language, or invoke them explicitly in Cursor via `/skill-name`. Workflow procedures live in `.agents/skills/`.

### Build your evidence base

- **Write a new win story** (`/write-win-story`) — Add a new numbered, tagged STAR file in `wins/` from `_templates/win-story.md`; end with `## Reflection` (private; never included in generated outputs).
- **Update a role file** (`/update-role`) — Align the right `roles/` file with reality: add dated `## Timeline` entries, refresh `## Key initiatives`, and link new evidence from `## Win stories`.
- **Promote content to assets** (`/promote-content`) — Move approved bullets or paragraphs into the correct `assets/` file when they’re ready to reuse, then log the promotion under `## Derived assets` on the source win story.

### Apply for jobs

- **Start a new application** (`/start-application`) — Copy `_templates/application/` to `applications/company-role-yyyy-mm/`, paste the raw job description into `job-ad.md`, and capture private notes in `application-notes.md`.
- **Research a company** (`/research-company`) — Fill `company-research.md` using the research prompt in `config/research-prompt.md` (often via a deep-research tool); start early so interview prep stays grounded.
- **Build a tailored CV** (`/build-cv`) — Build `cv.md` for that folder from the job ad, tags, win stories, and `assets/cv-content.md`, then verify every claim traces to evidence.
- **Build a cover letter** (`/build-cover-letter`) — Build `cover-letter.md` from `assets/cover-letter-content.md` and the job ad, then tune tone before you send.

### Run interview rounds

- **Prepare for a round** (`/prep-round`) — Copy `_templates/round/` into `applications/.../R#-description/`, record who you meet in `prep.md`, and request prep tailored to the round and interviewer.
- **Debrief after a round** (`/debrief-round`) — Record outcomes in `debrief.md` soon after the call; add `transcript.md` / `summary.md` if they exist, then log `feedback.md` once you know whether the process continues or stops.

### Maintain and refine the system

- **Update the tracker** (`/update-tracker`) — Sync `tracker.md` with each application’s status (e.g. applied, interview scheduled, round completed, offer, rejected, withdrawn); it’s the single cross-application view in the repo.
- **Refresh workbench** (`/refresh-workbench`) — Revisit `tracker.md`, `config/targets.md`, `assets/`, gaps in win stories, and `config/me.md` on a rhythm that fits you so targets and reusable copy match what you pursue and what lands.
- **Setup workbench** (`/setup-workbench`) — Bootstrap the repo from scratch: create config, role files, win stories, assets, and tracker from `_templates/`.

---

## Design principles

1. **Atomic evidence, composable outputs.** Small truth units — win stories, role context, promoted assets — assembled into different narratives depending on the target.
2. **Separate facts from framing.** Facts live in source files. Framing varies by target and lives in config and generated outputs.
3. **Every claim backed by a pointer.** CV bullets and cover letter paragraphs trace back to a win story or role file. No hallucination.
4. **Targets are lenses, not separate repositories.** Different role tracks are different emphases over the same base material.
5. **Promoted assets, not derived assets.** Content in `assets/` is promoted deliberately once polished. Never first drafts.
6. **Role files frame the story, win stories tell it.** Role files hold context, win stories hold achievements. No duplication.
7. **Don't build for problems that don't exist yet.** Start lean, add complexity when needed.
8. **Consistent structure over flexible structure.** Especially important for agent navigation.

---

## Best practices

- **Keep generated outputs contained** — application-specific outputs stay in `applications/company-role-yyyy-mm/`; source files remain your reusable evidence base.
- **Treat private sections as private** — never reuse content from `## Reflection`, `## Timeline`, or `application-notes.md` in outward-facing materials.
- **Version regularly** — commit after meaningful milestones, especially after writing win stories, setting up an application folder, or completing an interview round debrief.
- **Update roles and win stories while fresh** — Review and update your role files and win stories regularly (at least monthly or quarterly). Capture achievements, key initiatives, and impact while details are current—don't wait until you need them for an application.
- **Ask the agent to interview you** — Use the agent as an interviewer to help uncover new angles or overlooked impact in your past roles and win stories. Let it ask follow-ups, dig for specifics, and help you spot wins you’ve overlooked. You probably have more stories (and impact) than you realize — a good conversation can bring them to the surface.

---
