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
- [ ] Step 3: Paste the raw job ad into `job-ad.md` exactly as received — do not edit or summarize.
- [ ] Step 4: Add initial notes in `application-notes.md` (private — never referenced in outputs).
- [ ] Step 5: Identify relevant win stories and assets using `config/tags.md` — match job ad themes to tags and list the top candidates.

## Gotchas

- Application folder naming: `company-role-yyyy-mm` — all lowercase, hyphenated.
- `application-notes.md` is private — never quote, paraphrase, or reference it in generated outputs.
- Keep content flow one-way: source files are read-only during generation. Generated content goes in the application folder.
