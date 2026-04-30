# Pattern 02 — Hybrid: Operator Connect (France) + Direct Routing (Monaco)

## Context

A single organization operates across:
- France (standard numbering and PSTN via Operator Connect)
- Monaco (+377 numbering requiring Direct Routing via operator model)

## Decision

Adopt a hybrid tenant model:
- Operator Connect for the France numbering domain
- Direct Routing (via SBCaaS) for Monaco numbering

## Trade-offs

- clearer domain separation and routing intent
- more policies and dial plan normalization work

## Operating notes

- keep routing boundaries explicit
- document dialing normalization rules

## Evidence expectations

- dial plan / normalization overview
- routing policies per population
- call flow inventory (AA/CQ)
