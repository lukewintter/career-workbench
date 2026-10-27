# example/ — a filled workbench to browse

This folder is a **synthetic, self-contained example** of a filled career-workbench. Everything here belongs to a **fictional person — Firstname Lastname, a product manager** — invented purely to show the *shape* of the system: how config, roles, win stories, assets, and an application fit together and reference each other.

**Browse it, then delete it.** Nothing here is yours, and nothing here is operated on by the workflows. Once you've seen how the pieces connect, `rm -rf example/` and build your own via `setup-workbench`.

## What's inside

```
example/
├── config/          # who the persona is, what they target, the tag taxonomy, the research prompt
├── roles/           # one role file (context and framing only)
├── wins/            # two STAR win stories — the evidence behind every claim
├── assets/          # a slice of promoted, reusable CV language + boilerplate
├── applications/
│   └── example-health-senior-pm-2026-05/   # one opportunity, end to end
│       ├── job-ad.md, application-notes.md, cv.md, cover-letter.md
│       └── R1-recruiter-screen/            # one interview round: prep, debrief, feedback
└── tracker.md       # the cross-application status view
```

## What to notice

- **Claims trace to evidence.** Every quantified line in `cv.md` and `cover-letter.md` comes from a win story in `wins/` (see the `ws-refs` in `assets/cv-content.md`). Nothing is invented.
- **Facts vs. framing.** `roles/` holds context; `wins/` hold achievements; `config/` holds positioning. The same win is framed differently for different targets.
- **Private stays private.** `application-notes.md`, and the `## Reflection` / `## Timeline` / `## Growth edges` sections, are never reused in outward-facing outputs.

> All names, companies, metrics, and events below are fictional.
