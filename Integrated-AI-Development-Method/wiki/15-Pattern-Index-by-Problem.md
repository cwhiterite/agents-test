# Pattern Index by Problem

*Find the right pattern for your specific challenge*

---

## Overview

Rather than memorizing patterns, it's more effective to understand problems and find patterns that address them. Use this index to find relevant patterns based on your problem.

## Object Creation Problems

| Problem | Patterns |
|---------|----------|
| Creating objects with complex construction | [Builder](../wiki/03-GoF-Object-Oriented-Patterns.md#builder) |
| Creating families of related objects | [Abstract Factory](../wiki/03-GoF-Object-Oriented-Patterns.md#abstract-factory) |
| Creating different types of objects | [Factory Method](../wiki/03-GoF-Object-Oriented-Patterns.md#factory-method) |
| Cloning existing objects | [Prototype](../wiki/03-GoF-Object-Oriented-Patterns.md#prototype) |
| Ensuring single instance | [Singleton](../wiki/03-GoF-Object-Oriented-Patterns.md#singleton) |

## Structure and Composition Problems

| Problem | Patterns |
|---------|----------|
| Adding behavior dynamically | [Decorator](../wiki/03-GoF-Object-Oriented-Patterns.md#decorator) |
| Representing part-whole hierarchies | [Composite](../wiki/03-GoF-Object-Oriented-Patterns.md#composite) |
| Hiding implementation details | [Facade](../wiki/03-GoF-Object-Oriented-Patterns.md#facade) |
| Accessing remote/local objects | [Proxy](../wiki/03-GoF-Object-Oriented-Patterns.md#proxy) |
| Converting incompatible interfaces | [Adapter](../wiki/03-GoF-Object-Oriented-Patterns.md#adapter) |
| Decoupling abstraction from implementation | [Bridge](../wiki/03-GoF-Object-Oriented-Patterns.md#bridge) |

## Communication and Responsibility Problems

| Problem | Patterns |
|---------|----------|
| Notifying multiple observers | [Observer](../wiki/03-GoF-Object-Oriented-Patterns.md#observer) |
| Processing requests in sequence | [Chain of Responsibility](../wiki/03-GoF-Object-Oriented-Patterns.md#chain-of-responsibility) |
| Parameterizing operations | [Command](../wiki/03-GoF-Object-Oriented-Patterns.md#command) |
| Encapsulating algorithms | [Strategy](../wiki/03-GoF-Object-Oriented-Patterns.md#strategy), [Template Method](../wiki/03-GoF-Object-Oriented-Patterns.md#template-method) |
| Managing object state changes | [State](../wiki/03-GoF-Object-Oriented-Patterns.md#state) |
| Separating algorithms from structure | [Visitor](../wiki/03-GoF-Object-Oriented-Patterns.md#visitor) |

## Application Architecture Problems

| Problem | Patterns |
|---------|----------|
| Organizing traditional web app | [Layered Architecture](../wiki/04-Architectural-Patterns.md#layered-architecture) |
| Isolating domain from infrastructure | [Hexagonal](../wiki/04-Architectural-Patterns.md#hexagonal-architecture), [Onion](../wiki/04-Architectural-Patterns.md#onion-architecture), [Clean](../wiki/04-Architectural-Patterns.md#clean-architecture) |
| Separating read and write | [CQRS](../wiki/04-Architectural-Patterns.md#cqrs-command-query-responsibility-segregation) |
| Building loosely coupled services | [Event-Driven](../wiki/04-Architectural-Patterns.md#event-driven-architecture) |
| Decomposing large applications | [Microservices](../wiki/04-Architectural-Patterns.md#microservices-architecture) |

## Data and Persistence Problems

| Problem | Patterns |
|---------|----------|
| Mapping objects to database | [ORM patterns](08-Data-and-Domain-Patterns.md) |
| Managing domain model | [Domain Model](08-Data-and-Domain-Patterns.md#domain-model), [Transaction Script](08-Data-and-Domain-Patterns.md#transaction-script) |
| Handling temporal data | [Temporal Patterns](08-Data-and-Domain-Patterns.md#temporal-patterns) |
| Event sourcing state | [Event Sourcing](08-Data-and-Domain-Patterns.md#event-sourcing) |

## Concurrency Problems

| Problem | Patterns |
|---------|----------|
| Managing threads | [Thread Pool](../wiki/10-Concurrency-Patterns.md#thread-pool) |
| Coordinating parallel tasks | [Future/Promise](../wiki/10-Concurrency-Patterns.md#futurepromise) |
| Producer-consumer problems | [Producer-Consumer](../wiki/10-Concurrency-Patterns.md#producer-consumer) |
| Managing state in async code | [Async Messaging](../wiki/10-Concurrency-Patterns.md#async-messaging) |

## UI Problems

| Problem | Patterns |
|---------|----------|
| Organizing UI code | [MVP](../wiki/09-UI-and-Frontend-Patterns.md#mvp-model-view-presenter), [MVC](../wiki/09-UI-and-Frontend-Patterns.md#mvc-model-view-controller), [MVVM](../wiki/09-UI-and-Frontend-Patterns.md#mvvm-model-view-viewmodel) |
| Handling navigation | [Navigation patterns](../wiki/09-UI-and-Frontend-Patterns.md#navigation-patterns) |
| Two-way data binding | [Observer pattern implementation](../wiki/09-UI-and-Frontend-Patterns.md#data-binding) |
| Managing form state | [Form state patterns](../wiki/09-UI-and-Frontend-Patterns.md#form-state) |

## Testing Problems

| Problem | Patterns |
|---------|----------|
| Testing with dependencies | [Dependency Injection](../wiki/11-Testing-and-Quality-Patterns.md#dependency-injection) |
| Managing test data | [Test Data Builder](../wiki/11-Testing-and-Quality-Patterns.md#test-data-builder), [Object Mother](../wiki/11-Testing-and-Quality-Patterns.md#object-mother) |
| Testing async code | [Async testing patterns](../wiki/11-Testing-and-Quality-Patterns.md#async-testing) |
| Preventing test brittleness | [Test isolation](../wiki/11-Testing-and-Quality-Patterns.md#test-isolation) |

## Integration Problems

| Problem | Patterns |
|---------|----------|
| System integration | [Point-to-Point](../wiki/06-Integration-and-Messaging-Patterns.md#point-to-point), [Hub-and-Spoke](../wiki/06-Integration-and-Messaging-Patterns.md#hub-and-spoke) |
| Async communication | [Message Queue](../wiki/06-Integration-and-Messaging-Patterns.md#message-queue), [Publish-Subscribe](../wiki/06-Integration-and-Messaging-Patterns.md#publish-subscribe) |
| API gateway patterns | [API Gateway](../wiki/06-Integration-and-Messaging-Patterns.md#api-gateway) |
| Data synchronization | [Saga](../wiki/06-Integration-and-Messaging-Patterns.md#saga) |

## Quick Reference: Pattern Purpose Map

| If You Need... | Consider... |
|----------------|-------------|
| Flexibility in implementation | Strategy, Bridge |
| Simplified interface to complex system | Facade |
| Dynamic behavior addition | Decorator, Observer |
| Controlled object creation | Builder, Factory |
| Structure for complex compositions | Composite, Decorator |
| Decoupling senders from receivers | Observer, Mediator, Chain of Responsibility |
| Managing state machines | State |
| Versioned commands | Command |
| Isolated business logic | Hexagonal, Onion, Clean |
| Event-based consistency | Event Sourcing, CQRS |
| Distributed transactions | Saga |

---

## Finding Patterns for New Problems

1. **Describe the problem** in plain terms
2. **Identify the concern**: Creation? Structure? Behavior? Architecture?
3. **Consider forces**: What constraints or requirements must the solution handle?
4. **Evaluate candidate patterns** against the problem
5. **Apply judiciously**: Patterns are tools, not mandates

---

## Related

- [GoF Object-Oriented Patterns](03-GoF-Object-Oriented-Patterns.md)
- [Architectural Patterns](04-Architectural-Patterns.md)
- [Anti-Patterns](12-Anti-Patterns.md)
