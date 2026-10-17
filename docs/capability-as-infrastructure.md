# Capability-as-Infrastructure: Software on Demand

**Author:** Michael Shatny ([ORCID: 0009-0006-2011-3258](https://orcid.org/0009-0006-2011-3258))
**DOI:** [10.5281/zenodo.23438908](https://doi.org/10.5281/zenodo.23438908) (concept DOI — always resolves to the latest version)
**License:** MIT
**Status:** Concept paper, v0.1. It contains no empirical case study; it defines a validation protocol (§5).

---

## Abstract

Methodology-as-Infrastructure (MaI) compiles *how to think* into deterministic runtimes. Intent-as-Infrastructure (IaI) compiles *what to reach into*, with an intelligent compiler and the human reserved at the moment of consequence. Governance-as-Infrastructure (GaI) compiles *what must be true*, before any artifact exists. Each compiles something *per run*. None of them addresses what persists *between* runs once an agent can build the software itself.

This paper proposes **Capability-as-Infrastructure (CaI)**: a paradigm in which the durable unit of a software system is no longer the application but the **declared capability**, together with the data, history, decisions and authority it operates on. Applications, interfaces, synchronization logic and much of the executable code become **compiled, replaceable outputs** of an agentic environment that builds them when a need appears, maintains them while they are useful, and replaces them when they are not. The user describes the work. The environment supplies the competence to deliver it. This is *software on demand*.

Four properties are required: Capability-declared, Implementation-compiled, Continuity-sovereign, and Human-as-primitive at authority. A system in which agents build applications faster, but the application remains the unit of design, delivery and continuity, is *agents around an application*, not CaI. CaI is positioned against two prior lineages it extends, local-first software and malleable software, and as the fourth paper in the `-as-Infrastructure` series, opening a *duration* axis alongside GaI's upstream terminus. This is a concept paper. Its central claims are stated as hypotheses with a concrete validation protocol, to be reported in a subsequent version.

---

## 1. The Problem: The Application Is the Wrong Unit

Consider an organization that runs two hundred applications. Each presents its own interface, holds part of the organization's information, and implements a fixed set of operations. Work happens in the gaps: a person assembles a process by moving between programs, copying a customer from one into another, reconciling what each believes to be true.

Every new need follows the same path. It is framed as a product (*we need a CRM*), specified, built or bought, released, adopted, and then extended, integrated or replaced. The application is the unit of design, the unit of delivery, and, crucially, the unit of continuity. The data lives inside it. When the application is replaced, the data must be migrated out, and much of its meaning, the history of who changed what and why, is lost in the move.

AI agents have compressed the *build* step of that path dramatically. An agent can now produce a working application in an afternoon. But compressing the build does not change the path. The agent is still asked to build *an application*, and the result still carries the same structure: a product with its own boundary, its own data, its own release cycle. Agents around an application make the old unit faster. They do not question whether it is the right unit.

The question this paper asks is upstream of the build:

> **If an environment can build the software a need requires, what should be durable: the application, or something beneath it?**

The answer proposed here is that the durable layer is the **capability**: what the system must be able to do, the data it does it with, the decisions that have been made about that data, and the authority under which it acts. The application is one form that capability takes, today, for this user and this task.

---

## 2. The Concept: Capability-as-Infrastructure

### 2.1 Definition

**Capability-as-Infrastructure (CaI)** is a paradigm in which a software system's durable layer consists of **declared capabilities** and the **continuity record** (data, provenance, history, decisions, authority) they operate on, while applications, interfaces and executable implementations are compiled from that layer by an agentic environment, on demand, and remain replaceable.

The product delivered to the user is not an application. It is a **persistent working environment** that keeps the ability to produce whatever application the current need requires. A CRM, a report, a planning screen or a collaboration tool is assembled from shared data and available capabilities. Its boundaries are set by the current task, while what has been learned and agreed persists between assemblies.

### 2.2 The Four Required Properties

For a system to qualify as Capability-as-Infrastructure, all four must hold.

**1. Capability-declared.** The unit of design is a *capability declaration*: a human-readable statement of what the system must be able to do, which data it uses, what its operations mean, how disagreements are reconciled, what the environment may do autonomously, and how success is recognized. The declaration starts as text (a Markdown or skill file) and need not correspond to any existing adapter or program. It is *symbolic*: the file itself stores no records and executes no operations. It is the point from which an implementation is produced and maintained.

**2. Implementation-compiled.** Applications, interfaces, synchronization functions and storage layouts are *compiled* by the environment from the declaration, the continuity record and prior decisions, and they are **replaceable without loss**. Compilation does not mean regenerating everything on every action: a good implementation can be kept and reused indefinitely. Replaceability is a capability, not an obligation. What CaI forbids is the application being the *only* place where the system's meaning lives.

**3. Continuity-sovereign.** The continuity record is first-class, survives every implementation, and is human-readable and provable, carrying the provenance that earlier work in this series treats as a governance primitive [8]. Keeping the bytes is not enough; the record keeps *meaning*: who changed a record, which object it concerns, what the operation signified, and which decision was taken when changes were merged. It distinguishes three states that are usually collapsed: the **observation** (the original material, as received), the **interpretation** (what an agent concluded from it), and the **accepted working state**. A wrong interpretation can be corrected without losing the original. A system that silently overwrites the original with an agent's reading of it fails this property.

**4. Human-as-primitive at authority.** The human is the source of intent and of authority, not of technical execution. The user states the work, the desired outcome, and the autonomy granted. Within granted authority, the environment acts without re-asking. Extending access, accepting obligations, and making irreversible changes gate on a human decision. Disputed merges of commitments are routed to an authorized person. Technical competence (designing synchronization, choosing a schema, writing migrations) is supplied by the environment. A specialist is not an architectural constant (see §6.2).

A system in which agents build an application faster, but the application remains the unit of design and the place where meaning lives, is *agents around an application*. It is valuable, and it is not CaI. The four-property test is the diagnostic.

### 2.3 Relationship to MaI, IaI and GaI

The `-as-Infrastructure` series has, until now, moved along one axis: **upstreamness**. Each paradigm pins something earlier in the lifecycle, from MaI [7] through IaI [2], and GaI reaches the terminus, because nothing precedes the definition of what correctness means [1]. CaI does not claim a position further upstream. It opens a second axis: **duration**.

| Paradigm | What it compiles | What persists | Human role |
|---|---|---|---|
| Methodology-as-Infrastructure | *How to think* | The runtime | Receives output |
| Intent-as-Infrastructure | *What to reach into* | The finding artifact of each run | Primitive at the *moment of consequence* |
| Governance-as-Infrastructure | *What must be true* | The Governed Constraint Set | Primitive at the *moment of formalization* |
| **Capability-as-Infrastructure** | ***What must be possible*** | **Capabilities + the continuity record; the application is compiled** | **Primitive at the *moment of authority*** |

MaI, IaI and GaI each describe a run: an analysis executes, an intent compiles to an artifact, a constraint set gates. CaI describes a *lifetime*: the sequence of runs through which a working system appears, grows and changes while its users keep working.

CaI is most directly a continuation of IaI. IaI established that a bounded declaration, compiled by an AI model, can replace pre-built executable logic *for a task* [2]. CaI extends the same move *to the application and its whole lifetime*: the capability declaration plays the role of IaI's intent vocabulary, and the compiled application plays the role of IaI's per-run execution. IaI's sovereign artifacts become CaI's continuity record.

CaI composes with GaI rather than competing with it. A capability declaration carries its own constraints, autonomy limits and acceptance criteria: in GaI's terms, a Governed Constraint Set per capability [1][3]. GaI decides what must be true before anything is built; CaI decides what must remain true while it keeps being rebuilt.

### 2.4 Relationship to Local-First and Malleable Software

CaI extends two lineages from outside this series, and is clearer for naming them.

**Local-first software** [4] argued that users should own their data, work offline, and collaborate across devices, with the cloud as a participant rather than the custodian. CaI's reference architecture is local-first in shape: local storage, an outbox of pending changes, synchronization, and conflicts that remain visible. The difference is who builds the synchronization. In local-first systems, engineers design the data model and merge semantics, often using conflict-free replicated data types [5]. In CaI, **the synchronization protocol is itself a compiled capability**: agents design it, implement it, version it and migrate it as the participants change. The reference architecture (companion document) deliberately uses a server-authoritative log per workspace rather than CRDTs, because semantic conflicts (two records about the same customer, or a disputed commitment) need an explicit point of decision, not only convergence.

**Malleable software** [6] argued that users should be able to reshape the tools they use, rather than accept the fixed forms that application vendors ship. CaI shares the goal and changes the mechanism: instead of giving the user tools to modify software, it gives the user an environment that *produces* the software, while the user supplies intent, preferences and authority.

CaI's contribution is not offline-first data or user agency, both of which those lineages established. It is the claim that, with agents able to build and maintain implementations, **the application can be demoted from the unit of continuity to an output**, and the specific form that makes this safe: declared capabilities, a sovereign continuity record, and authority-gated autonomy.

---

## 3. The Mechanism

### 3.1 The Capability Declaration

A capability declaration is short, readable, and incomplete by design. It grows as the system does. The following example illustrates the idea; it is not a required format.

```markdown
# Capability: working with customers

## Purpose
Let the user add a customer today, make a call, record the outcome,
and schedule the next action.

## Data
Customer, contact, call note, next action.
Keep the provenance of every change and the history of decisions.

## Growth
Start with one user working locally.
When a colleague joins, provide shared work and exchange of changes.
Add further capabilities only when a real need appears.

## Reconciliation
Keep each participant's notes independently.
Never discard original values in a disputed merge.
Route ambiguous changes to commitments to an authorized person.

## Autonomy
Allowed: create views, write and test functions within granted authority.
Extending access or making irreversible changes requires a separate decision.

## Acceptance
Records survive restarts and application updates.
Re-delivering a change never duplicates an operation.
After exchange, participants share one state, or see an explicit open conflict.
```

Accepted refinements are written back into the declaration, so that the next implementation inherits what has already been agreed. The declaration is a starting point, not a guarantee: its existence does not mean the capability is ready, and the permissions it describes must still be *enforced* by the runtime, not merely stated in text.

### 3.2 The Continuity Record

Input arrives in many forms: a local database row, an email, a document, a note, the result of an external operation. The environment stores the original material and its provenance, then builds the views and relationships it needs.

Not everything that arrives becomes truth. The continuity record keeps observation, interpretation and accepted state apart (property 3), and names a **source of authority** for the accepted state: a central record, an agreed log, or another explicit scheme. The presence of a coordinating agent does not settle this question by itself.

One practical rule follows: **a local implementation may be disposable, but local data is not**, as long as it holds the only copy of work that has not yet been transmitted.

### 3.3 Synchronization as a Compiled Capability

In CaI, agents take on more than resolving individual conflicts. They design the interaction protocol, write reconciliation functions, negotiate versions and maintain them over time. Three related tasks should be kept distinct:

1. **Delivery:** what was created locally, what was sent, and what the other side accepted.
2. **Semantic reconciliation:** whether two records refer to the same customer, whether changes are compatible, and what a divergence means.
3. **Evolution of the mechanism:** how to change the format, the merge rules and the code while preserving compatibility and data.

Agents can participate in all three. Routine operations run as functions the agents created; new circumstances become a reason to revise the implementation. One constraint is non-negotiable: **agreement between agents must become a verifiable result**: a recorded version, an accepted change, a delivery acknowledgment, or an explicitly open conflict. Agreement reached in conversation is not reconciled data.

### 3.4 Regeneration and Maintenance

*Regeneration* means restoring or creating a working implementation from declarations, stored data, versions and decisions. It does not mean reproducing the previous source code exactly.

The environment can detect a need, propose a change, build the functions, test them against a copy of the data, apply a migration, and observe the result. If the change fails, it uses a recorded recovery path. Code, instructions, schemas and coordination procedures can all be updated. None of this requires a model to change its own weights, and none of it requires agents to propagate themselves across devices.

Each change travels as a **change package**: the reason and expected outcome, the new declaration and implementation, behavioral and compatibility checks, the data migration and its recovery path, and the activation conditions and authority required. The companion document describes how such a package is run as a durable, resumable workflow.

### 3.5 Interfaces Compiled per User

Because the interface is an output, two users of the same workspace can receive different views of the same data. One prefers a compact customer table showing the last contact and next action. Another prefers a list with expandable call history. The environment works from a shared visual language (typography, palette, spacing, recognizable signs for actions and states, accessibility rules) and a set of preferred patterns: tables for comparison, compact summaries, master–detail, parent–detail, progressive disclosure. It combines these per task and per person, and may propose something else when the task calls for it.

Three constraints keep this safe. Personalization never changes access rights or accepted business rules. A summary keeps essential meaning and a clear path to detail; interpretation and uncertainty stay distinguishable, and shortening must never hide a conflict or an obligation. User preferences are stored apart from the implementation of the interface, so a learned layout survives regeneration and is not rebuilt without reason.

> **A shared style guides how interfaces are made. The task and the person decide their form.**

---

## 4. Worked Scenario: One User Today, a Colleague Tomorrow

The first request might read: *"I need a simple CRM. Today I have to call customer ABC. Tomorrow a colleague joins. Start with what's essential."*

**Today**, the environment creates a customer record, a contact, a call note and a next action. Data is stored locally, and every change has a stable identity. Infrastructure for a hundred users is not needed and is not built.

**Tomorrow**, the environment provisions the colleague's workspace and shared exchange. Two local agents and a coordinating agent agree on formats, build the synchronization functions, test them and put a compatible version into service. (This division of roles is illustrative; the number of agents and where they run can vary.)

**As the system grows**, agents evolve the implementation: storage layout, exchange, views and processes. Moving from two users to a hundred requires real engineering changes. In CaI, designing and executing those changes is also part of the environment's work.

**The CRM is not the boundary.** It is the first capability to take form. Procurement, planning, correspondence or reporting can follow, each starting as a declaration, each using the same continuity record, and each combinable with the others in one process. Adding and growing areas of work becomes the environment's business-as-usual, within the limits of its demonstrated competence.

Growth runs along three independent directions:

| Direction | What changes | Example |
|---|---|---|
| Participants | Users, roles, collaboration | One person → a team → an organization |
| Load | Data volume, operation frequency, concurrency | More customers, events, connected devices |
| Capabilities | The range of tasks and their combinations | CRM → procurement → planning → one shared process |

One user can use many capabilities; many users can share one. Load growth calls for infrastructure work; capability growth may call for new sources, permissions and execution mechanisms. The environment organizes that work; it is not assumed that every new capability is equally hard.

---

## 5. Validation Protocol

This version of the paper reports no empirical results. The central claims are stated as hypotheses, with the test that would confirm or refute each.

**H1 — Continuity under replacement.** An environment can evolve a working solution on demand while preserving the continuity of work and data across implementations.

**H2 — Autonomous capability growth.** Given a changed or new declaration, an agent can build a new capability, verify it, and put it into service with existing data intact, without a human specialist designing the change.

The test bed is the CRM scenario of §4, grown one real need at a time.

| Scenario | Observable result |
|---|---|
| First user starts work | Customer, call and next action are stored |
| User works offline | Local changes remain available after restart |
| A colleague joins | Each side receives the data it is permitted to see |
| Both add notes concurrently | Both notes survive exchange |
| A delivery is retried | The operation is not duplicated |
| A semantic conflict occurs | Original values are kept; the conflict is visible |
| The data schema changes | History and meaning survive the migration |
| An agent replaces the interface | Work continues on the same data and rights |
| An update fails | A tested recovery path exists and works |

Passing the synchronization rows supports H1, but does **not** support H2: correct synchronization does not show that the environment can develop the application autonomously. H2 requires a separate experiment: modify a declaration, and observe whether the environment produces, verifies and activates the new capability with data preserved. The metrics to record are time to first useful result, cost of adding a capability, and whether work survives each change.

A reference implementation for running this protocol on Cloudflare (Workers, Durable Objects, the Agents SDK and Workflows) is described in the companion document, *Reference Architecture: Capability-as-Infrastructure on Cloudflare*. CaI does not depend on that provider.

---

## 6. Discussion

### 6.1 When Does a System Qualify as CaI?

The four-property test separates CaI from two neighbors that resemble it.

*Agents around an application* use agents to analyze, design, build and test a product. They may keep data separate from the interface and reuse components. But the application remains the unit of organization: the next need means extending, changing or replacing the product. This fails Capability-declared, and usually Continuity-sovereign, because meaning lives in the product's code and schema.

*AI application builders* generate an application from a prompt. They compile, but they compile *a product*, and its continuity lives inside it. Regenerating the product from a new prompt typically means starting over. They fail Continuity-sovereign.

| Workflow step | Agents around an application | CaI: the environment as the foundation |
|---|---|---|
| The need | Define a product, e.g. a CRM | Define the nearest useful result, e.g. the first call to a customer |
| Organizing the solution | Agents analyze, design, build and test the application | The environment combines data and capabilities, builds and verifies what is missing |
| The working form | An application with its own functions, interfaces and versions | Views and functions for the current task and user |
| The next need | Agents extend, change or replace the product | The environment uses, rebuilds or adds capabilities |
| What carries continuity | The product's lifecycle | Data, history, goals, and the environment's ability to deliver |

In CaI, good applications and components can last a long time. Persistence of a particular application becomes a *choice the environment makes*, not the starting unit of its design.

The two sequences differ in where they begin:

- **Product:** concept → build → go-live → use and new releases.
- **CaI:** running environment → need → first useful work → continuous growth.

This is a difference in how work is organized, not a promised speed-up. A minimal product can also launch fast and evolve continuously. Building the CaI environment itself is real work that must be implemented, tested and operated; the claimed advantage applies to needs met *after* the environment exists, and must be measured (§5).

### 6.2 The Competence Claim

The strongest statement in CaI is this: **if the environment supplies the competence a piece of work requires, the user does not need a separate specialist for it.** The need for competence remains; the need to obtain it from a person is not a given.

Stated that way, the claim is close to a tautology. If something supplies the skill, nobody else has to. The substantive claim is H2: that a real environment can supply it, across the cycle of analysis, design, implementation, integration, verification, deployment and maintenance, reliably enough that a permanent developer or architect need not be designed in as the final authority. CaI's architectural commitment is narrower and testable: **the specialist is not an architectural constant.** Whether a given implementation can operate and evolve without one is an empirical question, and its reliability must be demonstrated by results, not assumed in either direction.

The user remains the customer, the data owner, and the source of goals and authority. None of those roles requires a technical profession.

### 6.3 Open Questions

- **Generated code with granted authority.** Generated code runs in isolation first, and permission to change an interface never implies permission to widen data access or infrastructure rights. Proving that boundary holds under adversarial or mistaken generation is open work.
- **Drift.** Implementations regenerated many times may drift from the intent of their declaration in ways no single change reveals. Acceptance criteria in the declaration are the first defense; whether they are sufficient is untested.
- **Accountability.** When the environment makes a bad change within granted authority, the continuity record shows what happened. It does not settle who is responsible.
- **Cost.** Model calls on demand, verification runs and migrations against copies of data all cost money. Whether CaI is cheaper than buying the two hundred applications is an empirical question, not a premise.
- **External side effects.** A coordinator can guarantee that an operation is accepted once. It cannot by itself guarantee that an action in an arbitrary external system happens exactly once. That requires idempotency keys, state checks or reconciliation procedures supported by the external system.

### 6.4 Limits

CaI does not claim that the architecture described here is implemented in full, or that it automatically replaces enterprise systems. It does not claim novelty for offline-first data, user agency over software, or declarative intent; each has a lineage, cited above. It claims a specific architectural form: declared capabilities, compiled and replaceable implementations, a sovereign continuity record, and authority-gated autonomy, together with a test that distinguishes it from agents that merely build applications faster.

---

## 7. Conclusion

Automation has spent decades moving from operating software to producing it. Capability-as-Infrastructure takes the next step: from producing programs to **sustaining the ability to produce the programs a need requires**. The product delivered to the user becomes a persistent working environment, and any single application becomes one of the forms that environment takes.

The `-as-Infrastructure` progression has answered, in turn, how to think, what to reach into, and what must be true. CaI answers the question that becomes pressing once an agent can build the software itself: what must survive while everything else is rebuilt.

> **Data, meaning and principles persist. Agents build and maintain the implementation as the need arises.**

---

## References

[1] Shatny, M. (2026). *Governance-as-Infrastructure: From Audit to Runtime.* Zenodo. Concept DOI: 10.5281/zenodo.21010922

[2] Shatny, M. (2026). *Intent-as-Infrastructure: When the Compiler Is Claude.* Zenodo. DOI: 10.5281/zenodo.20681522

[3] Shatny, M. (2026). *Governance-Driven Design (GDD): Formalizing Intent Before the Machine Runs.* Zenodo. Concept DOI: 10.5281/zenodo.20938777

[4] Kleppmann, M., Wiggins, A., van Hardenberg, P., & McGranaghan, M. (2019). Local-first software: You own your data, in spite of the cloud. *Proceedings of the 2019 ACM SIGPLAN International Symposium on New Ideas, New Paradigms, and Reflections on Programming and Software (Onward! 2019).* DOI: 10.1145/3359591.3359737

[5] Shapiro, M., Preguiça, N., Baquero, C., & Zawirski, M. (2011). Conflict-free replicated data types. *Stabilization, Safety, and Security of Distributed Systems (SSS 2011).* DOI: 10.1007/978-3-642-24550-3_29

[6] Litt, G., Horowitz, J., van Hardenberg, P., & Matthews, T. (2025). *Malleable software: Restoring user agency in a world of locked-down apps.* Ink & Switch. https://www.inkandswitch.com/essay/malleable-software/

[7] Shatny, M. (2026). *Methodology-as-Infrastructure: From Framework to Runtime.* Zenodo. DOI: 10.5281/zenodo.18946630

[8] Shatny, M. (2026). *Semantic Intent as Governance Primitive for Agentic Systems.* Zenodo. DOI: 10.5281/zenodo.20436088

---

## Appendix A: Time to Work Inside a Running Environment

It helps to separate building the CaI environment from launching the next solution *inside* one that already runs.

| Stage | Agents around an application | A solution inside a running CaI environment |
|---|---|---|
| Concept | Define the minimal version of the product | Define the first useful result |
| Preparation | Build and release a working version | Prepare the minimal capability using the existing environment |
| Go-live | Start using the released application | Start the task as soon as the needed functions are ready |
| Growth | Use of the product, then new releases | Use of the environment, growing capabilities as needed |
| A new area of work | Extend the product, integrate another, or build a new one | Add a capability declaration and its implementation to the environment's normal process |
