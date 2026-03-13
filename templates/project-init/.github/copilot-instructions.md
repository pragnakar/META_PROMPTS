# GitHub Copilot Instructions

This project uses the **Meta-Prompts** protocol for AI-assisted software development.

## Before writing any code

Check whether `.build/` exists in the project root.

**No `.build/` directory:** This project has not been initialized. Read `meta_prompts/BOOTSTRAP.md` and follow the initialization sequence. Do not write application code until the sequence is complete and the human has approved the Phase 1 specification.

**`.build/` exists:** The project is initialized. Read:
- `.build/AGENT.md` — constraints and rules
- `.build/SPEC.md` — current phase and acceptance criteria
- `.build/BUILD_LOG.md` — resume from last log entry

## Core rules (always apply)

- No code before spec approval
- No hardcoded secrets — environment variables only
- Tests are required for every function (happy path, error path, boundary)
- Fail secure — authorization failures deny by default
- Structured JSON logging with `trace_id` in all services

Meta-prompts location: `meta_prompts/`
