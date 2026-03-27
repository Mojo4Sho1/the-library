# Ecosystem Library Refoundation

**Status:** Draft design note  
**Intended path:** `docs/design/ECOSYSTEM_LIBRARY_REFOUNDATION.md`  
**Applies to:** the refounded library repo that will support the Merlin ecosystem  
**Primary consumers:** Merlin, my-pi, future client-specific assistant systems, and developer workflows

## Purpose

This document defines how this repository should be refounded so that it becomes a **modular capability library** for the broader Merlin ecosystem rather than a generic prompt/skill distribution repo inherited from an external design philosophy.

The goal is **not** to preserve the original repository as-is. The goal is to keep only the useful high-level ideas and rebuild the repository around the design principles of our own systems.

This document exists so that, when the time comes, we can:

- remove pieces of the inherited repo that do not align with our architecture
- rebuild the useful pieces using our own tooling and conventions
- make the repo serve as a long-term modular library for reusable capabilities
- support future reuse across personal systems and client-specific assistant systems
- preserve clear boundaries between Merlin, my-pi, and this library layer

This repository does **not** need to be fully built now. It is acceptable for it to exist first as a design-driven placeholder until the surrounding systems are mature enough to justify implementation.

---

## Context

The broader ecosystem is expected to evolve along these lines:

- **my-pi** serves as the governed execution substrate for coding-oriented orchestration, specialists, teams, routing, and structured evaluation
- **Merlin** serves as the higher-level assistant orchestration layer that interprets user intent, routes work across capability layers, preserves continuity, and supervises workflows
- this **library repository** will serve as the modular catalog and source-of-truth registry for reusable capabilities that may be shared across systems, projects, and eventually clients

Over time, custom assistant systems may be built for small businesses on top of Merlin. Those systems will likely require custom capabilities, but some of those capabilities will have transferable structure and should be reusable across multiple deployments.

This repository is intended to become the place where that reuse is organized in a disciplined way.

---

## Core Problem This Repo Should Solve

As the ecosystem grows, capabilities will begin to sprawl across:

- prompts
- specialist definitions
- team templates
- workflow patterns
- evaluation assets
- policy bundles
- tool adapters
- client-specific overlays
- domain-specific knowledge structures
- onboarding and operator playbooks

Without a dedicated library layer, reuse becomes informal, duplicated, difficult to trace, and difficult to govern.

This repository should solve that problem by acting as a **capability registry and modular distribution layer** for the Merlin ecosystem.

---

## Repository Mission

This repository should become:

> A modular, provenance-aware, versioned library of reusable capabilities, definitions, templates, and support assets for Merlin-based systems.

That mission implies several key properties:

- capabilities must be identifiable and structured
- capabilities must have clear ownership and provenance
- capabilities must be composable through typed dependencies
- capabilities must support both private reuse and selective downstream transfer
- capabilities must remain distinct from live orchestration logic
- capabilities must support client-specific customization without collapsing into duplication

---

## What This Repo Is

This repo should eventually be:

- a **catalog of reusable capability definitions**
- a **registry of source-controlled modular assets**
- a **distribution layer for internal ecosystem reuse**
- a **provenance and dependency layer**
- a **home for reusable cross-client building blocks**
- a **supporting subsystem for Merlin-based products and research systems**

---

## What This Repo Is Not

This repo should **not** become any of the following:

- the main execution runtime for my-pi
- the orchestration engine for Merlin
- a loose folder of prompts with no metadata
- a generic dumping ground for experimental assets
- a public plugin marketplace
- a markdown-only substitute for typed system architecture
- a place where client-specific secrets or live production state are stored
- a monolithic package that all systems must fully import

Keeping these non-goals explicit is important. This repository should support the ecosystem, not swallow it.

---

## High-Level Design Position

The inherited repository contained useful ideas around capability reuse, references, and distribution, but parts of that design do not align with our current philosophy.

The refounded version of this repo should keep the following ideas:

- modular capability reuse
- reference-oriented organization
- typed dependency thinking
- provenance-awareness
- private-first distribution
- reusable workflows for growing agentic systems

The refounded version should reject or avoid the following as core design assumptions:

- treating markdown files alone as the runtime
- blurring the boundary between distribution and orchestration
- allowing loosely defined assets without strong metadata
- making the library the center of execution rather than a supporting layer
- optimizing primarily for convenience at the cost of architectural clarity

---

## Role in the Merlin Ecosystem

This repository should occupy a distinct layer in the stack.

### my-pi

my-pi owns:

- specialists
- teams
- sequences
- typed contracts
- routing behavior
- state-machine logic
- execution traces
- evaluation artifacts
- execution governance

### Merlin

Merlin owns:

- broad intent interpretation
- cross-capability routing
- continuity
- higher-level workflow supervision
- approvals and boundaries
- user-facing orchestration behavior

### This library repo

This repo should own:

- reusable capability definitions
- capability metadata
- provenance information
- dependency relationships
- install/import/reference policies
- reusable templates and bundles
- modular cross-project and cross-client assets

This separation should remain strict.

---

## Guiding Principles

## 1. Modular First

Everything that lives here should be structured for reuse. If something is highly specific and cannot reasonably transfer across projects, it likely belongs elsewhere unless it is stored as an overlay or client package.

## 2. Typed, Not Vague

Assets should not exist as unlabeled blobs. Each asset should have a type, identity, version, and declared role.

## 3. Provenance Matters

Every reusable capability should have a traceable source, owner, and version lineage.

## 4. Private First

This repo should support internal and client-limited reuse by default. Public distribution is not the main design target.

## 5. Separation of Concerns

This repo should organize and distribute capabilities. It should not become the orchestration engine.

## 6. Reuse Without Drift

Capabilities should be reusable across projects without requiring uncontrolled copying and mutation.

## 7. Client Modularity Without Cross-Contamination

Client-specific capabilities should be composable from reusable building blocks without leaking one client's private structure into another client's system.

## 8. Build Only What the Ecosystem Can Support

This repo should grow in phases. It should not be overbuilt before Merlin and my-pi are mature enough to consume it.

---

## Intended Capability Classes

This repo should eventually support a typed set of reusable objects. The exact list may evolve, but an initial design should assume support for at least the following.

## 1. Prompt Assets

Reusable prompt modules, prompt templates, system-instruction components, response style constraints, and task framing patterns.

## 2. Skill Assets

Reusable structured capabilities that define how a task should be approached, including expected inputs, outputs, dependencies, and operational guidance.

## 3. Specialist Definitions

Reusable specialist-level definitions that can be consumed by my-pi or related systems.

## 4. Team Templates

Reusable team structures or team-definition fragments that represent common workflow patterns.

## 5. Workflow Patterns

Reusable multi-step patterns that are broader than a single specialist but narrower than a full product deployment.

## 6. Evaluation Assets

Benchmarks, test suites, task sets, critique templates, artifact schemas, and evaluation policies.

## 7. Policy Bundles

Reusable constraints, approval requirements, escalation policies, compliance overlays, or domain-specific operational policies.

## 8. Tool Adapters and Tool Contracts

Definitions describing how external tools are integrated, invoked, or constrained.

## 9. Domain Bundles

Reusable domain-specific modular packages such as small-business support workflows, intake flows, FAQ logic, operational checklists, or sector-specific templates.

## 10. Client Overlays

Client-specific extension layers that build on reusable assets rather than replacing them wholesale.

---

## Target Metadata Model

Every reusable object in this repo should ultimately have structured metadata. The exact schema can evolve, but each asset should be expected to declare the following categories of information.

## Required identity fields

- asset id
- asset type
- human-readable name
- version
- status
- owner or maintainer

## Required purpose fields

- summary
- intended use
- expected consumers
- scope boundaries

## Required dependency fields

- required dependencies
- optional dependencies
- compatibility notes

## Required provenance fields

- source repo or source path
- creation origin
- author or maintainer lineage
- change history reference

## Required operational fields

- expected input shape
- expected output shape
- validation expectations
- usage notes

## Required governance fields

- private/internal/client/public visibility
- approval requirements
- deprecation status
- migration notes, when applicable

The schema does not need to be perfect immediately, but the repo should be built around the assumption that capabilities are structured entities, not loose files.

---

## Typed Dependency Philosophy

This repo should adopt typed dependency references from the beginning.

Dependencies should not be generic strings with unclear meaning. Dependencies should identify both the object and its type.

Illustrative examples:

- `prompt:planner.acceptance_criteria`
- `skill:artifact.review`
- `specialist:code.builder`
- `team:implementation.loop`
- `policy:client.approval.required`
- `eval:team.session.audit`
- `overlay:client.acme.support`

This matters for several reasons:

- it reduces ambiguity
- it supports validation
- it enables better tooling later
- it makes reuse auditable
- it prevents different classes of objects from collapsing into one namespace

The exact naming convention can change, but the typed dependency principle should remain.

---

## Versioning Philosophy

This repo must be version-aware.

Over time, reusable capabilities will evolve. Some changes will be additive. Others will break compatibility. Some will be client-safe. Others will be internal-only.

At minimum, the system should eventually support:

- explicit version identity
- compatibility notes
- deprecation markers
- replacement guidance
- version-to-version migration notes when appropriate

This is especially important because this repo is intended to support growing service quality over time. Reuse without versioning becomes drift. Drift becomes confusion.

---

## Provenance Philosophy

This repo should make it easy to answer questions like:

- where did this capability come from?
- who created it?
- what project introduced it?
- what client, if any, influenced its shape?
- what reusable core was extracted from that work?
- which systems currently depend on it?
- what version is in use where?

That level of provenance will matter once the ecosystem spans multiple repos, systems, and client deployments.

---

## Reuse Strategy for Future Client Systems

A major future use case for this repo is the creation of custom assistant systems for small businesses.

That future requires a careful reuse model.

### Reusable core

Some capabilities should be broad and cross-client:

- intake patterns
- scheduling patterns
- response formatting patterns
- escalation logic
- operational playbooks
- QA/evaluation scaffolds
- domain-agnostic workflow templates

### Domain-level reusable modules

Some capabilities should be reusable within a specific business category:

- appointment workflows
- lead qualification flows
- service estimate support
- support triage
- inventory inquiry handling
- FAQ retrieval patterns
- policy explanation patterns

### Client overlays

Some capabilities will be client-specific:

- business rules
- services offered
- communication style
- approval constraints
- local operating hours
- employee roles
- company-specific policies
- proprietary workflows

The system should encourage extracting reusable cores from client work while keeping client-specific overlays separate.

This repo should help that happen intentionally rather than informally.

---

## Desired Packaging Model

This repo should eventually support a layered packaging model.

## 1. Core reusable modules

Assets that are broad, internal, and likely to be shared across many systems.

## 2. Domain bundles

Reusable bundles for particular verticals or business domains.

## 3. Product bundles

Reusable bundles for a specific Merlin-based product or internal system.

## 4. Client overlays

Client-specific capability layers that attach to reusable bundles.

This layered model supports both scale and modularity.

---

## Repository Structure Direction

The exact structure can evolve, but the repo should eventually move toward a directory layout that reflects typed capability classes.

An illustrative structure might look like this:

~~~text
docs/
  design/
  foundations/
  playbooks/

registry/
  assets/
  bundles/
  overlays/
  policies/

prompts/
skills/
specialists/
teams/
workflows/
evaluations/
policies/
domains/
clients/

schemas/
examples/
tools/
~~~

This is **not** a command to implement the structure immediately. It is a direction for how the repo should evolve once implementation begins.

The important idea is that the layout should reflect type boundaries and lifecycle boundaries.

---

## What Should Be Removed or Reworked from the Inherited Repo

When this repo is actively rebuilt, we should remove or replace inherited assumptions that do not fit our systems.

## Remove as primary philosophy

- markdown-as-runtime assumptions
- command ergonomics that substitute for architecture
- overly generic "agent library" framing
- implementation details tied to an external ecosystem we do not control
- any packaging logic that assumes our systems consume assets in the original format
- any terminology that conflicts with Merlin or my-pi concepts

## Replace with our own equivalents

- our own asset schemas
- our own capability taxonomy
- our own naming conventions
- our own dependency model
- our own provenance model
- our own integration paths with Merlin and my-pi
- our own governance and evaluation expectations

## Preserve only if still useful

- high-level idea of modular capability distribution
- reference-oriented reuse
- private-first thinking
- search/discovery concept
- sync/install/import concept, if later justified
- dependency resolution concept, but in our own form

---

## How This Repo Should Integrate with my-pi

This repo should not be required for my-pi to exist.

Instead, integration should happen gradually and only when the ecosystem is ready.

Potential future integration points:

- my-pi imports or references specialist definitions from this repo
- my-pi consumes reusable team templates or workflow fragments from this repo
- my-pi stores evaluation schemas or benchmark definitions here
- my-pi reads policy bundles or constraints maintained here
- my-pi resolves typed references into local runtime-ready definitions

What should **not** happen:

- my-pi becoming dependent on this repo for basic execution before both systems are stable
- my-pi outsourcing its core orchestration logic to this repo
- my-pi losing clarity about which pieces are execution-time objects versus library-time objects

---

## How This Repo Should Integrate with Merlin

This repo should eventually help Merlin answer questions such as:

- what capabilities exist?
- what reusable bundles are available?
- what domain modules are compatible with this use case?
- what client overlays already exist?
- what reusable pieces can be assembled for a new assistant deployment?

Potential Merlin interactions include:

- catalog lookup
- capability discovery
- reuse planning
- client system composition
- provenance-aware deployment planning

What should **not** happen:

- Merlin treating this repo as its memory
- Merlin depending on this repo for all runtime decision-making
- Merlin collapsing catalog concerns into orchestration concerns

---

## Personal Workflow Benefits

Even before this repo becomes a formal ecosystem subsystem, it may eventually support your workflow in several ways:

- cataloging reusable prompt assets
- organizing team templates and evaluation patterns
- preserving modular work across multiple projects
- reducing repeated reinvention
- surfacing transferable ideas from client work
- helping identify what should be generalized and what should remain local

This means the repo may become useful before it is fully productized, but it should still be built with the long-term architecture in mind.

---

## Build Timing Guidance

This repo does **not** need to be implemented immediately.

It should become active only when at least one of the following becomes true:

- Merlin begins consuming reusable modular capabilities
- my-pi reaches a point where specialists or teams should be shared across repos
- multiple client systems begin to share overlapping structures
- prompt/skill/workflow sprawl begins to slow development
- provenance and reuse become operational pain points

Until then, this repo can remain a design-first repository.

---

## Phased Refoundation Plan

## Phase 0: Design-Only Incubation

### Goal

Define what this repo should become before building anything.

### Deliverables

- this design note
- supporting design notes as needed
- initial capability taxonomy
- initial metadata schema proposals
- naming and versioning principles
- clear ecosystem boundaries

### Output

A repo that is intentionally not yet operational, but has a strong conceptual foundation.

---

## Phase 1: Repository Cleanup and Reframing

### Goal

Remove inherited concepts that do not fit and reframe the repo around our architecture.

### Actions

- remove or archive inherited docs that assume the original runtime philosophy
- replace repo description and README with ecosystem-specific framing
- establish a `docs/design/` area for future design notes
- rename concepts where necessary to align with Merlin and my-pi
- identify which inherited files are still useful as inspiration only

### Output

A clean repo that reflects our intended direction, even if it still contains little executable functionality.

---

## Phase 2: Capability Taxonomy and Schema Foundations

### Goal

Define what kinds of objects the repo will hold and how they are described.

### Actions

- define initial asset classes
- define minimal metadata schema
- define typed dependency rules
- define naming conventions
- define versioning expectations
- define provenance expectations

### Output

A schema-first library foundation.

---

## Phase 3: Minimal Registry Layer

### Goal

Support a basic internal registry of reusable assets.

### Actions

- add registry structure
- support identity and metadata validation
- define minimal import/reference model
- support local discovery of typed capabilities
- create examples for one or two asset types only

### Output

A minimal but disciplined capability library.

---

## Phase 4: Ecosystem Integration

### Goal

Allow Merlin and my-pi to consume selected reusable assets from this repo.

### Actions

- define import or reference interfaces
- define runtime conversion rules where needed
- define compatibility checks
- add example integration paths
- support version-aware asset selection

### Output

A real supporting layer for the ecosystem.

---

## Phase 5: Domain and Client Modularity

### Goal

Support cross-client reuse while preserving client-specific overlays.

### Actions

- add domain bundle structure
- add client overlay structure
- define inheritance/composition rules
- define separation requirements for reusable versus client-specific assets
- define extraction workflow for turning client work into reusable library components

### Output

A library layer that helps future assistant systems improve over time.

---

## Phase 6: Governance, Tooling, and Maturity

### Goal

Add operational discipline once the repo is genuinely useful.

### Actions

- add validation tooling
- add provenance inspection
- add dependency graph tooling
- add deprecation workflows
- add review/approval rules for new reusable assets
- add migration guidance for breaking changes

### Output

A mature ecosystem library rather than a loose collection of reusable files.

---

## Recommended Near-Term Deliverables for This Repo

Since this repo is not yet needed operationally, the next useful documents are likely design documents rather than code.

Candidate future docs for this repo:

- `docs/design/CAPABILITY_TAXONOMY.md`
- `docs/design/ASSET_METADATA_SCHEMA.md`
- `docs/design/TYPED_DEPENDENCY_MODEL.md`
- `docs/design/DOMAIN_BUNDLES_AND_CLIENT_OVERLAYS.md`
- `docs/design/INTEGRATION_WITH_MERLIN_AND_MY_PI.md`
- `docs/design/VERSIONING_AND_PROVENANCE.md`

These should be added only as needed.

---

## Suggested Initial README Reframing

When this repo is actively cleaned up, the README should roughly communicate the following message:

- this is a modular capability library for the Merlin ecosystem
- it is not the execution runtime
- it exists to support reusable assets, provenance, and composable system-building
- it is intended to grow into a supporting layer for Merlin-based assistants and my-pi-compatible systems
- it is currently in a design-first state

The README should be short and directional, not overloaded with premature commands or implementation claims.

---

## Governance Expectations

This repo should eventually have clear rules for what may be added.

A reusable asset should be admitted only if it is:

- sufficiently modular
- sufficiently documented
- properly typed
- versioned
- provenance-aware
- not merely a private copy of one-off work
- likely to be useful beyond its source context

This matters because otherwise the repo will become a cluttered archive instead of a true library.

---

## Extraction Philosophy for Future Client Work

When a future client project produces something useful, the default question should be:

> Is there a reusable core here that should live in the library?

That question should not be answered casually.

A good extraction candidate is something that:

- appears across multiple deployments
- expresses a stable pattern
- is not dependent on client-private facts
- can be parameterized cleanly
- improves future build speed or quality

A bad extraction candidate is something that:

- depends heavily on one client's proprietary constraints
- is tightly coupled to a one-off deployment
- lacks clear boundaries
- is too immature to stabilize
- would create confusion if reused

This extraction discipline is how the service quality can improve over time without turning the library into a mess.

---

## Open Questions and Ambiguities

The following questions should remain open until implementation is closer.

## Identity and schema questions

1. What should the first-class asset types be in version one of this repo?
2. Should prompts, skills, specialists, and teams all use one shared metadata schema with extensions, or separate schemas per type?
3. What is the minimum metadata required before an asset is allowed into the library?

## Dependency questions

4. How strict should typed dependencies be from the beginning?
5. Should dependencies always be version-pinned?
6. How should optional dependencies be represented?

## Integration questions

7. How should Merlin discover assets from this repo?
8. How should my-pi convert reusable definitions from this repo into runtime-ready forms?
9. Should this repo favor reference-based consumption, copy-based vendoring, or a hybrid model?

## Packaging questions

10. What should be the difference between a reusable asset, a bundle, and an overlay?
11. How should domain bundles compose with client overlays?
12. Should client overlays ever live in this repo, or only reusable abstractions extracted from them?

## Governance questions

13. Who approves new reusable assets?
14. When should an asset be marked deprecated?
15. What review process should exist for assets extracted from paid client work?

## Privacy and boundary questions

16. How do we ensure reusable cores are extracted without leaking client-private information?
17. Should this repo include only internal reusable abstractions, with client overlays stored elsewhere?
18. What visibility levels should exist for internal, client-limited, and broader reusable assets?

## Tooling questions

19. What tooling is actually necessary before this repo becomes useful?
20. How much of discovery, validation, and packaging should be automated versus documented?
21. What is the lightest possible tooling layer that still preserves discipline?

---

## Non-Goals

This refoundation effort does **not** aim to do the following:

### 1. Replace Merlin or my-pi

This repo supports those systems. It does not replace them.

### 2. Become operational before the ecosystem needs it

Premature implementation will likely produce the wrong abstractions.

### 3. Preserve the inherited repository's philosophy wholesale

We are not maintaining the original design as the governing model.

### 4. Turn every useful file into a reusable asset

Reuse must be selective and disciplined.

### 5. Optimize for convenience at the cost of clarity

A capability library is only useful if it remains understandable, composable, and governable.

### 6. Force all future systems into one giant shared bundle

Modularity should remain real, not rhetorical.

---

## Initial Recommendation

When this repo is revisited for active development, the first concrete move should be:

1. clean the inherited framing
2. establish `docs/design/`
3. keep the repo design-first for a while
4. define the capability taxonomy and metadata model
5. only then begin building the minimal registry layer

That sequence preserves architectural clarity and reduces the risk of rebuilding the wrong thing.

---

## Summary

This repository should be rebuilt as a **modular ecosystem library** for reusable capabilities that support Merlin, my-pi, and future client-specific assistant systems.

It should:

- preserve modular reuse
- support typed dependencies
- preserve provenance
- enable cross-project and cross-client learning
- remain separate from runtime orchestration
- grow gradually as the surrounding ecosystem matures

The long-term value of this repo is not that it stores miscellaneous agent assets. Its value is that it becomes the place where reusable capability building blocks are organized, versioned, and made transferable across systems without sacrificing architectural discipline.