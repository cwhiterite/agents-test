# UI and Frontend Patterns

Frontend patterns organize rendering, state, user interaction, accessibility, and integration with backend APIs.

## Presentation Architecture

| Pattern | Use When | Notes |
| --- | --- | --- |
| MVC | Input, view, and model need separation. | Server or client applications. |
| MVP | Presenter mediates view behavior for testability. | Common in UI frameworks with passive views. |
| MVVM | View binds to a view model. | Strong fit for reactive binding frameworks. |
| Container/Presentational Components | Separate data/state from visual rendering. | Still useful, but modern hooks/composables may reduce need. |
| Unidirectional Data Flow | State updates should be predictable and traceable. | Flux, Redux, Elm-style designs. |
| Component Composition | UI features are assembled from small components. | Prefer composition over deep inheritance. |

## State Patterns

| Pattern | Use When | Notes |
| --- | --- | --- |
| Local Component State | State affects only one small UI area. | Default for simple UI. |
| Lifted State | Sibling components need shared state. | Avoid lifting everything to the root. |
| Store | Many parts of the app share state or need time-travel/debugging. | Normalize and scope stores carefully. |
| State Machine | UI has explicit states and transitions. | Excellent for forms, onboarding, checkout, async flows. |
| Optimistic UI | User action should feel immediate. | Requires rollback and conflict handling. |
| Derived State | State can be computed from other state. | Avoid storing duplicated derived values. |

## Data Fetching Patterns

| Pattern | Use When | Notes |
| --- | --- | --- |
| Query Cache | Remote reads need caching, refetching, and invalidation. | Use proven libraries when available. |
| Pagination | Large result sets need page navigation. | Stable sorting matters. |
| Infinite Scroll | Feed-like browsing matters more than precise navigation. | Accessibility and position restoration. |
| Lazy Loading | Data or code can load on demand. | Avoid layout shift. |
| Skeleton State | Loading should preserve layout and perceived speed. | Keep skeletons faithful to final shape. |
| Error Boundary | UI should isolate render failures. | Provide recovery actions. |

## Interaction and Accessibility Patterns

| Pattern | Use When | Notes |
| --- | --- | --- |
| Form Validation | User input needs fast feedback and server enforcement. | Client validation complements server validation. |
| Wizard / Stepper | A complex task has ordered steps. | Allow review and recovery. |
| Command Palette | Power users need fast navigation and actions. | Requires good search and keyboard support. |
| Modal Dialog | User must resolve focused task before returning. | Avoid using modals for ordinary navigation. |
| Toast / Notification | Non-blocking feedback is useful. | Do not hide critical errors in transient UI. |
| Progressive Disclosure | Advanced controls should not overwhelm primary workflow. | Keep discoverability. |

