# Pattern 04 — Legal recording as a chain

## Context

Regulated users require call recording for governance, legal, regulatory or business-control reasons.

In Teams Phone environments, recording is not a single switch. It is an end-to-end chain involving policy targeting, capture, access, export, retention and operational monitoring.

## Problem

Recording projects often focus too narrowly on whether a call is captured once during testing.

That is not enough for a regulated environment.

The real risks are chain risks:

- the right users may not be targeted;
- calls may be captured but not searchable;
- exports may fail silently;
- retention may be misunderstood;
- support may not know whether an incident belongs to Teams, the recording vendor, storage or policy assignment.

## Decision

Treat legal recording as an end-to-end service chain.

Design and validate:

- policy assignment;
- capture behavior;
- access and search layer;
- export path;
- long-term retention target;
- incident triage and ownership boundaries.

Do not claim compliance from technical evidence alone. Evidence supports review, but compliance remains a governance outcome.

## Trade-offs

### Benefits

- fewer ambiguous recording incidents;
- clearer audit support;
- better support readiness;
- stronger separation between technical evidence and compliance claims.

### Costs / constraints

- more validation effort before go-live;
- more stakeholders involved;
- requires coordination with recording vendor and storage owners;
- support must understand several systems rather than only Teams.

## Operating notes

Support needs a first-line recording triage path:

1. Confirm the user and call time.
2. Validate whether the user should be recorded.
3. Check policy assignment summary.
4. Validate whether the call should have matched the recording scope.
5. Check recording vendor portal / search layer.
6. Check export or retention path if capture exists but archive is missing.
7. Escalate to the correct boundary: tenant, recording vendor or storage owner.

The chain must be tested as a chain, not as isolated components.

## Evidence expectations

A clean delivery should include:

- recording policy assignment summary;
- recorded-user population overview;
- capture validation checklist;
- access/search validation evidence;
- export validation evidence;
- retention target description;
- responsibility boundary statement;
- incident triage runbook;
- handover notes for support.

## Anti-patterns

Avoid:

- claiming compliance because calls were recorded during a test;
- validating capture without validating access or export;
- leaving recording policy assignments undocumented;
- treating vendor portal visibility as a complete retention proof;
- omitting the recording chain from RUN handover;
- mixing technical evidence with legal sign-off language.

## Acceptance criteria

- Recorded populations are documented.
- Policy assignment evidence exists.
- Capture, access, export and retention assumptions are validated.
- Support has a recording incident triage path.
- Responsibility boundaries are documented across tenant, vendor and storage layers.
- Compliance claims are avoided unless provided by the appropriate governance process.
