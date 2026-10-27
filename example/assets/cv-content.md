---
last-updated: 2026-05-01
---

# CV Content Library

*(Fictional example — Firstname Lastname.)*

Curated, reusable CV blocks, selected during a build by tag-match. `build-cv`
reads this file but never writes it; the only writer is `promote-content` (the
post-build promotion audit). A block earns its place only when the user deliberately
promotes it — there is no automatic or reuse-count rule.

Per-block metadata is `tags` (the selection key) + `ws-refs` (backing win
stories; `[]` if none — and flag the gap).

---

## Professional Summary

#### Variant: growth
```yaml
tags: [data, ux, commercial]
ws-refs: [WS-001, WS-002]
```
Product manager focused on activation, engagement, and monetisation. Instruments funnels, redesigns the path to first value, and connects engagement work to revenue.

---

## Example Learning — Senior Product Manager

```yaml
company: Example Learning
role: Senior Product Manager
dates: March 2021 – Present
```

### Paragraph variants

#### Variant: growth-and-monetisation
```yaml
tags: [strategy, commercial, data]
ws-refs: [WS-001, WS-002]
```
Owned the learner onboarding, engagement, and self-serve monetisation surface across two squads. Rebuilt activation around the first completed lesson and opened a bottom-up expansion path with a new self-serve team tier.

### Bullet pool
*Optional — selectable achievement bullets; build picks the subset that matches the job.*

- ```yaml
  tags: [ux, data]
  ws-refs: [WS-001]
  ```
  Cut week-one new-learner activation drop-off by 22 points (41% → 63% first-lesson completion) by rebuilding onboarding around the first completed lesson, validated in a controlled A/B test.

- ```yaml
  tags: [commercial, strategy]
  ws-refs: [WS-002]
  ```
  Grew expansion revenue 31% in two quarters by designing and shipping a self-serve team tier, opening a bottom-up expansion path without cannibalising individual subscriptions.

- ```yaml
  tags: [stakeholders, commercial]
  ws-refs: [WS-002]
  ```
  Turned sales channel conflict into a qualified-lead source by sizing the self-serve team tier to hand off accounts above 10 seats to the sales team.

---

## Example Software — Product Manager

```yaml
company: Example Software
role: Product Manager
dates: June 2018 – February 2021
```

### Paragraph variants

#### Variant: core
```yaml
tags: [commercial]
ws-refs: []
```
Owned billing and pricing for a B2B SaaS product.
