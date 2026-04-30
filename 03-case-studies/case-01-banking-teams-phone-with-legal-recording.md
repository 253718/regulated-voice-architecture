# Case 01 — Banking Teams Phone with legal recording (anonymized)

## Context

A Monaco-based banking environment required a Teams Phone migration with:
- PSTN via Direct Routing
- operator-managed SBCaaS
- legal recording for regulated users
- evidence-oriented handover to support

## Constraints

- responsibility split: tenant vs operator SBC layer vs recording vendor
- auditability and long retention expectations
- need for predictable RUN operations

## Architecture decisions

- Direct Routing via Monaco Telecom SBCaaS
- Legal recording implemented as an end-to-end chain (capture → access → export → retention)
- Standard call flows (AA/CQ) designed for operational readability

## Operating model

- formal handover to Support/Operations
- routine checks and incident triage defined
- escalation boundaries explicit (operator vs recording vendor)

## Outcomes (non-sensitive)

- stable post-migration operations due to clear boundaries and runbook coverage
- reduced ambiguity during incidents by correlating Teams-side symptoms with boundary ownership

## Proof links

See `04-proof-links/01-technical-portfolio-entrypoints.md` for:
- evidence pack examples
- DAT snippet examples
- read-only export patterns
