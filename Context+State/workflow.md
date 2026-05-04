For a project with a high file count and complex logic, a single global `AGENTS.md` file will eventually become a bottleneck. As the file grows, the AI may begin to "skim" or prioritize the beginning and end of the document, losing the middle—a phenomenon known as context thinning.

To truly "pin" layers effectively, you need a **Hierarchical Context Architecture**. This ensures the AI only loads what is mechanically necessary for the current operation.

### 1. Is a global AGENTS.md enough?

No. For large-scale development, a single file is too "noisy." Instead, use a **Global-to-Local** inheritance model:

- **Global (`/.clinerules` or `/PROJECT_ROOT.md`):** Contains your "North Star" and "Rules of Engagement." This defines _how_ the AI should write code and the overall architecture.
- **Directory-Specific (`/src/components/AGENTS.md`):** Contains the "Contextual Map." It explains what the files in that specific folder do, preventing the AI from having to read every file to understand the module's intent.

---

### 2. Creating an Updateable "Working" Directory

To track the "Operational" layer (current phase and state), you can implement a dedicated `.context/` or `active_task/` directory. This acts as the AI's "short-term memory."

#### Recommended Structure:

Create a folder at the root called `.context/` and include these three files:

1.  **`CURRENT_PHASE.md`**: Tracks the macro-goal (e.g., "Phase 3: Implementing WebSocket Streams").
2.  **`TASK_STATE.json`**: A machine-readable file that the AI updates after every successful execution. It should include the last completed sub-task and any persistent errors.
3.  **`CONVENTIONS_CACHE.md`**: A "living" document for patterns discovered during development that aren't yet in the global rules.

---

### 3. The "Context Sync" Ritual

To keep the "Working" directory from becoming stale, you can enforce a rule in your global instructions (Stage 4) that requires the AI to update the state.

**Add this to your Global Rules:**

> "At the end of every successful task or session, you MUST update `/.context/TASK_STATE.json` with a summary of changes, the current build status, and the next immediate step. If a solution failed, log it in `/.context/FAILED_ATTEMPTS.md` to avoid repetition."

### Hierarchy of Contextual Pins

| Layer                        | File Location               | Update Frequency          |
| :--------------------------- | :-------------------------- | :------------------------ |
| **I. Global (Rules)**        | `/.clinerules`              | Rare (Monthly)            |
| **II. Structural (Map)**     | `**/AGENTS.md`              | Occasional (New Features) |
| **III. Operational (State)** | `/.context/TASK_STATE.json` | Constant (Every Task)     |

### Why this works

By breaking the context into these files, you can "pin" the Global rules permanently, but only "pin" the relevant Directory Map when working in that folder. The "Working" directory files are then read at the start of every session to "hydrate" the AI's memory of where it left off.

Would you prefer a manual template for that `TASK_STATE.json`, or would you like to see a script that could automate the summarization of your recent work into that file?
