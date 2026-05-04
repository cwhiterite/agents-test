# Security and API Patterns

Security and API patterns are design tools for trust boundaries, authorization, identity, data exposure, compatibility, and abuse resistance.

## Identity and Access

| Pattern | Use When | Watch For |
| --- | --- | --- |
| Federated Identity | Authentication should be delegated to an identity provider. | Claim mapping, token lifetime, logout, provider outage. |
| Role-Based Access Control | Permissions map cleanly to job roles. | Role explosion and overbroad roles. |
| Attribute-Based Access Control | Access depends on user, resource, action, and context attributes. | Policy complexity and test coverage. |
| Policy Decision Point / Policy Enforcement Point | Authorization should be centralized but enforced near resources. | Network dependency and fail-open mistakes. |
| Least Privilege | Components should receive only needed permissions. | Operational friction if permissions are too narrow or undocumented. |
| Valet Key / Pre-Signed URL | Client needs limited direct access to storage/resource. | Scope, expiry, revocation, and leakage. |

## Boundary Protection

| Pattern | Use When | Watch For |
| --- | --- | --- |
| API Gateway | Public clients need one controlled entry point. | Gateway accumulating business logic. |
| Backend for Frontend | Client types need different API shapes. | Duplication and inconsistent authorization. |
| Anti-Corruption Layer | External models should not leak into internal domain. | Translation drift and partial mappings. |
| Input Validation | Untrusted input crosses a boundary. | Validation split between UI and server; server must enforce. |
| Output Encoding | Data is rendered into HTML, SQL, shell, URLs, or logs. | Context-specific encoding mistakes. |
| Rate Limiting | Protect APIs from abusive or accidental overuse. | Fairness, tenant isolation, and client backoff. |
| Quarantine | External files/packages/data must be checked before use. | Delayed processing and exception workflow. |

## Secrets and Configuration

| Pattern | Use When | Watch For |
| --- | --- | --- |
| External Configuration Store | Runtime config should be separate from deployment. | Unauthorized config changes and unclear ownership. |
| Secret Store | Credentials and keys must not live in source or plain env files. | Rotation, audit, and local development ergonomics. |
| Key Rotation | Keys or credentials may be compromised or expire. | Dual-read/dual-write rollout windows. |
| Envelope Encryption | Data keys encrypt data and master keys protect data keys. | Key hierarchy complexity. |

## API Evolution

| Pattern | Use When | Watch For |
| --- | --- | --- |
| Versioned API | Breaking changes must coexist. | Too many active versions. |
| Consumer-Driven Contract | Providers must preserve consumer expectations. | Contract ownership and stale consumers. |
| Tolerant Reader | Consumers should ignore unknown fields. | Silent data loss if semantics change. |
| Pagination | Result sets can grow large. | Stable ordering and cursor security. |
| Idempotency Key | Clients may retry create/update operations. | Storage, expiry, and collision behavior. |
| Problem Details | Error responses need machine-readable consistency. | Leaking sensitive internals. |

## Security Review Prompt

```text
Review this design for trust boundaries, authentication, authorization, data exposure, abuse resistance, secrets, and API compatibility. Identify the smallest changes needed to make the design safe enough for the stated risk level.
```

