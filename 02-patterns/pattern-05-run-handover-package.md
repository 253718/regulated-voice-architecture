## Pattern 05 — RUN handover package

### Context

Teams Phone services are inherited by support teams after go-live.

In regulated or service-oriented environments, a voice service is not complete when calls work during acceptance testing. It is complete when support can understand, monitor, change and restore it.

### Problem

Many voice deliveries create operational ambiguity after go-live:

- support does not know which objects exist;
- escalation paths are unclear;
- routine changes are not repeatable;
- incident triage depends on the original build engineer;
- evidence exists informally but is not packaged;
- AA/CQ, recording, operator and endpoint boundaries are mixed together.

This creates fragile operations even when the technical build was correct.

### Decision

Standardize a RUN handover package for voice projects.

The package should describe:

- service scope;
- responsibility boundaries;
- monitoring perimeter;
- routine checks;
- standard changes;
- incident triage paths;
- evidence baseline;
- known limitations;
- escalation triggers.

The handover package is part of the architecture, not an administrative afterthought.

### Package contents

A minimum package should include:

- service overview;
- number and call-flow inventory;
- Auto Attendant / Call Queue inventory;
- routing policy and dial plan overview;
- operator / SBC responsibility split;
- recording responsibility split where applicable;
- monitoring perimeter;
- routine check list;
- standard change templates;
- incident triage runbooks;
- escalation map;
- acceptance test evidence;
- known limitations and accepted risks;
- handover sign-off checklist.

### Trade-offs

**Benefits**

- reduces post-go-live dependency on the build team;
- improves incident localization;
- makes routine changes safer;
- supports audits and service reviews;
- creates a repeatable delivery standard.

**Costs / constraints**

- requires time before go-live;
- requires disciplined evidence capture;
- can feel heavy for small scopes unless proportionality is applied;
- must be maintained when the service changes.

### Operating notes

The handover package should answer practical support questions:

- what service is this?;
- which numbers and flows are in scope?;
- who owns the tenant layer?;
- who owns the operator / SBC layer?;
- what can support change safely?;
- what must be escalated?;
- what evidence exists from go-live?;
- what is known to be out of scope?

A good package prevents support from having to reverse-engineer the service during an incident.

### Evidence expectations

A clean handover should include:

- signed or acknowledged handover checklist;
- archived configuration snapshot;
- test evidence;
- runbook catalog;
- support owner mapping;
- operator escalation information;
- known limitations;
- change process notes.

### Anti-patterns

Avoid:

- considering handover complete with only a verbal explanation;
- delivering configuration without operational ownership;
- hiding accepted risks from support;
- omitting AA/CQ operational changes from standard procedures;
- creating runbooks that only the build engineer understands;
- publishing tenant-changing procedures in public artefacts.

### Acceptance criteria

- Support can identify service objects and ownership boundaries.
- Routine changes are documented.
- Incident triage paths exist for common symptoms.
- Evidence from delivery is packaged and accessible.
- Accepted risks and known limitations are documented.
- The build team can disengage without leaving hidden knowledge behind.
