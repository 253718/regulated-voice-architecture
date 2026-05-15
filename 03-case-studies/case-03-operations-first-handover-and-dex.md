# Case 03 — Operations-first: handover and DEX (anonymized)

## Context

In regulated environments, operations teams inherit voice services.
A recurrent issue is the absence of operational reference material.

A Teams Phone service can pass acceptance tests and still remain fragile if support cannot understand which objects exist, which boundary owns the symptom, and which changes are safe to perform after go-live.

## Approach

- deliver a RUN guide and handover package as first-class deliverables
- separate the as-built architecture document from the operations document
- define routine checks and triage paths
- document how to localize incidents across boundaries (Teams / SBC / operator / endpoint)
- keep customer-specific procedures private while publishing reusable, anonymized templates

## What "good" looks like

- support can identify the relevant service objects without reverse-engineering the tenant
- support can produce a concise diagnosis: where it breaks and the next action
- changes to AA/CQ messages, schedules, agents and overflow targets are repeatable and validated
- recording issues have a clear first-line checklist before escalation
- delivery evidence and RUN guidance are connected rather than stored as unrelated documents

## Architecture / operations split

The as-built DAT should answer:

- what was delivered
- which numbers, Auto Attendants, Call Queues and Resource Accounts are in scope
- which PSTN model and operator boundary applies
- how inbound, outbound, schedule and holiday behavior is expected to work

The DEX should answer:

- how support checks the service
- how routine changes are handled
- what must be validated after change
- how incidents are localized
- how rollback is approached
- what periodic maintenance is required

## Outcomes (non-sensitive)

- reduced dependency on the original build engineer
- clearer BUILD → RUN transition
- safer routine changes after go-live
- better incident localization across tenant, operator, SBC and endpoint boundaries
- stronger evidence posture without publishing tenant-changing procedures

## Proof links

See 04-proof-links/01-technical-portfolio-entrypoints.md for:

- Teams Phone as-built DAT template
- Teams Phone RUN / DEX operations template
- handover run template
- runbook catalog
- generated DAT snippets and evidence pack examples
