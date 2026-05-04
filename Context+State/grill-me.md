The **"Grill-Me" skill** (popularized by developers like Matt Pocock and within the Claude Code/MCP communities) is essentially a "Reverse Interview" technique. Instead of you giving a prompt and the AI immediately generating code, the AI becomes an aggressive, inquisitive project manager.

It is arguably the most critical "skill" for a project of your scale because it solves the **"Assumed Understanding" problem**, where an AI builds something based on a guess rather than a requirement.

---

### Why "Grill-Me" Fits Your Phase 1

You mentioned Phase 1 is **Project Overview and Requirements**. The Grill-Me skill is the engine that generates that overview.

| Feature          | Passive AI (Standard)                          | "Grill-Me" AI (The Skill)                           |
| :--------------- | :--------------------------------------------- | :-------------------------------------------------- |
| **Pace**         | Dumps 100 lines of code immediately.           | Asks **one** question at a time.                    |
| **Logic**        | Accepts vague instructions ("Make it fast").   | Challenges ambiguity ("Define 'fast' in ms").       |
| **Architecture** | Guesses a structure based on "best practices." | Explores your constraints (broker rules, hardware). |
| **Output**       | A first draft that might be 40% wrong.         | A validated **Requirements Handshake**.             |

---

### How it Integrates with Your `.context/` Folder

The "Grill-Me" session is the source of truth for your permanent context files. Once the "grilling" is over, you tell the AI to summarize the results into the files we just built:

1.  **Results of Grill** $\rightarrow$ `CURRENT_PHASE.md` (Objective and DoD)
2.  **Trade-offs decided** $\rightarrow$ `CONVENTIONS_CACHE.md` (Architectural decisions)
3.  **Forbidden paths** $\rightarrow$ `FAILED_ATTEMPTS.md` (Known "don'ts")

---

### The "Grill-Me" Prompt Template

You can trigger this mode by pasting the following into your chat. This is designed to be "relentless" until a shared understanding is reached.

> **Instruction: Initiate "Grill-Me" Mode**
>
> "I have a new feature/project idea. Do NOT write any code yet. Your goal is to interview me relentlessly until you have a 100% shared understanding of the requirements, architecture, and constraints.
>
> **Rules for this session:**
>
> 1. **One question at a time.** Do not overwhelm me with a list.
> 2. **Push back.** If my requirement is vague or contradicts our current tech stack, challenge me.
> 3. **Depth-first.** Pick one branch (e.g., Data Model) and exhaust it before moving to the next (e.g., UI).
> 4. **Recommend.** For every question, provide your 'best-practice' recommendation based on our `CONVENTIONS_CACHE.md`.
>
> When we are done, I will ask you to 'Finalize the Grill,' at which point you will update my `.context/` files."

---

### Why this works for a 60k file project

In a massive codebase, context drift is your biggest enemy. By using a "Grill-Me" session for every new feature:

- You prevent the AI from "hallucinating" how your 1-minute candle backfilling works.
- You ensure the AI remembers your specific Section 475(f) tax status or broker-specific fee structures before it writes a "Slippage Audit" module.
- It forces the AI to "think" about the dependency graph before it touches a single file in your directory structure.

Would you like me to "Grill" you on a specific feature you're planning right now, or should we save this for your next major development sprint?
