use_skill("brainstorming")

Skill When to Use
brainstorming Before any creative work
writing-plans After brainstorming, to create implementation plans
test-driven-development Before writing implementation code
systematic-debugging When encountering bugs or test failures
subagent-driven-development For executing plans with independent tasks
verification-before-completion Before claiming work is complete
receiving-code-review When receiving code review feedback
finishing-a-development-branch When implementation is complete
requesting-code-review Before merging to verify work
dispatching-parallel-agents For 2+ independent tasks
executing-plans To execute a written implementation plan
using-git-worktrees For isolated feature work
writing-skills For creating/editing skills
using-superpowers At the start of any conversation

Yes, the **Superpowers** ecosystem (developed by Jesse Vincent/obra) is essentially the professional-grade, automated version of the manual context strategy we just built.

It isn't just a collection of prompts; it is a **disciplined operational layer** that forces an LLM to behave like a senior engineer rather than a "vibe coder."

---

## ⚡ What is Superpowers?

At its core, Superpowers is a library of **structured skills** (currently 14+) that are injected into an AI’s context. Each skill is a codified process (a `SKILL.md` file) that the AI must follow.

### The Superpowers Workflow (The "Happy Path")

1.  **Brainstorming:** This is the "Grill-Me" phase. The AI is forbidden from writing code until it has interviewed you and generated a shared understanding.
2.  **Spec Writing:** It turns the brainstorm into a rigorous technical specification.
3.  **Implementation Planning:** It breaks the spec into tiny, 2–5 minute tasks with exact file paths.
4.  **Sub-Agent Execution:** For each task, it spawns a "fresh" sub-agent. This is critical for your 60k-file project because the sub-agent only sees the specific files needed for that one task, effectively **bypassing context drift and the "RAM tax."**
5.  **Review & TDD:** It enforces a Red-Green-Refactor cycle. If the tests don't pass, the agent is "blocked" from merging the code.

---

## 🛠 The MCP Server Integration

The reason you're hearing about the **MCP (Model Context Protocol) server** is that it allows you to plug these skills into almost any modern AI IDE (Cursor, Windsurf, Roo Code, etc.).

By running the `superpowers-mcp` server, your AI assistant gains a set of "tools" like:

- `use_skill("brainstorming")`: Triggers the intensive Q&A mode.
- `use_skill("test-driven-development")`: Forces the AI into a strict TDD loop.
- `compose_workflow`: Chains multiple skills together for complex features.

---

## 🧠 Why It Works (The Psychology)

The framework is famous for using **psychological persuasion principles** (based on Robert Cialdini’s work) to ensure "compliance" rather than just "understanding."

- **Commitment:** The AI must announce which skill it is using before it starts.
- **Authority:** The skills are framed as mandatory protocols, not suggestions.
- **Consistency:** By using the same `SKILL.md` every time, the AI produces predictable, high-quality code regardless of how complex the project gets.

---

## ⚖️ How it compares to our `.context/` Strategy

Our manual strategy is **"Superpowers Lite."** \* Your `TASK_STATE.json` is a manual version of their **Implementation Plan**.

- Your `FAILED_ATTEMPTS.md` is a manual version of their **Systematic Debugging** skill.

**The Verdict:** If you are comfortable managing the files yourself, the manual way gives you 100% control and zero "token bloat." However, if you want the AI to **self-police** and manage its own sub-agents to handle your 60,000 files, installing the `superpowers-mcp` server is a massive productivity multiplier.

### Recommendation for Your Setup

Since you are using **Roo Code**, you can actually add the Superpowers MCP server directly to your `petals` or `mcp_config.json`. This would allow Roo Code to call `list_skills` and `use_skill` natively.

Would you like the configuration snippet to add a Superpowers MCP server to your environment?
