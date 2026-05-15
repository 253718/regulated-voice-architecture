# Pattern 01 — Operator-managed SBCaaS

## Context

A regulated or service-oriented organization needs Microsoft Teams Phone with Direct Routing in a geography where the PSTN operator provides the SBC layer as a managed service.

This pattern is common when local numbering, carrier constraints or regional operating models make pure Operator Connect insufficient or unavailable.

The key point is that the SBC exists, but it is not owned or operated by the customer or integrator.

## Problem

Operator-managed SBCaaS can look deceptively simple from the Teams tenant side.

The main risk is not the routing configuration itself. The main risk is unclear responsibility boundaries:

- Teams policies and routes are owned on the tenant side;
- SBC hardening, lifecycle and availability are owned by the operator;
- PSTN reachability is owned by the operator;
- endpoint and network symptoms may still appear first to customer support;
- incident triage can become slow if the boundary is not documented.

## Decision

Use operator-managed SBCaaS for Direct Routing when the operator model is the best fit for the numbering domain and operational context.

Keep the customer / integrator scope focused on:

- tenant-side SBC declaration;
- voice routes and routing policies;
- dial plans and normalization;
- user voice enablement;
- Auto Attendants and Call Queues;
- handover and operational evidence.

Do not present the solution as if the customer owns the SBC platform.

## Trade-offs

## Benefits

- reduced infrastructure ownership;
- no customer-run SBC platform to patch, harden or monitor;
- operator ownership of SBC availability and PSTN integration;
- simpler platform lifecycle for the customer.

## Costs / constraints

- incidents often require coordination with the operator;
- tenant-side visibility into SBC internals may be limited;
- monitoring boundaries must be explicit;
- design documentation must clearly separate tenant, SBC and PSTN ownership.

## Operating notes

Support teams need a clear diagnostic split:

1. Validate Teams user / service configuration.
2. Validate routing policy and dial plan assignment.
3. Validate Auto Attendant / Call Queue behavior when relevant.
4. Test Teams-to-Teams behavior to separate endpoint/client issues from PSTN issues.
5. Test outbound and inbound PSTN flows.
6. If signaling, PSTN reachability, media path or trunk behavior is suspected, escalate to the operator with a precise symptom package.

The support model should document what can be checked internally and what requires operator intervention.

## Evidence expectations

A clean delivery should include:

- tenant-side routing snapshot;
- SBC FQDN / trusted SBC declaration summary;
- voice routing policy overview;
- dial plan and normalization overview;
- call flow inventory for AA/CQ services;
- operator responsibility boundary statement;
- support escalation path;
- test evidence for inbound and outbound PSTN flows;
- handover checklist.

## Anti-patterns

Avoid:

- describing the SBC as customer-managed when it is not;
- accepting vague operator / customer boundaries;
- delivering Direct Routing without an escalation package;
- troubleshooting every PSTN symptom as a Teams tenant issue;
- omitting AA/CQ flows from the routing evidence;
- promising resilience that belongs to the operator contract but is not documented.

## Acceptance criteria

- The operator boundary is documented.
- Tenant-side routing objects are captured in evidence.
- Inbound and outbound PSTN calls are tested.
- AA/CQ flows using the SBCaaS path are tested where applicable.
- Support knows when to investigate internally and when to escalate to the operator.
- The handover package identifies owner, scope and escalation trigger for each layer.
