---
last-updated: yyyy-mm-dd
---

# CV Content Library

Curated, reusable CV blocks, selected during a build by tag-match. `build-cv`
reads this file but never writes it; the only writer is `promote-content` (the
post-build promotion audit). A block earns its place only when the user deliberately
promotes it — there is no automatic or reuse-count rule.

Per-block metadata is `tags` (the selection key) + `ws-refs` (backing win
stories; `[]` if none — and flag the gap). Nothing else is stored: origin,
recency, and usage are derivable from git + live-search over `applications/`.

Structure per role: one or more `#### Variant:` paragraph blocks (one → used
as-is; several → build selects by tag-match) plus an optional `### Bullet pool`.

---

## Professional Summary

#### Variant: <name>
```yaml
tags: [ux, strategy]
ws-refs: [WS-###]
```
Summary variant angled toward a theme. Claims must be backed by the referenced win stories.

---

## Company — Role

```yaml
company:
role:
dates:
```

### Paragraph variants

#### Variant: <name>
```yaml
tags: [strategy, platform]
ws-refs: [WS-###]
```
Prose paragraph for this role.

### Bullet pool
*Optional — selectable achievement bullets; build picks the subset that matches the job.*

- ```yaml
  tags: [commercial, data]
  ws-refs: [WS-###]
  ```
  Verb-led achievement with quantified impact.
