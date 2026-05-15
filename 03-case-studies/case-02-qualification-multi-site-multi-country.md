# Case 02 — Qualification of a multi-site, multi-country migration (anonymized)

## Context

A multi-site organization planned a Cisco-to-Teams Phone migration.
Key characteristics:

- multiple data centers
- many remote sites
- countries with local PSTN constraints (not all regions support centralization)

## What made qualification non-trivial

- not all sites could share the same PSTN model
- some regions required local gateways or non-SIP connectivity
- the largest sites needed receptionist-style call handling and schedule-based logic

## Architecture stance

Instead of forcing uniformity, qualification focused on:

- separating "core" sites from "satellite" sites
- defining where local termination was mandatory
- using proportionality to reduce operational burden

## Delivery stance

Qualification included early planning for:

- training (admins, local support, local site referents)
- operating procedures for gateways and routing diagnostics

## Outcomes (non-sensitive)

- clearer scope and boundaries before implementation
- reduced risk of over-designed solutions

## Proof links

See `04-proof-links/01-technical-portfolio-entrypoints.md` for:

- templates (migration plan, cutover/rollback, handover)
- evidence pack patterns
