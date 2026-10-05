---
name: missao
description: Mandatory 4-phase workflow (Research → Planning → Execution → Validation) for complex, multi-file missions. Invoked manually with /missao <mission description>.
disable-model-invocation: true
argument-hint: <mission description>
---

# Mission Workflow

Mission: $ARGUMENTS

Execute the phases in order. No phase may be skipped, and each one ends with its handoff before the next begins.

## Phase 0 — Research (Auditor)
- Delegate codebase discovery to the Explore subagent. Run several Explore agents in parallel only when the areas are independent.
- Identify reusable code, project conventions (local `CLAUDE.md`), dependencies, and the skills and MCP servers relevant to the mission. Note runtime or hardware constraints that affect the solution.
- **Handoff — Analysis Report:** relevant files, reusable logic, constraints, risks, open questions.

## Phase 1 — Planning (Architect)
- No functional code in this phase. Prefer plan mode; otherwise write the plan without editing files.
- For large designs, use the Plan subagent. Define data flow, state management, files to create or modify, and the validation strategy.
- Ask the user only for decisions that cannot be resolved from the code or sensible defaults.
- **Handoff — Technical Blueprint:** ordered steps, affected files, validation plan. Present it and wait for approval before Phase 2.

## Phase 2 — Execution (Developer)
- Implement in the main thread, strictly following the approved Blueprint. If the Blueprint proves wrong, stop and explain the deviation before continuing.
- Use skills and MCP tools when they fit the task; do not force them.
- **Handoff — Affected File List and Logic Summary.**

## Phase 3 — Validation (QA)
- Delegate to the `qa-validator` subagent, passing the Blueprint and the affected file list.
- For UI changes, also verify the result in the browser preview.
- **Circuit breaker:** if a failure persists after 2 consecutive correction attempts, abort the loop and request user intervention.
- **Handoff — Status Report (PT-BR):** result, what was validated and how, pending issues.
