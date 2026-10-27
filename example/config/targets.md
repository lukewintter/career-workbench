# Current targets

*(Fictional example — Firstname Lastname.)*

## Search snapshot
- Updated: 2026-05-01
- Priority order: Growth PM > Core Product PM

## Role tracks

### Track 1: Growth / engagement product

- **Typical titles:** Lead Product Manager (Growth), Principal PM, Senior PM (Growth/Activation)
- **Level and scope target:** own a full funnel or engagement area; 1–2 squads
- **Company types and stage:** Series B–D B2C or B2B2C with a large user base
- **Primary mission:** raise activation, retention, and expansion with measured iteration
- **Strategic rationale (why this track fits my broader career direction right now):** it compounds my activation + monetisation track record into a bigger surface and a lead seat.
- **Personal motivation (why this work genuinely energizes me now):** I like the tight loop between a user problem and a number that moves.
- **Relative priority:** high

### Track 2: Core product (learning / consumer software)

- **Typical titles:** Senior Product Manager, Lead Product Manager
- **Level and scope target:** own a core product area end to end
- **Company types and stage:** mission-driven consumer or edtech, Series A–C
- **Primary mission:** ship a coherent product experience users return to
- **Strategic rationale (why this track fits my broader career direction right now):** keeps me close to end-user craft while I grow scope.
- **Personal motivation (why this work genuinely energizes me now):** I care about products people use to get better at something.
- **Relative priority:** medium

## Cross-track decision filters

Canonical source for agents and humans (one YAML block per filter):

#### Remote / location

```yaml
id: remote-hybrid
dimension: work location
rule: fully remote, or hybrid within commuting distance of Manchester
stance: must-have
flex: negotiable
exception_trigger: exceptional role with relocation support
notes:
  - based in Manchester, UK
```

#### Product surface

```yaml
id: growth-surface
dimension: product area
rule: role owns activation, engagement, retention, or monetisation
stance: nice-to-have
flex: negotiable
exception_trigger: strong core-product role with a clear growth lever
notes:
  - platform/infra-only roles are a poor fit
```

#### Team stage

```yaml
id: stage
dimension: company stage
rule: post product-market fit; Series A through D
stance: nice-to-have
flex: negotiable
exception_trigger: none
notes:
  - avoids very early 0→1 with no user base to iterate on
```
