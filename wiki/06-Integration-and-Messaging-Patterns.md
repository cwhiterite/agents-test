# Integration and Messaging Patterns

Integration patterns connect systems while managing format differences, delivery guarantees, routing, transformation, and monitoring.

## Integration Styles

| Style | Use When | Trade-Off |
| --- | --- | --- |
| File Transfer | Batch exchange is acceptable. | Simple but delayed and less interactive. |
| Shared Database | Multiple apps need the same data store. | Tight coupling through schema. |
| Remote Procedure Invocation | Caller needs synchronous behavior. | Temporal coupling and network failure. |
| Messaging | Systems should communicate asynchronously. | Requires idempotency, monitoring, and operational maturity. |

## Messaging Systems

| Pattern | Use When |
| --- | --- |
| Message Channel | Applications communicate through a logical pipe. |
| Message | Data, command, or event crosses a channel. |
| Pipes and Filters | Processing can be decomposed into independent stages. |
| Message Router | Messages must go to different paths. |
| Message Translator | Systems use different data models. |
| Message Endpoint | App connects to a messaging system cleanly. |

## Channel Patterns

| Pattern | Use When |
| --- | --- |
| Point-to-Point Channel | Exactly one consumer should process each message. |
| Publish-Subscribe Channel | Multiple consumers should receive each event. |
| Dead Letter Channel | Invalid or undeliverable messages need inspection. |
| Guaranteed Delivery | Messages must survive process or network failure. |
| Channel Adapter | External systems need to connect to messaging. |
| Messaging Bridge | Two messaging systems must interoperate. |
| Message Bus | A shared messaging backbone coordinates many apps. |

## Message Construction

| Pattern | Use When |
| --- | --- |
| Command Message | Receiver should perform an action. |
| Document Message | Receiver needs a data document. |
| Event Message | Receiver should know something happened. |
| Request-Reply | Sender needs a response. |
| Correlation Identifier | Replies must be matched to requests. |
| Message Expiration | Stale messages should not be processed. |
| Format Indicator | Receivers need to know payload format or version. |

## Routing Patterns

| Pattern | Use When |
| --- | --- |
| Content-Based Router | Route based on message content. |
| Message Filter | Drop messages that do not matter. |
| Dynamic Router | Routing rules change at runtime. |
| Recipient List | Send to computed list of recipients. |
| Splitter | Break one message into multiple messages. |
| Aggregator | Combine related messages into one result. |
| Resequencer | Restore intended order. |
| Scatter-Gather | Query multiple recipients and combine results. |
| Routing Slip | Message carries its processing itinerary. |
| Process Manager | A central component manages a long-running flow. |
| Message Broker | Intermediary routes and transforms among systems. |

## Transformation Patterns

| Pattern | Use When |
| --- | --- |
| Envelope Wrapper | Add metadata around payload. |
| Content Enricher | Add missing data from another source. |
| Content Filter | Remove unnecessary data. |
| Claim Check | Store large payload externally and pass a reference. |
| Normalizer | Convert multiple formats into a common model. |
| Canonical Data Model | Many systems need a shared integration model. |

## Endpoint and Operations Patterns

| Pattern | Use When |
| --- | --- |
| Polling Consumer | Receiver checks for messages on schedule. |
| Event-Driven Consumer | Receiver reacts when messages arrive. |
| Competing Consumers | Multiple workers share a queue for throughput. |
| Idempotent Receiver | Duplicate messages are possible. |
| Service Activator | Message invokes application service behavior. |
| Wire Tap | Copy messages for observation without changing flow. |
| Message History | Track where a message has been. |
| Message Store | Persist messages for audit, replay, or recovery. |
| Control Bus | Manage and monitor messaging infrastructure. |

