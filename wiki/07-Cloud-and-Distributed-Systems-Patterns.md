# Cloud and Distributed Systems Patterns

Distributed systems patterns handle latency, partial failure, scaling, isolation, data partitioning, and operational control.

## Reliability and Failure Handling

| Pattern | Use When | Key Risk |
| --- | --- | --- |
| Retry | Failures are transient. | Retrying non-idempotent operations can duplicate work. |
| Circuit Breaker | Dependency failures may persist. | Thresholds and recovery behavior need tuning. |
| Timeout | Calls must not wait forever. | Too short creates false failures. |
| Bulkhead | One failure domain should not exhaust all resources. | Capacity fragmentation. |
| Queue-Based Load Leveling | Bursts should be smoothed. | Queue latency and backlog management. |
| Health Endpoint Monitoring | Operators need synthetic health checks. | Shallow health checks can lie. |
| Compensating Transaction | A multi-step operation needs undo behavior. | Undo may be business-specific and incomplete. |

## Scale and Performance

| Pattern | Use When | Key Risk |
| --- | --- | --- |
| Cache-Aside | Expensive reads can be cached on demand. | Stale data and invalidation. |
| Materialized View | Queries need precomputed projections. | Projection lag. |
| Sharding | Data exceeds a single database or ownership boundary. | Cross-shard queries and rebalancing. |
| Priority Queue | Some work should run before other work. | Starvation of low-priority work. |
| Rate Limiting | Protect services from overuse. | Poor client experience if limits are unclear. |
| Throttling | Control consumption under load. | Requires caller backoff behavior. |
| Static Content Hosting | Static assets can be served directly. | Cache invalidation and deployment coordination. |

## Service Boundary and API Patterns

| Pattern | Use When | Key Risk |
| --- | --- | --- |
| API Gateway | Clients need one entry point to many services. | Gateway becomes business logic sink. |
| Backends for Frontends | Different clients need tailored APIs. | Duplication across BFFs. |
| Gateway Aggregation | Client would otherwise make many calls. | Gateway latency and partial failures. |
| Gateway Routing | One endpoint routes to multiple services. | Route complexity. |
| Gateway Offloading | Cross-cutting concerns belong at the edge. | Hidden behavior outside app code. |
| Ambassador | Helper proxy handles connectivity concerns. | Operational sidecar complexity. |
| Sidecar | Separate process provides supporting capability. | Deployment and debugging complexity. |
| Anti-Corruption Layer | New model must be protected from legacy or external model. | Translation layer can become large. |

## Data Consistency and Workflow

| Pattern | Use When | Key Risk |
| --- | --- | --- |
| Saga | Business transaction spans services. | Compensation, observability, and ordering. |
| Choreography | Services can react through events without central coordinator. | Emergent flows can be hard to understand. |
| Orchestration / Process Manager | Long-running workflow needs central control. | Coordinator becomes availability bottleneck. |
| Event Sourcing | State changes must be recorded as an append-only event log. | Event schema evolution and replay complexity. |
| CQRS | Commands and queries need separate models. | Synchronization and conceptual overhead. |
| Transactional Outbox | State change and event publication must be atomic. | Polling/relay operation and deduplication. |

## Modernization and Deployment

| Pattern | Use When | Key Risk |
| --- | --- | --- |
| Strangler Fig | Replace legacy functionality incrementally. | Routing and data coexistence complexity. |
| Deployment Stamps | Deploy repeated independent units by tenant or region. | Operational duplication. |
| Geode | Serve requests from geographically distributed nodes. | Data consistency and conflict resolution. |
| External Configuration Store | Config should be separate from deployments. | Misconfiguration blast radius. |
| Federated Identity | Identity should be delegated to trusted provider. | Token, claims, and lifecycle complexity. |
| Valet Key | Clients need restricted direct access to a resource. | Token scope and expiration mistakes. |

