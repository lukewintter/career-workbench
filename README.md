# career-workbench

A personal system for managing your professional narrative — from raw career evidence through tailored CVs, cover letters, interview prep, and application tracking. You write the source material; AI agents assemble it into tailored outputs for each opportunity, with every claim traceable to real evidence and nothing invented.

> **Read [PRODUCT.md](PRODUCT.md) first** for the mental model — what the workbench is, the five core concepts, how you and agents divide the work, and the principles behind it. This README is the how: stand it up and run it.

---

## Quickstart

This repo is a **template**. You create your own private copy, open it in your AI tool, and fill it with your own career material — the folders for that material don't exist yet; setup creates them.

1. **Use this template → choose Private.** On the public repo, click **Use this template** → **Create a new repository**, and set visibility to **Private**. Your workbench holds personal career data, so it must be private. This gives you a clean, standalone repo with no fork relationship.
2. **Open it in your AI tool.** Open the repo folder in an agent that reads `AGENTS.md` — for example Claude Code, Codex, Cursor, or GitHub Copilot. The rules and workflows load from the repo itself; there's nothing to configure. If something doesn't respond as expected, see [Troubleshooting](#troubleshooting).
3. **Recommended — start from what you already have.** Drop your current CV, past cover letters, or a LinkedIn export into `reference-materials/`, and read [reference-materials/README.md](reference-materials/README.md) for what happens next. Setup uses them as a starting point, and you confirm everything before it's written. CVs and cover letters you'd still send are kept as [references](#references) that future ones are modelled on. Your raw documents stay uncommitted. No documents? Setup starts from scratch.
4. **Run setup.** Ask your agent to set up the workbench (or type `/setup-workbench`). It walks you through building your foundation step by step — config, role files, win stories, reusable assets — drawing on anything in `reference-materials/` and asking you about the rest. Each step is refined with you and approved before the next one starts. It's a long conversation, so you can stop after any step and pick up again in a later session.

Browse the [`example/`](example/) folder to see the shape of a filled workbench before you start. Delete it whenever you like.

---

## Repo structure

What's included in the template (before you run setup):

```
career-workbench/
├── README.md              # This file — how to stand it up and run it
├── PRODUCT.md             # The why and the mental model — read first
├── AGENTS.md              # Agent instructions and strict rules
├── CLAUDE.md              # Points Claude Code at AGENTS.md
├── LICENSE                # MIT
├── .gitignore             # Keeps OS, editor, and local-settings clutter out of git
│
├── .agents/skills/        # Workflow skills (one folder per workflow)
├── .claude/skills/        # Links to .agents/skills/ so Claude Code finds them
├── _templates/            # Copy from here to start anything new (for agents or humans)
│
├── example/               # A synthetic, filled workbench to browse — then delete
└── reference-materials/
    ├── README.md          # Drop existing CVs/cover letters here for setup to start from
    └── .gitignore         # Keeps your dropped documents out of git
```

Setup creates your runtime folders (these are **not** in the template — you build them):

```
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
│   ├── interview-answers.md          # Core narratives + track variants
│   ├── cv-references/                # Past CVs you'd still send (see References below)
│   └── cover-letter-references/      # Past cover letters you'd still send
│
├── applications/          # One folder per opportunity
│   └── company-role-yyyy-mm/
│       ├── job-ad.md              # Raw job description, preserved exactly
│       ├── application-notes.md   # Private: motivation, gut feel, red flags
│       ├── company-research.md    # Strategy, product, culture, key people
│       ├── interview-intel.md     # Hiring process, values, interview signals
│       ├── cv.md                  # Tailored CV for this application
│       ├── cover-letter.md        # Tailored cover letter
│       └── R#-description/        # One folder per interview round
│           ├── prep.md            # Who, signals to send, prepped answers
│           ├── debrief.md         # What landed, what didn't, intel gathered
│           ├── feedback.md        # Decision: continuing or closed
│           ├── transcript.md      # Raw call transcript (optional)
│           └── summary.md         # AI-generated call summary (optional)
│
└── tracker.md             # Cross-application status table
```

The order matters: tags should exist before you tag win stories, and win stories should exist before you turn them into reusable content. `setup-workbench` walks the full sequence.

### References

References are past CVs and cover letters you'd still send, saved as markdown in `assets/cv-references/` and `assets/cover-letter-references/`. Setup offers to save them from what you drop in `reference-materials/`; you can add more any time, named like `2026-05-01-company-cv.md`.

- **They set the style, not the facts.** `build-cv` matches the length and density of your two most recent reference CVs. `build-cover-letter` matches the voice, structure, and length of your reference letters. Neither takes claims from them — claims come only from your win stories and role files.
- **Their wording can be promoted.** `promote-content` can lift a strong phrase from a reference into your reusable blocks, with your approval.
- **Without them, outputs still work** — voice then comes from `config/me.md` alone, which is a weaker model of how you write.

---

## Workflows

You can run the following workflows with natural language, or invoke them explicitly via `/skill-name` where your tool supports it. Workflow procedures live in `.agents/skills/`.

### Build your evidence base

- **Write a new win story** (`/write-win-story`) — Capture an achievement as a tagged STAR story in `wins/` — the evidence behind every claim.
- **Create or update a role file** (`/update-role`) — Add a job you've held, or keep a role's context, scope, and key initiatives current and link new evidence to it.
- **Promote content to assets** (`/promote-content`) — Move proven language from a finished CV, a win story, or a reference into your reusable `assets/` library, with your approval.

### Apply for jobs

- **Start a new application** (`/start-application`) — Spin up an `applications/` folder for an opportunity, with the job ad and your private notes.
- **Research a company** (`/research-company`) — Build a research brief on the company (often via a deep-research tool) so prep stays grounded.
- **Capture interview intel** (`/capture-interview-intel`) — Optional step to capture hiring process, values, and interview signals — usually when the company has rich material publicly available.
- **Build a tailored CV** (`/build-cv`) — Assemble a tailored CV from your evidence base and pre-approved assets (`assets/cv-content.md`), with every claim traceable. Length and density follow your two most recent [reference](#references) CVs.
- **Build a cover letter** (`/build-cover-letter`) — Draft a cover letter tuned to the role and company, in the voice, structure, and length of your [reference](#references) letters.

### Run interview rounds

- **Prepare for a round** (`/prep-round`) — Prepare for a round: who you'll meet, likely questions for the stage, and prepped answers — informed by any previous rounds.
- **Debrief after a round** (`/debrief-round`) — Capture how a round went and the intel gathered, add a transcript or summary if you have one, and record whether the process continues.
- **Critique an interview round** (`/critique-round`) — Get a candid critique of how a round went and where to sharpen for next time.

### Maintain and refine the system

- **Update the tracker** (`/update-tracker`) — Sync `tracker.md`, your single cross-application status view, with each application.
- **Refresh workbench** (`/refresh-workbench`) — Periodically revisit targets, assets, and win-story gaps so the repo matches what you're pursuing.
- **Setup workbench** (`/setup-workbench`) — Bootstrap the whole repo from `_templates/` by interviewing you, starting from anything in `reference-materials/` and saving the CVs and letters you'd still send as references.

---

## Best practices

- **Keep generated outputs contained** — application-specific outputs stay in `applications/company-role-yyyy-mm/`; source files remain your reusable evidence base.
- **Treat private sections as private** — never reuse content from `## Reflection`, `## Timeline`, `## Growth edges`, or `application-notes.md` in outward-facing materials. The reflection, timeline, and growth-edge sections are optional — fill them if they help you. `application-notes.md` is different: the workflows keep its timeline and contacts current, so it's private but not optional.
- **Version regularly** — commit after meaningful milestones, especially after writing win stories, setting up an application folder, or completing an interview round debrief.
- **Update roles and win stories while fresh** — review and update your role files and win stories regularly (at least quarterly). Capture achievements, key initiatives, and impact while details are current — don't wait until you need them for an application.
- **Ask the agent to interview you** — use the agent as an interviewer to help uncover new angles or overlooked impact in your past roles and win stories. Let it ask follow-ups, dig for specifics, and help you spot wins you've overlooked. You probably have more stories (and impact) than you realize — a good conversation can bring them to the surface.

---

## Troubleshooting

### Workflows don't seem to run

Every workflow announces itself: a reply that starts with **"Using `setup-workbench` workflow"** (or the matching workflow name) means it loaded. If you ask your agent to set up the workbench and the reply doesn't start that way:

- **Start the session with "Read AGENTS.md and follow it."** Its workflow table points the agent to each skill, so plain-language requests work even when slash commands don't.
- **Slash commands missing?** Skills ship in `.agents/skills/` (read by Codex, Cursor, GitHub Copilot, and Gemini CLI) and `.claude/skills/` (Claude Code). If your tool uses another folder, check its docs.
- **Gemini CLI** reads `GEMINI.md` by default. Point it at `AGENTS.md` with the `context.fileName` setting.
- **Windows:** `.claude/skills/` uses symlinks. If they arrived as small text files, enable Git's symlink support (`core.symlinks`) and clone again.
