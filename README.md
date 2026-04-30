# Regulated Voice Architecture

Architecture and design notes for **regulated enterprise voice services** (banking, private banking, institutional environments).

This repository is a **narrative layer**:
- it explains *why* certain architecture choices are made,
- it captures delivery trade‑offs and operating assumptions,
- it remains **anonymized** (no client identifiers, no numbers, no tenant data).

It is **not** a tooling repo and it intentionally contains:
- no scripts,
- no runbooks that perform tenant changes,
- no customer‑specific configuration.

## Start here

- **Positioning** → `00-start-here/01-positioning.md`
- **Scope / Non-scope** → `00-start-here/02-scope-nonscope.md`
- **Reader map (5 min / 30 min paths)** → `00-start-here/03-reader-map.md`
- **How to use this repo with proof links** → `00-start-here/04-how-to-use-with-proof-links.md`

## Why this repo exists

My technical portfolio repo focuses on **proof** (artefacts, evidence packs, read‑only pipelines). This repo focuses on **meaning**: decisions, constraints, and operating realities.

If you want technical proof, see `04-proof-links/01-technical-portfolio-entrypoints.md`.

## Scope and intent

All content in this repository is derived from real delivery work.
The current focus is on architectural decisions and operating principles rather than extended storytelling.

## Operator naming

This repo may reference Monaco Telecom where the **operator-managed SBCaaS model** is the architectural decision driver.
For France, Operator Connect is discussed generically ("a major Operator Connect provider"). A Direct Routing provider name (e.g., Hexanet) may appear **only** in a case study where it materially changes the design.

## License

Text content is licensed under **CC BY-NC-ND 4.0** (see `LICENSE`).
