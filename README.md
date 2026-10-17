# Capability-as-Infrastructure: Software on Demand

<!-- DOI badge: add the concept ("all versions") DOI after the first Zenodo release -->
[![ORCID](https://img.shields.io/badge/ORCID-0009--0006--2011--3258-brightgreen?logo=orcid)](https://orcid.org/0009-0006-2011-3258)

**Author:** Michael Shatny ([ORCID](https://orcid.org/0009-0006-2011-3258))

An organization runs two hundred applications, and every new need starts another product cycle. AI agents now build applications in an afternoon, but they still build *applications*: products with their own boundary, their own data, and their own release cycle. This paper proposes moving the durable layer beneath the application. **Declared capabilities**, and the data, history, decisions and authority they operate on, persist. Applications, interfaces and synchronization logic are **compiled on demand** by an agentic environment and stay replaceable. Where Methodology-as-Infrastructure compiles *how to think*, Intent-as-Infrastructure compiles *what to reach into*, and Governance-as-Infrastructure compiles *what must be true*, **Capability-as-Infrastructure compiles *what must be possible*.** The application is compiled from it and kept up to date.

> **Data, meaning and principles persist. Agents build and maintain the implementation as the need arises.**

## Read the Paper

- [Capability-as-Infrastructure: Software on Demand](docs/capability-as-infrastructure.md) (concept paper)
- [Reference Architecture: Capability-as-Infrastructure on Cloudflare](docs/reference-architecture-cloudflare.md) (companion)

## Key Argument

| Agents around an application | Capability-as-Infrastructure |
|---|---|
| The unit of design is a product (*we need a CRM*) | The unit of design is a capability declaration |
| Agents build, extend or replace the product | The environment uses, rebuilds or adds capabilities |
| Meaning lives in the product's code and schema | Meaning lives in a continuity record that outlives every implementation |
| Continuity = the product's lifecycle | Continuity = data, history, decisions and authority |
| A specialist is the final technical authority | Competence is supplied by the environment; the human supplies intent and authority |

## The Four Required Properties

For a system to qualify as Capability-as-Infrastructure, all four must hold:

1. **Capability-declared**: the unit of design is a human-readable capability declaration (purpose, data, reconciliation, autonomy, acceptance), not an application
2. **Implementation-compiled**: applications, interfaces and synchronization are compiled from the declaration and the continuity record, and are **replaceable without loss**; persistence of a good implementation is a choice, not the starting unit
3. **Continuity-sovereign**: data, provenance, history and decisions survive every implementation; *observation*, *interpretation* and *accepted state* are kept distinct, so a wrong interpretation never overwrites the original
4. **Human-as-primitive at authority**: the human supplies intent and authority; within granted authority the environment acts; widening access, accepting obligations and irreversible change gate on a human decision

A system in which agents build applications faster, but the application remains the unit of design and the place where meaning lives, is *agents around an application*, not CaI. The four-property test is the diagnostic.

## Status

This is a **concept paper (v0.1)**. It reports no empirical results. Its two central claims are stated as hypotheses, with a validation protocol built on a growing CRM scenario:

- **H1, continuity under replacement:** the environment evolves a working solution on demand while work and data stay continuous.
- **H2, autonomous capability growth:** from a changed declaration, the environment builds, verifies and activates a new capability with data intact, without a human specialist designing the change.

Results are intended for a subsequent version.

## The Paradigm Progression

| Paradigm | What it compiles | What persists | Human role |
|---|---|---|---|
| Methodology-as-Infrastructure | How to think | The runtime | Receives output |
| Intent-as-Infrastructure | What to reach into | The finding artifact of each run | Primitive at the *moment of consequence* |
| Governance-as-Infrastructure | What must be true | The Governed Constraint Set | Primitive at the *moment of formalization* |
| **Capability-as-Infrastructure** | **What must be possible** | **Capabilities + the continuity record** | **Primitive at the *moment of authority*** |

MaI, IaI and GaI move along one axis, **upstreamness**, and GaI is its terminus. CaI opens a second axis, **duration**: not what one run compiles, but what survives while the software is rebuilt. It continues IaI (a declaration compiled by an AI model, extended from a task to an application's lifetime) and composes with GaI (each capability declaration carries its own governed constraints).

## Lineage Outside the Series

- **Local-first software** (Kleppmann et al., 2019): local data, offline work, sync across devices. CaI's reference architecture is local-first in shape; what changes is that **the sync protocol itself is a compiled capability**, designed and migrated by agents.
- **Malleable software** (Ink & Switch, 2025): users reshaping their tools. CaI shares the goal; the mechanism is an environment that *produces* the software from the user's intent.

## Related Work

- [Intent-as-Infrastructure: When the Compiler Is Claude](https://doi.org/10.5281/zenodo.20681522): the paradigm CaI continues
- [Governance-as-Infrastructure: From Audit to Runtime](https://doi.org/10.5281/zenodo.21010922): the upstream terminus CaI composes with
- [Methodology-as-Infrastructure: From Framework to Runtime](https://doi.org/10.5281/zenodo.18946630): the first paradigm in the progression
- [Governance-Driven Design (GDD)](https://doi.org/10.5281/zenodo.20938777): the discipline behind each capability's constraints
- [Semantic Intent as Governance Primitive for Agentic Systems](https://doi.org/10.5281/zenodo.20436088): provenance as a governance primitive

## License

MIT
