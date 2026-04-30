# How I think about regulated enterprise voice projects

Enterprise voice projects in regulated environments tend to be misunderstood.

They are often approached either as:

- a purely technical exercise (“configure Teams Phone, it rings, done”), or
- a compliance-heavy narrative focused on certifications, labels, and marketing claims.

My experience is that neither view reflects reality.

## Voice is a service, not a feature

In banking and institutional environments, voice is not a feature sitting inside a collaboration tool.
It is a **service** with:

- explicit accountability boundaries,
- operational expectations,
- auditability requirements,
- and long-term consequences once decisions are made.

Most failures I have seen were not caused by incorrect configuration.
They were caused by **unclear ownership** and **unspoken assumptions**.

## Design starts with boundaries

Before choosing any connectivity model, SBC topology, or recording solution, I focus on one question:

> Where does responsibility start and where does it stop?

In practice, this means making boundaries explicit between:

- the Microsoft Teams tenant,
- the operator (Operator Connect or Direct Routing),
- the SBC layer (self-managed or operator-managed),
- the recording and archiving chain,
- and the customer’s own operational teams.

Architectures that look simple on diagrams often become fragile in production
when these boundaries are left implicit.

## Proportionality over ideology

Not all sites, users, or countries deserve the same level of complexity.

A recurring pitfall is to design for a *theoretical worst case*, rather than for **actual business criticality**.
This usually results in:

- unnecessary infrastructure,
- brittle failover logic,
- and operational debt that support teams inherit.

I favor **proportional architectures**:

- strong local termination where it is justified,
- centralization where risk is acceptable,
- and, most importantly, risks that are **explicitly documented and accepted**.

Saying “no” to certain forms of redundancy is sometimes the most responsible design choice.

## BUILD → RUN is not a phase transition

In regulated voice projects, delivery does not end at go-live.

If a service cannot be:

- monitored,
- explained,
- escalated,
- and restored by teams other than the architect,

then it is not finished.

This is why I treat BUILD → RUN continuity as a **design input**, not a downstream concern.
Runbooks, escalation paths, evidence packs, and handover material are not documentation overhead;
they are part of the architecture itself.

## Evidence is not compliance

Another common confusion is between **evidence** and **compliance**.

Producing clean, read-only, reviewable evidence is essential.
Claiming compliance because evidence exists is a different matter.

My role is to design services that:

- generate the right evidence,
- in a predictable and reviewable way,
- without pretending to replace governance, legal review, or regulatory sign-off.

Clear separation here matters, especially in financial environments.

## Why this repository is structured the way it is

This repository deliberately prioritizes:

- decisions over implementation steps,
- principles over procedures,
- and operating reality over storytelling.

The work documented here is derived from real delivery projects.
What may evolve over time is **not the experience**, but the depth of narrative context
as projects settle and hindsight becomes clearer.

This is a living body of thinking, not a marketing narrative.

Its purpose is simple:
to make voice architecture in regulated environments **understandable, operable, and honest**.
