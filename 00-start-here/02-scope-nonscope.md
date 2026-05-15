# Scope / Non-scope

## In scope

- Regulated enterprise voice architecture and delivery patterns
- Teams Phone connectivity models:
  - Operator Connect (France patterns)
  - Direct Routing via operator-managed SBCaaS (Monaco patterns)
  - Hybrid OC + DR where numbering and operators differ
- Legal/compliance recording as a **chain** (not a toggle)
- BUILD → RUN continuity: handover, support enablement, evidence packaging

## Out of scope (deliberate)

- Emergency / life-safety voice systems ("mission-critical" in the strict sense)
- "5 nines" marketing narratives that do not match real boundaries
- Customer-specific internal escalation paths or credentials
- Tenant-changing scripts and operational automation

## Design stance: proportionality

Not every site, country, or use-case deserves the same complexity.
A consistent pattern in real work is **proportional architecture**:

- high-value sites get stronger local termination and resilience
- low-criticality sites may accept centralization to reduce operational load

The important part is not perfection. It is **explicit risk ownership**.
