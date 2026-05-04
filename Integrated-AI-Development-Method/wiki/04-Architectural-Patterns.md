# Architectural Patterns

*System-level patterns for structuring applications*

---

## Overview

Architectural patterns provide high-level structures for organizing code and defining relationships between major components.

## Layered Architecture

**Intent**: Organize code into horizontal layers with specific responsibilities.

**Typical Layers**:
```
┌─────────────────────────────────┐
│         Presentation            │  (UI, Controllers)
├─────────────────────────────────┤
│         Application             │  (Use Cases, Commands)
├─────────────────────────────────┤
│           Domain                │  (Entities, Business Rules)
├─────────────────────────────────┤
│       Infrastructure            │  (Database, External Services)
└─────────────────────────────────┘
```

**When to Use**:
- Traditional business applications
- When clear separation of concerns exists
- Teams are organized by layer

**Pros**: Clear separation, easy to understand
**Cons**: Can lead to "architecture sinking" where domain depends on infrastructure

---

## Hexagonal Architecture (Ports and Adapters)

**Intent**: Isolate the core business logic from external concerns.

**Structure**:
```
        ┌──────────────────────────────┐
        │         Adapters              │
        │   (Primary)    (Secondary)   │
        │      ↓            ↑          │
        │   Ports         Ports         │
        │      ↓            ↑          │
        │   ┌──────────────┐             │
        │   │ Application │             │
        │   │   Core      │             │
        │   │  (Domain)   │             │
        │   └──────────────┘             │
        └──────────────────────────────┘
```

**When to Use**:
- Testability is critical
- Multiple ways to interact with the same logic
- External dependencies should not leak into domain

---

## Onion Architecture

**Intent**: Place domain at the center, with dependencies pointing inward.

**Layers** (inside to outside):
1. Domain (entities, value objects)
2. Application Services (use cases)
3. Infrastructure (persistence, external services)
4. UI (controllers, presenters)

**Key Principle**: Dependencies only point inward. Outer layers can depend on inner layers, never the reverse.

---

## Clean Architecture

**Intent**: Separate concerns into distinct layers with strict dependency rules.

**Layers**:
```
┌─────────────────────────────────────────────┐
│                  UI Layer                    │
├─────────────────────────────────────────────┤
│              Devices Layer                   │
├─────────────────────────────────────────────┤
│            Presenters Layer                  │
├─────────────────────────────────────────────┤
│             Use Cases Layer                  │
├─────────────────────────────────────────────┤
│            Entities Layer                    │
├─────────────────────────────────────────────┤
│          Frameworks & Drivers               │
└─────────────────────────────────────────────┘
```

**Key Principle**: Source code dependencies only point toward inner layers.

---

## CQRS (Command Query Responsibility Segregation)

**Intent**: Separate read and write operations into different models.

**Structure**:
```
Commands (Write)              Queries (Read)
      ↓                            ↑
┌──────────────┐            ┌──────────────┐
│    Command   │            │     Query    │
│   Handlers   │            │  Handlers    │
└──────────────┘            └──────────────┘
      ↓                            ↑
┌──────────────────────────────────────────┐
│              Event Bus                    │
└──────────────────────────────────────────┘
      ↓                            ↑
┌──────────────┐            ┌──────────────┐
│   Write DB   │ ──────── → │   Read DB   │
└──────────────┘            └──────────────┘
```

**When to Use**:
- Read/write workloads differ significantly
- Complex domain with many queries
- Need for different read models (projections)

---

## Event-Driven Architecture

**Intent**: Build systems around the production and consumption of events.

**Components**:
- **Event Producer**: Detects and publishes events
- **Event Consumer**: Receives and processes events
- **Event Channel**: Transport mechanism (message broker)

**When to Use**:
- Microservices integration
- Real-time event processing
- Loose coupling between services

---

## Microservices Architecture

**Intent**: Decompose applications into small, independent services.

**Principles**:
- Single responsibility per service
- Services own their data (database per service)
- Communication via lightweight protocols (HTTP, messaging)
- Services can be independently deployed

**When to Use**:
- Large teams working on independent components
- Need for independent scaling
- Multiple technology stacks

**Considerations**:
- Increased operational complexity
- Distributed system challenges (network failures, consistency)

---

## Pipes and Filters

**Intent**: Process data through a series of processing stages.

**Structure**:
```
Input → Filter1 → Filter2 → Filter3 → Output
            ↓           ↓           ↓
         (transform) (transform) (transform)
```

**When to Use**:
- Data processing pipelines (ETL, stream processing)
- Reusable, composable processing steps

---

## Selection Guide

| Need | Pattern |
|------|---------|
| Traditional web app | Layered Architecture |
| Testability focus | Hexagonal, Onion, Clean |
| Complex reads | CQRS |
| Service integration | Event-Driven |
| Large team, scaling | Microservices |
| Data processing | Pipes and Filters |

---

## Related

- [GoF Object-Oriented Patterns](03-GoF-Object-Oriented-Patterns.md)
- [Cloud and Distributed Systems Patterns](07-Cloud-and-Distributed-Systems-Patterns.md)
- [Integration and Messaging Patterns](06-Integration-and-Messaging-Patterns.md)
