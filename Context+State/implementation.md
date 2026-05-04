To manage a codebase of this scale without losing the plot, these templates are designed to be "scannable" for both you and the AI. Placing these in a root `.context/` folder creates a dedicated "black box" for the AI’s operational memory.

---

### 1. `TASK_STATE.json`

**Purpose:** The machine-readable "short-term memory." This is the first file the AI should read to understand exactly what is happening _right now_.

```json
{
  "active_task": {
    "id": "TASK-001",
    "name": "Implement WebSocket Liquidity Filter",
    "status": "in-progress",
    "last_updated": "2026-05-03T23:20:00Z"
  },
  "subtasks": [
    { "description": "Initialize stream listener", "completed": true },
    {
      "description": "Apply ATR-based volatility threshold",
      "completed": false
    },
    { "description": "Log slippage audit metrics", "completed": false }
  ],
  "context_check": {
    "current_blockers": ["High latency on testnet feed"],
    "next_immediate_step": "Optimize buffer for 1-minute candle backfilling"
  },
  "git_status_snapshot": "branch: feature/liquidity-filter, uncommitted: 4 files"
}
```

---

### 2. `CURRENT_PHASE.md`

**Purpose:** The "North Star" for the mid-term goal. It prevents the AI from suggesting features that belong in a future phase.

```markdown
# Current Phase: [Phase Name, e.g., Live Trading Integration]

## 🎯 Objective

Transition from backtesting to live-streamed paper trading with sub-second execution logic.

## ✅ Definition of Done (DoD)

- [ ] 1-minute candles backfill correctly on startup.
- [ ] Multi-strategy weighting logic applied to live tickers.
- [ ] All trade signals logged to SQLite without blocking the main event loop.

## 🚧 Scope Boundaries

- **In Scope:** Live streaming, real-time liquidity scoring.
- **Out of Scope:** Mobile dashboard UI, multi-broker support (staying on current broker for now).
```

---

### 3. `CONVENTIONS_CACHE.md`

**Purpose:** A "living" document for patterns that haven't made it into the global standards yet. It prevents the AI from asking "How should I handle this?" twice.

```markdown
# Project Conventions Cache

## 🛠 Tech Stack Specifics

- **Runtime:** Node.js / TypeScript
- **State Management:** React Context + custom hooks for stream data.
- **Database:** SQLite (WAL mode enabled for concurrent reads).

## 📝 Emerging Patterns

- **Error Handling:** Use a `Result<T, E>` pattern for all trading logic to avoid uncaught exceptions during live streams.
- **Naming:** All utility functions for ATR or Volatility calculation must prefix with `calc_`.
- **Testing:** New hooks must include a "mock-stream" test case.
```

---

### 4. `FAILED_ATTEMPTS.md`

**Purpose:** The "Anti-Pattern" log. This is the most effective way to stop an AI from suggesting a "fix" that you already know doesn't work.

| Date       | Attempted Solution                      | Result/Failure Reason                      | Avoidance Rule                                                      |
| :--------- | :-------------------------------------- | :----------------------------------------- | :------------------------------------------------------------------ |
| 2026-04-28 | Native `setInterval` for ticker updates | Inconsistent timing due to event loop lag. | Never use `setInterval` for precision data; use `process.hrtime()`. |
| 2026-05-01 | Full-store re-renders on every tick     | UI froze during high volatility.           | Use memoized sub-components for live price updates.                 |

---

### Implementation Pro-Tip: The "Hydration" Command

To make these effective, add a "System Instruction" to your AI environment (like your `.clinerules`):

> "At the start of every session, read all files in `/.context/`. At the end of every task, update `TASK_STATE.json` and `FAILED_ATTEMPTS.md` if applicable. This is your primary mechanism for maintaining state across sessions."

This setup turns your context window into a structured database rather than a rambling conversation history. Do you want to try setting up an automated "Check-out" prompt for the AI to fill these out at the end of a session?
