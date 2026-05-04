## Pattern 02 — Hybrid: Operator Connect + Direct Routing

### Context

A single organization uses Microsoft Teams Phone across several numbering domains or countries.

Some users can be served through Operator Connect. Others require Direct Routing because of local numbering constraints, operator availability, regulatory expectations, legacy dependencies or regional PSTN models.

This pattern applies when one tenant must support both models at the same time.

### Problem

Hybrid Teams Phone models are powerful, but they can become difficult to operate when routing intent is not explicit.

Typical risks include:

- users receiving the wrong voice routing policy;
- normalization rules becoming inconsistent between populations;
- Auto Attendants or Call Queues being attached to the wrong numbering domain;
- support teams not knowing whether an issue belongs to Operator Connect, Direct Routing, SBCaaS or the tenant;
- migration waves mixing countries or numbering domains without clear rollback boundaries.

### Decision

Adopt a hybrid tenant model with explicit domain separation:

- Operator Connect where the operator model is available and sufficient;
- Direct Routing where local constraints or operator posture require it;
- separate routing policies per population or numbering domain;
- documented dial plan and normalization intent;
- call flows mapped to their PSTN path.

The goal is not to hide complexity. The goal is to make the complexity readable and supportable.

### Trade-offs

**Benefits**

- fits real-world country and operator constraints;
- avoids forcing one PSTN model everywhere;
- allows simpler Operator Connect operation where possible;
- preserves Direct Routing flexibility where required.

**Costs / constraints**

- more policies and validation paths;
- stronger naming discipline required;
- support must understand two operating models;
- evidence must distinguish Operator Connect and Direct Routing flows.

### Operating notes

The tenant should be readable by population:

- which users are on Operator Connect;
- which users are on Direct Routing;
- which policies apply to each group;
- which Auto Attendants and Call Queues belong to each numbering domain;
- which escalation path applies to each PSTN model.

For incidents, support should first identify the affected population and PSTN path before troubleshooting deeply.

### Evidence expectations

A clean delivery should include:

- population-to-PSTN-model mapping;
- voice routing policy summary;
- dial plan and normalization overview;
- Auto Attendant / Call Queue inventory with associated numbering domain;
- operator boundary statement for each model;
- migration wave mapping;
- test evidence per country or numbering domain;
- rollback assumptions per wave.

### Anti-patterns

Avoid:

- using one generic routing policy for all populations when routing intent differs;
- mixing Operator Connect and Direct Routing numbers without documenting ownership;
- assuming that a successful test in one country validates the other;
- leaving AA/CQ service numbers outside the numbering domain inventory;
- creating migration waves that mix incompatible rollback boundaries.

### Acceptance criteria

- Each user population has a documented PSTN model.
- Each numbering domain has a documented routing intent.
- Test evidence exists for Operator Connect and Direct Routing flows separately.
- AA/CQ numbers are mapped to the correct PSTN model.
- Support can identify the escalation boundary from the affected number or population.
