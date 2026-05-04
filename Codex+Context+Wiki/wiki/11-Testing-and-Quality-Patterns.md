# Testing and Quality Patterns

Testing patterns protect design decisions by making behavior observable and change safer.

## Test Structure Patterns

| Pattern | Use When | Notes |
| --- | --- | --- |
| Arrange-Act-Assert | Tests need readable structure. | Keep each section obvious. |
| Given-When-Then | Behavior should be described in scenario language. | Useful for acceptance tests. |
| Test Data Builder | Test setup is verbose. | Default values should be realistic. |
| Object Mother | Shared test objects are needed. | Can become global fixture soup. |
| Fixture | Expensive setup is reused. | Avoid hidden coupling between tests. |

## Test Doubles

| Pattern | Use When | Notes |
| --- | --- | --- |
| Dummy | Argument required but not used. | Keep simple. |
| Stub | Provide canned responses. | Good for query dependencies. |
| Fake | Lightweight working implementation. | In-memory databases and clocks. |
| Mock | Verify interactions. | Avoid overspecifying implementation. |
| Spy | Record calls while preserving behavior. | Useful for side effects. |

## System Quality Patterns

| Pattern | Use When | Notes |
| --- | --- | --- |
| Contract Test | Service/API boundary must remain compatible. | Strong for microservices and libraries. |
| Characterization Test | Legacy behavior must be captured before refactor. | Documents current behavior, even if imperfect. |
| Golden Master | Complex output should remain stable. | Requires update discipline. |
| Property-Based Test | Many input combinations should satisfy invariants. | Excellent for parsers, transformations, calculations. |
| Mutation Testing | Test suite strength needs measurement. | Can be slow. |
| Smoke Test | Deployment needs quick confidence. | Shallow by design. |
| Canary Release | Production rollout should be gradual. | Requires metrics and rollback. |

