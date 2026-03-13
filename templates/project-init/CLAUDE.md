# Development Protocol

This project uses the **Meta-Prompts** protocol for AI-assisted software development.

## If the project is not yet initialized (no `.build/` directory)

Read the bootstrap protocol and follow its initialization sequence:

```
[META_PROMPTS_PATH]/BOOTSTRAP.md
```

The bootstrap file contains step-by-step instructions. Do not write code until the initialization sequence is complete and the human has approved the Phase 1 specification.

## If the project is already initialized (`.build/` directory exists)

Read the control documents in this order:

1. `.build/AGENT.md` — your directive, rules, and constraints
2. `.build/SPEC.md` — find the current active phase and its acceptance criteria
3. `.build/BUILD_LOG.md` — the last entry tells you exactly where the build left off

Then report to the human:
> "Resuming [project name]. Last session: [last log entry summary]. Current phase: [phase name]. Ready to continue with: [next action from log]."

Ask: "Is there anything that changed since the last session I should know about?"

Do not restart initialization. Pick up exactly where the last log entry left off.

## Meta-Prompts location

The Meta-Prompts protocol files are at: `[META_PROMPTS_PATH]/`

---

*Replace `[META_PROMPTS_PATH]` with the actual path to the meta-prompts submodule in this project (e.g., `meta_prompts`).*
