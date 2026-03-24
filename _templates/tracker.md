---
last-updated: yyyy-mm-dd
---

# Application Tracker

HQ view of all active and closed applications. Answers the question:
what's happening right now, and what do I need to do next?

Update whenever something changes — a reply received, a round scheduled,
a decision made. Keep `last-updated` current so awaiting-reply status
is meaningful.

---

## Controlled vocabulary

**Stage** — furthest point reached in the process. Only moves forward.
- `applied` — application submitted, nothing more yet
- `screening` — initial talent or recruiter conversation
- `interviewing` — past screening, in active interview rounds
- `offer` — offer received

**Status** — current operational state.
- `awaiting-reply` — ball is in their court, you are waiting
- `action-needed` — something is on you right now
- `scheduled` — next round or meeting is confirmed
- `closed` — process is over, outcome recorded

**Outcome** — set once when the process ends.
- `accepted` — offer accepted
- `rejected` — rejected by them
- `withdrawn` — withdrawn by you
- `ghosted` — no response after reasonable follow-up attempts

---

## Tracker

| Folder | Company | Role | Salary | Posted | Applied | Last updated | Stage | Status | Next action | Outcome |
|--------|---------|------|--------|--------|---------|--------------|-------|--------|-------------|---------|
|        |         |      |        |        |         |              |       |        |             |         |

