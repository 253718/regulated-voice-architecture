# Case 04 — France Direct Routing via an independent provider (anonymized)

## Context

In France, Operator Connect is often the default path for standard PSTN integration.
However, some situations still require **Direct Routing** (constraints, legacy, specific routing control, or provider posture).

This case study is based on qualification work where Direct Routing was considered via an independent Direct Routing provider (e.g., **Hexanet**).

## What changes compared to Operator Connect

- The SBC boundary becomes explicit (even when hosted):
  - certificate lifecycle
  - SIP/TLS reachability assumptions
  - media and firewall constraints
- Support and escalation patterns differ:
  - incident triage often needs correlation across Teams and SBC/provider logs

## Qualification stance

- Start from call flows and numbering intent (what must route where)
- Validate network flows and assumptions early (what is required vs what is "assumed")
- Define responsibilities explicitly (who owns SBC platform, upgrades, monitoring)

## Outcomes (non-sensitive)

- The decision to use Direct Routing should be driven by **constraints**, not by habit.
- When OC is available and sufficient, it reduces operational surface.
- When DR is necessary, the project must include stronger boundary documentation and run readiness.

## Proof links

- Technical routing and boundary artefacts: see `04-proof-links/01-technical-portfolio-entrypoints.md`
