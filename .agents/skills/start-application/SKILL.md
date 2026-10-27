---
name: start-application
description: >
  Start a new job application from templates. Use this skill when the user
  has a job they want to apply for, wants to set up a new application folder,
  or has a job ad to process. Also use when they mention applying, starting
  an application, or setting up an opportunity.
---

# Start Application

Start the response with "Using `start-application` workflow"

## When to use

The user has a job opportunity and wants to set up the application folder, capture the job ad, and identify relevant evidence from their base.

## Required context

Read before starting:
- `config/me.md`
- `config/targets.md`
- `config/tags.md`
- The job ad (provided by the user)

## Steps

- [ ] Step 1: Copy `_templates/application/` into `applications/`.
- [ ] Step 2: Rename the folder to `company-role-yyyy-mm` (lowercase, hyphenated, no spaces).
- [ ] Step 3: Paste the raw job ad into `job-ad.md` exactly as received — do not edit, normalize, or summarize. This is the primary input for all generated outputs in this application folder.
  - If the user provides a URL instead of pasted text, fetch the job ad from the URL and preserve the fetched text in `job-ad.md`.
  - Record the source URL in frontmatter. If there are multiple job-ad URLs, keep the canonical/source URL in `url` and add additional explicit metadata fields such as `linkedin_url`.
- [ ] Step 4: Add initial notes in `application-notes.md` (private — never referenced in outputs), including a dated timeline using `date — milestone — status/source` form.
  - Populate `## People / contacts` with any known recruiter, referrer, hiring manager, or interviewer details.
  - For each person, capture company title, role in process, location, LinkedIn/email when known, source, round relevance, and notes.
- [ ] Step 5: Identify relevant win stories and assets using `config/tags.md` — match job ad themes to tags and list the top candidates.

## application-notes.md sections

`application-notes.md` is private — never referenced in outputs. Its sections:
- `## First impressions` — gut feeling when the ad is found; why it caught attention.
- `## Motivation` — why I want this role, what excites me, what gives pause.
- `## People / contacts` — durable list of people in this process (see Gotchas).
- `## Salary and logistics` — discussed range, my target, location/remote, work mode, notice period, their fill timeline.
- `## Timeline and process` — current stage plus dated `YYYY-MM-DD — milestone — status/source` entries.
- `## Red flags` — anything that felt off, in the ad, conversations, or research.
- `## Questions to ask` — questions that emerge through the process.
- `## Running notes` — ongoing catch-all: things heard, gut checks after conversations, things to remember.

## User-owned notes

Do not fill subjective sections unless the user provides content or explicitly asks for agent interpretation:
- `## First impressions`
- `## Motivation`
- `## Red flags`
- `## Questions to ask`
- `## Running notes`
- `My target` (in `## Salary and logistics`)

Leave these as `tbd` by default.

Agent-generated notes may include only:
- neutral source and timeline facts
- known people/contact details from the user or job source
- job-ad theme mapping
- evidence candidates from tags, win stories, role files, or assets

## Gotchas

- Use `application-notes.md` as the durable application-level people list. Copy relevant people into round prep files when a round is confirmed.
- For people/contact details, preserve uncertainty from the source or user input (for example, `likely hiring manager` or `Stockholm or London; unclear`). Put person-specific source details in `application-notes.md`; put job-ad URLs in `job-ad.md` metadata.
- Keep `application-notes.md` timeline entries parallel: `YYYY-MM-DD — milestone — status/source`. Use `Next — milestone — tbd` when a date is not known.
