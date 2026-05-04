## Pattern 03 — Multi-site hub-and-spokes with proportionality

### Context

A multi-site organization needs Teams Phone across locations with different sizes, call volumes, business criticality and local PSTN constraints.

A single uniform architecture may look attractive, but it often ignores operational reality.

Some sites justify local termination or stronger resilience. Others can reasonably accept centralized behavior.

### Problem

Multi-site voice projects often fail in one of two ways:

- over-standardization: every site receives the same model even when constraints differ;
- over-engineering: every site receives complex resilience even when the business value does not justify it.

Both approaches create operational debt.

The real issue is not whether a site is centralized or local. The real issue is whether the risk is explicit, accepted and supportable.

### Decision

Use a proportional hub-and-spokes model:

- stronger local termination where business criticality or local constraints justify it;
- centralized hub behavior where risk is acceptable;
- explicit documentation of accepted SPOFs;
- site classification before design finalization;
- cutover and rollback planning adapted to site criticality.

Do not design all sites identically unless their requirements are actually identical.

### Trade-offs

**Benefits**

- avoids unnecessary complexity on low-criticality sites;
- concentrates stronger design effort where it matters;
- makes accepted risk visible;
- improves migration planning and stakeholder alignment.

**Costs / constraints**

- requires honest classification of site criticality;
- requires stakeholder sign-off on accepted risks;
- may produce several operating patterns rather than one universal model;
- support documentation must clearly identify site category and escalation path.

### Operating notes

Each site should have an operating profile:

- site category;
- PSTN model;
- dependency on hub services;
- local constraints;
- expected fallback behavior;
- support owner;
- rollback approach.

Support should not need to infer whether a site is critical after an incident has started.

### Evidence expectations

A clean delivery should include:

- site classification matrix;
- PSTN model per site;
- accepted SPOF register;
- local termination decision log;
- call-flow inventory for high-value sites;
- cutover and rollback templates;
- stakeholder sign-off on proportionality decisions;
- support handover notes per site category.

### Anti-patterns

Avoid:

- designing every site as if it had the same business impact;
- hiding centralization risk behind generic diagrams;
- promising failover that has not been tested;
- omitting local PSTN constraints from early qualification;
- treating rollback as identical for all sites.

### Acceptance criteria

- Sites are classified by criticality and constraints.
- Local termination decisions are documented.
- Accepted SPOFs are visible and owned.
- Cutover and rollback plans reflect site category.
- Support can identify the expected behavior for each site during an incident.
