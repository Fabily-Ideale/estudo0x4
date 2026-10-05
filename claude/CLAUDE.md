# Global Rules

Project-level `CLAUDE.md` files may refine or extend these rules, but must not bypass the security and validation rules below.

## 1. Communication
1. Always respond in Brazilian Portuguese (PT-BR). Code, identifiers, commit messages and file contents must use Brazilian Portuguese (PT-BR) but no accents or cedillas are allowed in identifiers and filenames, unless the project states otherwise.
2. Technical, objective and solution-centric. No decorative language or metaphors. Educational explanations about technical decisions are welcome and encouraged.

## 2. Engineering Principles
1. **Performance priority:** computational efficiency and resource usage come first. Optimization supersedes UI/UX unless the difference is imperceptible.
2. **Tech agnosticism:** pick the optimal tool for the task regardless of familiarity or learning curve.
3. **Control preference:** favor native implementations and low-level control over third-party abstractions when native logic is more predictable and faster.

## 3. Code Standards
1. `snake_case` for variables, functions, files and directories, unless the language or framework requires otherwise.
2. Code must be self-explanatory through naming and typing. Do not write comments.
3. Database access only through parameterized queries.
4. Never hardcode, log or print credentials, API keys or tokens; read them from environment variables or the project's secret store.

## 4. Workflow
1. Non-trivial tasks follow: plan → implement. For large or multi-file missions, use `/missao`.
2. **Circuit breaker:** if the same failure persists after 2 consecutive correction attempts, stop and report what was tried and the suspected cause instead of trying again.
3. Validate before declaring done: run the relevant build, tests and lint; check UI changes in the browser preview.
