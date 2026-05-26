---
description: This document defines the mandatory workflow for complex missions. All sub-agents must operate as a coordinated unit, leveraging the ecosystem of skills and MCPs, and adhering to the global standards defined in `~/.gemini/GEMINI.md`.
---

# Mandatory Mission Workflow

## Phase 0: Research (Auditor)
**Responsibility:** Audit the codebase and environment before architectural decisions.
- **Action:** Analyze `@Codebase` and existing `skills/` to identify reusable logic.
- **Audit:** Evaluate hardware constraints and external dependencies.
- **Handoff:** Generate an **Analysis Report**. No technical planning may begin without this completed audit.

## Phase 1: Planning (Architect)
**Responsibility:** Structure the high-level technical solution.
- **Action:** Review rules (local or global) to align the solution with project standards.
- **Integration:** Evaluate available MCP connections (**StitchMCP, github-mcp-server, gmp-code-assist, sequential-thinking**) to map data flows.
- **Handoff:** Generate a detailed **Technical Blueprint**. Coding is strictly prohibited in this phase.

## Phase 2: Execution (Developer)
**Responsibility:** Transform the Blueprint into functional, high-performance code.
- **Action:** Implement logic strictly following the Technical Blueprint.
- **Skill Integration:** Mandatory use of existing skills (**algorithmic-art, brand-guidelines, canvas-design, doc-coauthoring, docx, frontend-design, internal-comms, mcp-builder, pdf, pptx, skill-creator, slack-gif-creator, theme-factory, webapp-testing, web-artifacts-builder, xlsx**) for API handling and UI components.
- **Handoff:** Provide an **Affected File List and Logic Summary** describing implemented features and utilized MCPs.

## Phase 3: Validation (QA)
**Responsibility:** Ensure technical integrity, security, and functional compliance.
- **Diagnostics:** Use Terminal (Git Bash/pwsh) for environment diagnostics and Browser Preview (Port 9222) for UI validation.
- **Safety:** Verify no credentials or API keys (GitHub, Stitch, Maps) are exposed.
- **Circuit Breaker:** If a technical failure persists after **2 consecutive correction attempts**, abort the loop and request Orchestrator/Human intervention.
- **Handoff:** Generate a **Status Report**.

## Phase 4: Final Status (Localization)
**Responsibility:** Facilitate clear communication with the Orchestrator.
- **Action:** Translate the final **Status Report** and completion notification into **Brazilian Portuguese (PT-BR)**.
- **Requirement:** Ensure all technical accomplishments are clearly explained to the Human user in their native language.

## Communication & Security Protocol
- **File Access:** Respect the Non-Workspace File Access policy. Request explicit permission to modify external configurations.
- **Persistence:** Document critical architecture and database decisions in the **Knowledge** tab to ensure technical memory persists across mission cycles.
- **Runtime:** Identify the active shell (PowerShell vs. Git Bash) at mission start and adapt syntax immediately.