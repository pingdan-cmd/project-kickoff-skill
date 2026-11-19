# Harness Shell

> **Use when**: Stage ⑤ — build an Agent runtime shell, or judge "does switching business require a rewrite".
> **Triggers**: Harness, runtime, perceive-plan-act-observe, LLM adapter, Tools registry, only the right side changes when switching business.
> **Path**: `skills/superpowers/skills/project-kickoff-prep/references/harness-shell.md`
> **Boundary**: Only gives the generic shell structure; contains no tools or skills for any specific business.

    User task
      ↓
    ┌─ Agent Harness runtime (generic) ─────────────────────────────┐
    │ ① Perceive · assemble context (build prompt: task + memory + tool descriptions) │
    │ ② Plan (LLM decides: which tool / skill to call next?)       │
    │ ③ Act (call a Tool / execute a Skill)                         │
    │ ④ Observe (write result to Memory · judge whether done)       │
    │    ↺ back to ①; when done → structured result handed to UI   │
    └──────────────────────────────────────────────────────────────┘

    Left: LLM Engine adapter (swap the brain at any time)
          Memory (short-term: this conversation / task state; long-term: vector store semantic retrieval)
    Right: Tools registry + Skills library   ← business-specific, only this side changes when switching business
    Bottom: Tracing / Eval (traceable replay, token / latency, quality evaluation, failure replay)

## Reuse boundary

The shell (perceive → plan → act → observe) is built once and reused forever; **when switching business, only change the business-specific Tools and Skills on the right; the shell does not change**.
The same applies to scenarios like "Douyin expert / Zhihu expert": do not touch the runtime, only swap the right side.
