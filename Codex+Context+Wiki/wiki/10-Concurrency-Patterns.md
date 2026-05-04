# Concurrency Patterns

Concurrency patterns coordinate work that runs at the same time or overlaps in time. They are often language/runtime-specific, but the forces are stable: shared state, ordering, throughput, isolation, fairness, and cancellation.

## Coordination Patterns

| Pattern | Use When | Risks |
| --- | --- | --- |
| Producer-Consumer | Producers and workers should be decoupled by a queue. | Backpressure and queue growth. |
| Worker Pool / Thread Pool | Many similar tasks need bounded concurrency. | Starvation and blocking work in shared pools. |
| Future / Promise | A result will be available later. | Cancellation and error propagation. |
| Async/Await | Asynchronous operations should read like sequential code. | Hidden concurrency and unhandled rejections. |
| Reactor / Event Loop | Many I/O events should be multiplexed on few threads. | Blocking the loop harms all work. |
| Active Object | Method invocation is decoupled from execution. | Queue visibility and lifecycle. |
| Monitor Object | Object protects its state with synchronized access. | Deadlocks and contention. |

## Safety Patterns

| Pattern | Use When | Risks |
| --- | --- | --- |
| Immutable Object | Shared data should not change after creation. | Copy cost for large structures. |
| Copy-on-Write | Reads dominate writes and snapshots are useful. | Write cost. |
| Read-Write Lock | Many readers, few writers. | Writer starvation. |
| Semaphore | Limit access to finite resource. | Leaks if permits are not released. |
| Mutex | Protect critical section. | Deadlock, priority inversion. |
| Actor | State is isolated behind message handling. | Mailbox backlog and message ordering. |
| Backpressure | Producers must slow down when consumers cannot keep up. | Requires end-to-end propagation. |

## Design Questions

- What state is shared?
- Who owns mutation?
- What ordering is required?
- What happens on cancellation?
- What happens when work is slower than arrival rate?
- How are errors reported and retried?
- How is concurrency bounded?

