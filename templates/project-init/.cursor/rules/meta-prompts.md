---
description: Meta-Prompts development protocol — applies to all files in this project
globs: ["**/*"]
alwaysApply: true
---

# Development Protocol

This project uses the Meta-Prompts protocol for AI-assisted software development.

## Initialization check

Before taking any action, check for `.build/` in the project root.

**No `.build/`:** Read `[META_PROMPTS_PATH]/BOOTSTRAP.md`. Follow the initialization sequence completely. Do not write application code until the human approves the Phase 1 spec.

**`.build/` exists:** Read `.build/AGENT.md` → `.build/SPEC.md` → `.build/BUILD_LOG.md`. Resume from the last BUILD_LOG entry.

## Non-negotiable rules

- No code before Phase 1 spec is approved
- No hardcoded secrets anywhere — environment variable names only
- Every function needs unit tests: happy path, error path, boundary conditions
- Fail secure — missing auth = denied, not allowed
- Structured JSON logs with `trace_id` field in all services
- One phase at a time — verify and get approval before moving to the next

Meta-prompts: `[META_PROMPTS_PATH]/`
