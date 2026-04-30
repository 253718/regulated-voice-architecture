# Operator boundaries and responsibility splits

Operator models shape voice architecture more than many Teams settings do.

## Two common models

### Operator Connect (France patterns)

- PSTN integration is abstracted behind the Operator Connect program.
- Operational ownership is mostly about tenant configuration + service readiness.

### Direct Routing via operator-managed SBCaaS (Monaco patterns)

- The SBC is provided and operated by the operator.
- The customer (or integrator) primarily owns tenant-side configuration:
  - SBC declaration, routing, dial plans, AA/CQ, policies
- The operator owns:
  - SBC hardening, firmware, HA/SLA of SBCaaS
  - PSTN side and trunk availability

## Why responsibility splits matter

Most incidents are "boundary incidents":
- symptom appears in Teams
- cause sits on SBC, operator PSTN, customer network, or endpoint

A robust design makes boundaries explicit:
- which flows exist (and which do not)
- what monitoring is expected
- escalation triggers

## Practical design stance

A good architecture is not only *how it routes*.
It is also *how it can be supported*.
