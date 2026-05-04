Since you’re ready to roll with those templates, here is the final piece of the puzzle: **The "Check-Out" Prompt.**

Think of this as an "End of Shift" report. By giving the AI this specific instruction when you're done for the day, you ensure that the next time you open the project, it knows exactly where the hammers were dropped.

---

### The "Session Sync" Instruction

Paste this into your **Global Rules** or `.clinerules` file so the AI knows its responsibility:

> **Session Maintenance Protocol:**
> At the end of every task or when I say "Session Wrap-up," you must:
>
> 1.  Update `/.context/TASK_STATE.json` with the current progress and next steps.
> 2.  Log any failed logic or architectural dead-ends in `/.context/FAILED_ATTEMPTS.md`.
> 3.  If a new design pattern emerged, document it in `/.context/CONVENTIONS_CACHE.md`.
> 4.  Summarize the "State of the Build" (e.g., "Build passing, but WebSocket latency is still >100ms").

---

### Example "Wrap-up" Command

When you are ready to stop, you can just tell the AI:

> "We're done for now. Run the Session Sync and update the `.context` files."

This forces the AI to reflect on what it actually accomplished versus what it _thought_ it was doing, which is the best way to catch logic errors early.

### Quick Implementation Checklist:

- [ ] Create the `/.context/` folder in your root directory.
- [ ] Drop those four templates in as empty (or populated) files.
- [ ] Update your global AI instructions with the **Session Maintenance Protocol**.

This setup effectively turns your AI into a senior developer who keeps a meticulous lab notebook.

Are you planning to have the AI manage these file updates automatically through its tool-calling (file writing) abilities, or do you want to review the summaries before they are saved?
