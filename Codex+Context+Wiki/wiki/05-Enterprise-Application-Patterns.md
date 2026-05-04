# Enterprise Application Patterns

Enterprise application patterns help organize business logic, persistence, transactions, web presentation, and application service boundaries.

## Domain Logic Patterns

| Pattern | Use When | Notes |
| --- | --- | --- |
| Transaction Script | Business logic is simple and maps closely to use cases. | Good for straightforward workflows; can become repetitive. |
| Domain Model | Domain behavior and rules are rich. | Keeps rules near data and invariants. |
| Table Module | Logic is organized around database tables or record sets. | Common in data-heavy enterprise apps. |
| Service Layer | Use cases need a stable application boundary. | Coordinates transactions, authorization, domain operations, and integrations. |

## Data Source Patterns

| Pattern | Use When | Notes |
| --- | --- | --- |
| Table Data Gateway | One object handles database operations for a table. | Simple and explicit. |
| Row Data Gateway | One object represents one row and its persistence operations. | Can mix persistence with data behavior. |
| Active Record | Domain object contains data and persistence methods. | Productive for simple domains; weak for complex domain rules. |
| Data Mapper | Domain objects are independent of persistence. | Strong separation; more mapping code. |

## Object-Relational Patterns

| Pattern | Use When | Notes |
| --- | --- | --- |
| Unit of Work | Track changes and commit them as one transaction. | Common in ORMs. |
| Identity Map | Ensure one in-memory object per database identity. | Prevents duplicate object inconsistencies. |
| Lazy Load | Load related data only when needed. | Beware N+1 queries. |
| Repository | Collection-like access to aggregates or domain objects. | Should express domain queries, not hide every database feature. |

## Web Presentation Patterns

| Pattern | Use When | Notes |
| --- | --- | --- |
| Model View Controller | Separate input, presentation, and model concerns. | Baseline web UI architecture. |
| Page Controller | One controller handles one page or route. | Simple route-based apps. |
| Front Controller | Central request handler dispatches to actions. | Common in frameworks. |
| Template View | Render pages through templates. | Server-rendered HTML. |
| Transform View | Transform structured data into output formats. | Useful for XML/JSON/document generation. |

## Session and Transaction Patterns

| Pattern | Use When | Notes |
| --- | --- | --- |
| Client Session State | Session state lives with client. | Scales well, security-sensitive. |
| Server Session State | Session state lives server-side. | Easier control, operational storage cost. |
| Database Session State | Session state persists in database. | Survives restarts, adds database load. |
| Optimistic Offline Lock | Conflicts are rare. | Detect conflict at commit. |
| Pessimistic Offline Lock | Conflicts are likely or costly. | Prevent conflict by locking earlier. |

