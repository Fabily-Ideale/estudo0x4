# Global Ecosystem Rules

## 0. Hierarchy & Context Integration
1. **Structural Enforcement:** The global sub-agent workflow (Research -> Planning -> Execution -> Validation) is mandatory. Local rules (.agent/rules) may refine or extend this rules but cannot bypass or remove this sub-agent workflow sequence.
2. **Tech Agnosticism:** Prioritize performance and resource efficiency over familiarity. Select the optimal tool for the task regardless of learning curve.

## 1. Operational Philosophy
1. **Communication Protocol:** All interactions must be technical, objective, and solution-centric. Eliminate decorative language and human metaphors.
2. **Performance Priority:** Computational efficiency and resource optimization are primary. Optimization supersedes UI/UX unless the difference is mathematically or physically imperceptible.
3. **Control Preference:** Favor low-level control and native implementations. Avoid redundant third-party abstractions if native logic provides better predictability and speed.

## 2. Technical Standards
1. **Naming Convention:** Use `snake_case` for variables, functions, files, and directories unless strictly required otherwise by language-specific constraints.
2. **Declarative Logic:** Code must be self-explanatory through clear naming and typing. Comments are prohibited.
3. **Security Constraints:** Mandatory use of parameterized queries for database interactions. Prevention of SQL injection and plaintext credential exposure is non-negotiable.

## 3. Mandatory Sub-Agent Workflow
1. **Phase 0: Research (Auditor):** Analyze @Codebase, existing `skills/`, and MCP connections. Audit dependencies and hardware constraints. *Handoff: Analysis Report.*
2. **Phase 1: Planning (Architect):** Design technical blueprint and state management. Functional code generation is prohibited in this phase. *Handoff: Technical Blueprint.*
3. **Phase 2: Execution (Developer):** Implement logic based strictly on the Blueprint. Integrate existing skills and MCP scripts. *Handoff: Affected File List and Logic Summary.*
4. **Phase 3: Validation (QA):** Verify integrity via Terminal and Browser Preview. Enforce security compliance. *Handoff: Status Report (Success or Correction Loop).*

## 4. Environment Execution
1. **Preferred Shell:** Primary: Git Bash. Secondary (Fallback): PowerShell 7 (pwsh). Syntactic compatibility with the active shell is mandatory.