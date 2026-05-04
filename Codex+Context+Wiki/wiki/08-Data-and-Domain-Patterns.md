# Data and Domain Patterns

Data and domain patterns protect business meaning, consistency boundaries, persistence, and query performance.

## Domain-Driven Design Patterns

| Pattern | Use When | Notes |
| --- | --- | --- |
| Entity | Object identity matters across time. | Equality is based on identity. |
| Value Object | Attributes matter, identity does not. | Make immutable when possible. |
| Aggregate | A consistency boundary protects invariants. | Keep aggregates small and transactional. |
| Aggregate Root | External references enter aggregate through one root. | Prevents bypassing invariants. |
| Domain Event | The domain should record that something meaningful happened. | Events are part of the ubiquitous language. |
| Domain Service | Behavior does not naturally belong to one entity/value object. | Avoid turning into procedural dumping ground. |
| Repository | Domain needs collection-like access to aggregates. | Do not expose arbitrary persistence details. |
| Factory | Aggregate creation is complex or invariant-heavy. | Keep creation rules explicit. |
| Specification | Business predicates need composition or reuse. | Beware unreadable predicate frameworks. |
| Bounded Context | A model is valid within a clear boundary. | Integration needs translation across contexts. |
| Anti-Corruption Layer | Protect one model from another model's assumptions. | Essential for legacy/external integrations. |

## Persistence and Query Patterns

| Pattern | Use When | Notes |
| --- | --- | --- |
| Data Mapper | Domain should be persistence-ignorant. | More mapping code. |
| Active Record | Domain is simple and close to database model. | Can become weak for complex rules. |
| Repository + Unit of Work | Aggregate changes should be coordinated transactionally. | Keep transaction boundary explicit. |
| Identity Map | Avoid duplicate in-memory instances of same record. | Often handled by ORM session. |
| Lazy Load | Related data is expensive and optional. | Watch for N+1 queries. |
| Eager Load | Related data is needed immediately. | Watch for overfetching. |
| Optimistic Lock | Conflicts are uncommon. | Good default for web apps. |
| Pessimistic Lock | Conflicts are likely or dangerous. | Can reduce throughput. |

## Data Architecture Patterns

| Pattern | Use When | Notes |
| --- | --- | --- |
| Database per Service | Service autonomy requires owned data. | Cross-service queries and transactions become harder. |
| Shared Database | Simplicity outweighs service autonomy. | Schema becomes integration contract. |
| Read Replica | Read load should move away from primary database. | Replication lag. |
| Materialized View | Query shape differs from write model. | Rebuild and freshness strategy needed. |
| Event Sourcing | Full history is valuable and state can be derived. | Schema evolution and replay cost. |
| Change Data Capture | Downstream systems need database changes. | Operational and ordering complexity. |
| Outbox | Persist state change and outbound event atomically. | Consumers must dedupe. |
| Inbox | Consumer tracks processed messages. | Storage cleanup needed. |

