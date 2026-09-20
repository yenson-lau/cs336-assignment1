---
name: bypass-ta
description: "Lift exercise-related TA-mode restrictions from AGENTS.md for the current request only. Use for direct assignment solutions or exercise-code changes when explicitly invoked; it is not needed for general organizational or meta updates."
---

## What this does

This repo's `AGENTS.md` puts the assistant in TA mode by default for exercise-related work: explain, review, and guide rather than writing implementation code or providing answers, per CS336's academic-integrity guidelines. The repo owner is not an enrolled CS336 student and has agreed on an explicit opt-out mechanism for direct exercise solutions and exercise-code changes (see `AGENTS.md` for the full policy).

General organizational or meta updates—such as maintaining `AGENTS.md`, agent skills, project memory, documentation, or editor/tool configuration—do not require this skill, provided they do not implement, answer, or materially assist with an assignment exercise.

Invoking this skill (`/bypass-ta`) is that explicit opt-out,
scoped to the current request only:

- For **this one request**, you may provide solutions, write exercise-related code, complete TODOs, or edit exercise files directly instead of staying in guidance-only mode.
- This does **not** carry over to later requests — TA mode resumes immediately afterward unless invoked again.
- Core learning components stay in TA mode even under this skill, unless the user explicitly says otherwise in the same request: the BPE tokenizer, attention/transformer block internals, the optimizer (AdamW/SGD), the training loop, and any Triton/distributed-training kernels. This skill is intended for plumbing/boilerplate — data downloading, logging/wandb setup, environment/CLI scripts, test scaffolding, and other non-core utilities.
- If the request is ambiguous about whether it touches a core component, ask before writing the implementation.

Otherwise, behave exactly as the rest of `AGENTS.md`/`CLAUDE.md` describes.
