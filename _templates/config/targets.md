# Current targets

## Search snapshot
- Updated: yyyy-mm-dd
- Priority order: Track A > Track B > Track C

## Role tracks

### Track 1: [name]
- **Typical titles:**
- **Level and scope target:**
- **Company types and stage:**
- **Primary mission:**
- **Strategic rationale (why this track fits my broader career direction right now):**
- **Personal motivation (why this work genuinely energizes me now):**
- **Relative priority:** high | medium | low

### Track 2: [name]
- **Typical titles:**
- **Level and scope target:**
- **Company types and stage:**
- **Primary mission:**
- **Strategic rationale (why this track fits my broader career direction right now):**
- **Personal motivation (why this work genuinely energizes me now):**
- **Relative priority:** high | medium | low

## Cross-track decision filters

Canonical source for agents and humans (one YAML block per filter):

#### [Dimension 1]

```yaml
id: [kebab-case-id]
dimension: [short human-readable dimension name]
rule: [specific threshold or condition to evaluate]
stance: must-have | nice-to-have | neutral | no-go
flex: hard | negotiable
exception_trigger: [what would justify overriding this; or none]
notes:
  - [optional context line 1]
  - [optional context line 2]
```

#### [Dimension 2]

```yaml
id: [kebab-case-id]
dimension: [short human-readable dimension name]
rule: [specific threshold or condition to evaluate]
stance: must-have | nice-to-have | neutral | no-go
flex: hard | negotiable
exception_trigger: [what would justify overriding this; or none]
notes:
  - [optional context]
```

To add a filter, copy one YAML block and keep keys: `id`, `dimension`, `rule`, `stance`, `flex`, `exception_trigger`, `notes`.
