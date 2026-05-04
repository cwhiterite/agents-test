# Pattern Index by Problem

Use this page when you know the design problem but do not know which pattern family to inspect.

## Object and Module Design

| Problem | Candidate Patterns |
| --- | --- |
| Object creation is complex | Builder, Factory Method, Abstract Factory |
| Many algorithms share one interface | Strategy |
| Behavior changes by lifecycle state | State, State Machine |
| Need undo, queueing, audit, or retry of actions | Command |
| Need to adapt an external API | Adapter, Anti-Corruption Layer |
| Need a simpler boundary over complex subsystem | Facade |
| Need optional behavior around same interface | Decorator, Proxy |
| Need to traverse a collection without exposing internals | Iterator |
| Need to notify many dependents | Observer, Publish/Subscribe |

## Application Architecture

| Problem | Candidate Patterns |
| --- | --- |
| Need a familiar web/app structure | Layered Architecture, MVC |
| Business logic must be independent of frameworks | Hexagonal Architecture, Clean Architecture |
| Need strong internal boundaries but one deployable | Modular Monolith |
| Need independently deployable business capabilities | Microservices |
| Need extension ecosystem | Microkernel / Plugin Architecture |
| Need async reactions across modules | Event-Driven Architecture |
| Read and write models differ | CQRS, Materialized View |

## Domain and Data

| Problem | Candidate Patterns |
| --- | --- |
| Protect business invariants | Aggregate, Aggregate Root, Value Object |
| Express meaningful business occurrence | Domain Event |
| Keep persistence out of domain | Data Mapper, Repository, Unit of Work |
| Simple database-backed model | Active Record, Table Data Gateway |
| Integrate different domain languages | Bounded Context, Anti-Corruption Layer, Canonical Data Model |
| Avoid duplicate processing | Idempotent Receiver, Inbox, Deduplication |
| Atomically persist state and publish event | Transactional Outbox |
| Need full history and replay | Event Sourcing |

## Integration and Messaging

| Problem | Candidate Patterns |
| --- | --- |
| Async communication | Message Channel, Message, Message Endpoint |
| One event to many consumers | Publish-Subscribe Channel |
| One message to one worker | Point-to-Point Channel, Competing Consumers |
| Route by message content | Content-Based Router |
| Break large message into parts | Splitter |
| Combine related messages | Aggregator |
| Query many services and combine | Scatter-Gather, Gateway Aggregation |
| Transform payloads | Message Translator, Normalizer, Content Enricher |
| Handle poison messages | Dead Letter Channel, Message Store |
| Observe message flow | Wire Tap, Message History, Control Bus |

## Distributed Systems

| Problem | Candidate Patterns |
| --- | --- |
| Transient dependency failures | Retry with backoff, Timeout |
| Persistent dependency failures | Circuit Breaker |
| Isolate resource failure | Bulkhead |
| Smooth bursts | Queue-Based Load Leveling |
| Protect service from overuse | Rate Limiting, Throttling |
| Long-running distributed transaction | Saga, Process Manager |
| Gradual legacy replacement | Strangler Fig, Anti-Corruption Layer |
| Tailored APIs per client | Backends for Frontends |
| Shared edge concerns | API Gateway, Gateway Offloading |
| Client direct access to resource | Valet Key |

## Frontend

| Problem | Candidate Patterns |
| --- | --- |
| Predictable client state | Unidirectional Data Flow, Store |
| Explicit UI transitions | State Machine |
| Shared state among siblings | Lifted State |
| Remote data caching | Query Cache |
| Fast perceived response | Optimistic UI, Skeleton State |
| Isolate render failures | Error Boundary |
| Multi-step task | Wizard / Stepper |
| Power-user command access | Command Palette |

## Quality and Delivery

| Problem | Candidate Patterns |
| --- | --- |
| Preserve legacy behavior while refactoring | Characterization Test, Golden Master |
| Validate service compatibility | Contract Test |
| Generate rich test inputs | Property-Based Test |
| Measure test quality | Mutation Testing |
| Gradual production rollout | Canary Release, Feature Flag |
| Capture architectural rationale | ADR |

