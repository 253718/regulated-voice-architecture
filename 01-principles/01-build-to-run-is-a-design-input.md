# BUILD → RUN is a design input

In regulated voice work, the primary failure mode is not "configuration".
It is **operational ambiguity** after go-live:

- unclear escalation boundaries
- missing monitoring scopes
- missing runbooks and validation steps

## Principle

Design must include the operating model:

- who owns what (tenant, operator, customer network, recording vendor)
- what is monitored and by whom
- which runbooks exist and what evidence is captured

## Minimal RUN package (what should exist)

- Responsibility matrix (RACI-style)
- Escalation flow (who to call, when, for which symptoms)
- Monitoring perimeter list
- Runbook catalog:
  - routine checks
  - standard changes (AA/CQ schedules, messages)
  - incident triage (Teams ↔ SBC ↔ operator ↔ endpoint)
- Handover checklist

## Why this matters

The service is not "delivered" when calls work once.
It is delivered when a support team can:

- detect a problem
- localize the boundary
- execute the next action without guesswork
