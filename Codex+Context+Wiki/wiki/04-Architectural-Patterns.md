# Architectural Patterns

Architectural patterns shape module, application, or system boundaries. They usually affect team ownership, deployability, test strategy, operational risk, and long-term change.

## Layered Architecture

Organizes code into layers such as presentation, application, domain, and infrastructure.

Use when:

- The app has clear vertical responsibilities.
- You want predictable dependency direction.
- The team needs a familiar default.

Risks:

- Layers become pass-through ceremony.
- Domain logic leaks into UI or persistence.

## Hexagonal Architecture / Ports and Adapters

Core application logic communicates through ports; adapters handle databases, APIs, UI, queues, and frameworks.

Use when:

- Business logic should be testable without infrastructure.
- Integrations are volatile.
- You want strong separation between policy and mechanism.

Risks:

- Too many ports for simple CRUD.
- Generic abstractions that do not match business needs.

## Clean Architecture

A dependency-rule architecture where inner policy layers are independent of outer frameworks and infrastructure.

Use when:

- Business rules are valuable and long-lived.
- Frameworks, databases, and delivery mechanisms may change.

Risks:

- Boilerplate if the domain is simple.
- Misplaced interfaces in generic shared packages.

## Microkernel / Plugin Architecture

A stable core is extended by plugins.

Use when:

- Features vary by customer, tenant, integration, or extension ecosystem.
- The core lifecycle should be separate from extensions.

Risks:

- Versioning and plugin compatibility become product concerns.

## Event-Driven Architecture

Components communicate by emitting and consuming events.

Use when:

- Producers and consumers should be decoupled.
- Multiple downstream reactions are expected.
- Work can be eventually consistent.

Risks:

- Harder tracing, ordering, idempotency, and replay.
- Events become undocumented integration contracts.

## Microservices

System decomposed into independently deployable services around business capabilities.

Use when:

- Team autonomy and independent deployment are more important than local simplicity.
- Boundaries are well understood.
- Operational maturity exists.

Risks:

- Distributed data consistency.
- Network failure, latency, observability, and deployment complexity.
- Premature decomposition around unstable domains.

## Modular Monolith

Single deployable application with strong internal module boundaries.

Use when:

- The team wants simplicity but also wants boundaries that can later be extracted.
- The domain is still evolving.

Risks:

- Boundaries are social unless enforced by tests, package rules, or build tooling.

## CQRS

Separate read and write models.

Use when:

- Read and write workloads have different shapes.
- Queries need denormalized projections.
- Command validation differs from query needs.

Risks:

- Synchronization lag.
- More moving parts and harder debugging.

## Model-View-Controller and Related UI Architectures

Separates user interaction, presentation, and state or domain logic.

Use when:

- UI complexity needs explicit boundaries.
- Testing presentation logic matters.

Related patterns:

- MVC
- MVP
- MVVM
- Flux/Redux-style unidirectional data flow

