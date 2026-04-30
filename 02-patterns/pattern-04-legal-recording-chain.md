# Pattern 04 — Legal recording as a chain (ASC Recording Insights)

## Context

Regulated users require **legal recording**.
The real system is a chain:
- capture
- access/search
- export
- long-term retention

## Decision

Design and validate the chain end-to-end.
Treat recording as a service with boundaries (tenant, recording vendor, storage).

## Trade-offs

- higher upfront validation effort
- lower audit risk and fewer "it records sometimes" incidents

## Operating notes

- policy targeting checks
- missing recording triage path
- export pipeline monitoring

## Evidence expectations

- policy assignment summary (aggregated)
- end-to-end validation checklist
- handover notes for support teams


## Diagram (recording chain)

```mermaid
flowchart LR
  Calls[Teams Phone calls] --> ASC[Recording vendor
(ASC Recording Insights)]
  ASC --> Access[Search / access layer
(Neo Core / portal)]
  ASC --> Export[Automated export] --> Archive[(Long-term retention
Object storage)]

  note["Design goal: validate capture + access + export + retention as one chain"]
  Calls --- note
```
