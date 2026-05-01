# Regulated Voice Architecture

Architecture and design notes for **regulated enterprise voice services** (banking, private banking, institutional environments).

This repository is the **public narrative layer** of my work:

- it explains *why* certain architecture choices are made,
- it captures delivery trade-offs and operating assumptions,
- it remains **anonymized** (no client identifiers, no numbers, no tenant data).

It is **not** a tooling repo and intentionally contains:

- no scripts,
- no runbooks that perform tenant changes,
- no customer-specific configuration.

If you are looking for **technical proof** (artefacts, evidence packs, read-only pipelines), see `04-proof-links/01-technical-portfolio-entrypoints.md`.

## Start here

Suggested reading path:

- **Positioning** → `00-start-here/01-positioning.md`
- **Scope / Non-scope** → `00-start-here/02-scope-nonscope.md`
- **Reader map (5 min / 30 min paths)** → `00-start-here/03-reader-map.md`
- **How to use this repo with proof links** → `00-start-here/04-how-to-use-with-proof-links.md`

## Scope and intent

All content in this repository is derived from real delivery work.

The focus is on architectural decisions, operating boundaries, and design principles.  
This repository prioritizes structure and clarity over exhaustive storytelling.

For a more explicit statement of intent and approach, see:

- **How I think about regulated enterprise voice projects**  
  → 01-principles/how-i-think-about-regulated-voice.md

## Operator naming

This repository may reference Monaco Telecom where the **operator-managed SBCaaS model** is the architectural decision driver.  
For France, Operator Connect is discussed generically ("a major Operator Connect provider"). A Direct Routing provider name (e.g. Hexanet) may appear **only** in a case study where it materially changes the design.

## License

Text content is licensed under **CC BY-NC-ND 4.0** (see `LICENSE`).
