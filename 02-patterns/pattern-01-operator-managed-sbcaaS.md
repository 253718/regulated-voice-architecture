# Pattern 01 — Operator-managed SBCaaS (Monaco Telecom)

## Context

You need Direct Routing and PSTN services in a geography where the operator provides **SBC as a Service**.

## Decision

Use operator-managed SBCaaS for Direct Routing.
Keep the integrator/customer scope focused on tenant configuration.

## Trade-offs

**Pros**
- reduced infrastructure ownership (no customer SBC platform to run)
- operator HA/SLA on the SBC layer

**Cons**
- boundary incidents (tenant vs operator) are common
- you must document responsibilities precisely

## Operating notes

- define escalation path to the operator
- keep a minimal set of routine checks (SBC presence, test calls, AA/CQ behavior)

## Evidence expectations

- tenant-side routing snapshot (policies/routes/dial plans)
- responsibility split document
- handover checklist


## Diagram (responsibility boundary)

```mermaid
flowchart LR
  User[Users / Endpoints] -->|Teams client| Teams[Microsoft Teams Cloud]
  Teams -->|SIP/TLS + SRTP| SBCaaS[Operator-managed SBCaaS
(Monaco Telecom)]
  SBCaaS -->|PSTN| PSTN[(PSTN)]

  classDef tenant fill:#e8f0fe,stroke:#3b82f6,color:#111827;
  classDef operator fill:#ecfdf5,stroke:#10b981,color:#111827;

  note1["Tenant scope: routes, policies, dial plans, AA/CQ, user enablement"]:::tenant
  note2["Operator scope: SBC hardening, HA/SLA, trunk, PSTN"]:::operator

  Teams --- note1
  SBCaaS --- note2
```
