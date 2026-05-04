For high-level AI project development, especially when managing complex codebases, your four categories provide a strong foundation. To make an AI truly effective—minimizing "hallucinations" and "context drift"—it helps to think of the context window in layers of **permanence** and **specificity**.

Here is an optimized breakdown of the information an AI should always have, building on your structure:

---

## 1. The Project "North Star" (Overview & Requirements)

This is the immutable core. Without this, the AI may suggest features or optimizations that look good in isolation but conflict with the project's ultimate purpose.

- **The "Why":** Business goals or the specific problem being solved.
- **High-Level Architecture:** Is it a microservices-based system, a monolith, or an agentic workflow?
- **Success Metrics:** What defines a "working" project at the 10,000-foot view?

## 2. The Contextual Map (Environment & Structure)

For large-scale projects, the AI must understand its surroundings to avoid suggesting redundant code or breaking dependencies.

- **Directory-Specific Context:** Using files like `AGENTS.md` or `.clinerules` to define what a specific folder does.
- **The Dependency Graph:** A high-level view of how major modules interact.
- **Active Tech Stack:** Specific versions of languages, frameworks, and critical libraries to prevent the use of deprecated syntax.

## 3. The Execution Phase (Current Task & Completion)

This is the "Active Memory." It prevents the AI from getting lost in a "refactoring loop."

- **The "Definition of Done":** Explicit unit tests, UI benchmarks, or functional requirements that must be met before moving to the next phase.
- **Step-by-Step Implementation Plan:** A checklist of the sub-tasks within the current phase.
- **Known Constraints:** Temporary technical debt or specific "blocked" paths it shouldn't try to go down.

## 4. The Rules of Engagement (Standards & Boundaries)

This acts as the AI's "personality" and quality control.

- **Coding Conventions:** Naming patterns (e.g., camelCase vs snake_case), file naming, and folder organization.
- **Security & Safety:** Strict boundaries regarding API key handling, data privacy, and forbidden libraries.
- **Logic Patterns:** Preferences for specific design patterns (e.g., "Always use functional components over classes").

---

### Critical Additions for Large Projects

While your four phases are excellent, adding these two elements can significantly reduce "context tax" and errors:

- **The "State of the Union":** A summary of the _very last_ thing that happened. If you are resuming a session, the AI needs to know if the last build passed or failed and what the specific error was.
- **Negative Context (The "Don't" List):** A log of what hasn't worked. This prevents the AI from suggesting the same failed solution multiple times when it hits a wall.

### Context Hierarchy Table

| Layer           | Content                                             | Persistence                  |
| :-------------- | :-------------------------------------------------- | :--------------------------- |
| **Global**      | Project Overview, Core Stack, High-level Goals      | Permanent                    |
| **Structural**  | Directory Roles, Module Dependencies, Linting Rules | Semi-Permanent               |
| **Operational** | Current Phase, Active Task, Recent Errors           | Transient (Rotates per task) |

Does your current development environment allow you to "pin" these different layers, or are you looking for a way to manage them manually within the chat?
