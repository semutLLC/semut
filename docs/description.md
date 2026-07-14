# Semut Current Architecture (July 2026)

> Living document describing the current direction of Semut.
>
> This document intentionally reflects the current state of the architecture.
> Migration will happen gradually rather than through a complete rewrite.

---

# Vision

Semut is building a coordination engine between human intentions and executable actions.

The underlying AI model is replaceable.

The long-term value is not the model itself, but Semut's accumulated memory, action network, and coordination knowledge.

---

# Current State

Current implementations exist across multiple repositories.

Some responsibilities are not yet in their ideal locations.

This is expected.

Migration will happen incrementally while maintaining working software.

---

# Current Repositories

## semut-core

Current:

- shared utilities
- local LLM experiments
- beginning of routing layer

Target:

Reusable coordination engine.

Responsibilities:

- routing
- policy
- execution
- registry
- workflow execution
- local LLM interface

---

## semut-remote

Current:

- FastAPI
- dashboard
- authentication
- SSE
- Codex jobs
- Git execution
- Service execution

Target:

Computer administration interface.

Should become primarily:

- UI
- HTTP APIs
- authentication
- SSE
- job monitoring

Business logic gradually migrates into semut-core.

---

## semut-memory

Current:

Research repository.

Target:

Persistent memory.

Responsibilities:

- traces
- feedback
- action memories
- embeddings
- similarity search
- long-term learning

Future action network will likely reside here.

---

## semut-connect

Current:

Research.

Target:

Communication layer.

Responsibilities:

- email
- SMS
- phone
- WhatsApp
- translation
- messaging

Uses semut-core.

---

## semut-trace

Current:

Trace recording application.

Also currently contains much of the Semut roadmap.

Target:

Trace capture application only.

Roadmap and architecture documents should gradually migrate into this repository (semut).

---

# Architectural Direction

Current:

```
User

↓

semut-remote

↓

Git
Service
```

Target:

```
User

↓

Application

↓

semut-core

↓

Policy

↓

Registry

↓

Execution

↓

Result
```

Applications should no longer execute commands directly.

---

# Execution Model

Every executable capability becomes a registered action.

Examples:

```
git.status

git.pull

git.commit

service.status

service.restart

filesystem.read

filesystem.write

docker.restart

calendar.create

email.draft
```

Execution always occurs through the Action Registry.

---

# Action Registry

The registry becomes the canonical list of executable capabilities.

Responsibilities:

- discover actions
- validate actions
- dispatch execution
- expose metadata
- support permissions
- support documentation

---

# Policy Layer

Every execution passes through policy.

Policy determines:

- allowed target
- allowed action
- confirmation requirements
- user permissions
- organization permissions
- risk level

Policy executes before every action.

---

# Routing

Routing converts human requests into structured intent.

Initially:

- deterministic matching
- local LLM

Eventually:

- memory lookup
- action network
- local LLM
- external LLM

Routing never executes actions.

---

# Memory

Semut should gradually replace hardcoded routing with learned coordination memory.

Rather than continuously expanding Python rules, Semut should accumulate explicit knowledge.

Examples:

- successful routes
- corrected routes
- common phrasing
- execution history
- user feedback

This knowledge becomes reusable across applications.

---

# Action Network

Long-term direction.

Action Network connects:

Human intention

↓

Known patterns

↓

Executable actions

↓

Feedback

↓

Updated confidence

Instead of continually retraining LLMs, Semut improves by strengthening its explicit coordination knowledge.

---

# Current Migration Plan

Phase 1

Move Git execution from semut-remote into semut-core.

---

Phase 2

Move Service execution into semut-core.

---

Phase 3

Introduce central Action Registry.

---

Phase 4

Introduce common Policy layer.

---

Phase 5

Move deterministic routing into semut-core.

---

Phase 6

Connect local LLM through routing.

---

Phase 7

Introduce persistent action memory.

---

Phase 8

Introduce Action Network.

---

Phase 9

Allow every Semut application to reuse the same coordination engine.

---

# Design Principles

- Applications should remain thin.
- Execution belongs in semut-core.
- Knowledge belongs in semut-memory.
- UI belongs in applications.
- LLMs assist routing rather than directly executing commands.
- Memory should improve the system over time.
- The underlying LLM should be replaceable without changing the architecture.

---

# Current Status

The current architecture is intentionally evolving.

Working software takes priority over perfect organization.

Repositories will be migrated gradually while preserving compatibility.

Large rewrites should be avoided.

Every migration should reduce duplication and increase reuse without breaking existing applications.


---

# Centralized Today, Swarm Tomorrow

The current Semut architecture is intentionally centralized.

Today, the coordination flow resembles:

```
Human

↓

Routing

↓

Policy

↓

Registry

↓

Execution
```

This architecture is easier to understand, implement, debug, and validate.

It allows Semut to establish reusable interfaces before exploring more distributed coordination models.

This is **not** considered the final architecture.

---

# Long-Term Research Direction

Semut is inspired by swarm systems.

A swarm does not necessarily eliminate hierarchy.

Instead, it replaces rigid centralized decision-making with many local decisions that collectively produce coordinated behavior.

Examples include:

- ant colonies
- immune systems
- neural networks
- Internet routing
- distributed databases

Each contains multiple layers of organization without requiring a single global controller.

Semut aims to explore similar principles.

---

# Possible Future Architecture

Rather than one centralized routing component:

```
Human

↓

Router

↓

Action
```

Semut may evolve toward specialized routing agents:

```
Human

↓

Git Agent

Service Agent

GitHub Agent

Calendar Agent

Filesystem Agent

↓

Consensus

↓

Policy

↓

Execution
```

Likewise, action memories may become distributed rather than centralized.

For example:

```
Human

↓

Memory Nodes

↓

Candidate Actions

↓

Consensus

↓

Execution
```

No single component necessarily owns every decision.

---

# semut-core is an Implementation, Not a Final Theory

The current semut-core should be viewed as the first practical implementation of Semut's coordination research.

It is expected to evolve.

Future experimentation may change:

- routing
- registry
- policy
- memory
- execution
- workflows

The architecture should evolve based on evidence rather than assumptions.

Changing semut-core as understanding improves is considered progress rather than failure.

---

# Guiding Principle

Semut does not attempt to remove hierarchy.

Instead, it explores whether coordination can emerge from:

- explicit memory
- reusable actions
- local knowledge
- feedback
- evolving relationships
- distributed decision-making

The objective is not decentralization for its own sake.

The objective is better coordination.

Centralization and decentralization are implementation choices that should be evaluated empirically.

The architecture should remain flexible enough to support both.
