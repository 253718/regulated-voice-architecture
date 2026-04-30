# Pattern 03 — Multi-site hub-and-spokes with proportionality

## Context

Multi-site organizations often attempt to standardize everything.
In practice, sites differ:
- call volumes
- local PSTN constraints
- operational criticality

## Decision

Use a **proportional** model:
- stronger local termination where needed
- centralized hub behavior where acceptable
- accepted SPOFs are documented, not hidden

## Trade-offs

- reduced operational complexity vs perfect resilience
- requires explicit stakeholder sign-off on accepted risks

## Operating notes

- define which sites must never depend on the hub
- define validation and rollback triggers

## Evidence expectations

- architecture boundary statement
- risk register excerpt (accepted SPOFs)
- cutover and rollback templates
