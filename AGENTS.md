# AGENTS.md

This repository is the **Meta-Prompt Ecosystem** — a structured protocol system for AI-assisted software development.

## For AI Agents

**Before you do anything else:** Read `BOOTSTRAP.md` and follow the initialization sequence it contains.

`BOOTSTRAP.md` is the imperative entry point. It contains:
- A step-by-step initialization protocol (read it fully before acting)
- A decision table for selecting which companion meta-prompts to load
- Templates for the three control documents: `AGENT.md`, `SPEC.md`, `BUILD_LOG.md`
- The phase execution and verification protocol
- Instructions for resuming an already-initialized project

Do not write code, create files, or make architectural decisions until the `BOOTSTRAP.md` initialization sequence is complete and the human has approved the Phase 1 specification.

## Repository Structure

```
Meta_Prompts/
├── BOOTSTRAP.md                         ← Start here — imperative initialization protocol
├── AGENTS.md                            ← This file — cross-agent entry point
├── README.md                            ← Human-readable overview
├── templates/                           ← Standalone control document templates
│   ├── AGENT.md
│   ├── SPEC.md
│   ├── BUILD_LOG.md
│   └── project-init/                    ← Copy to parent project root when used as submodule
│       ├── CLAUDE.md
│       ├── AGENTS.md
│       ├── .windsurfrules
│       ├── .github/
│       │   └── copilot-instructions.md
│       └── .cursor/
│           └── rules/
│               └── meta-prompts.md
├── LLM_NATIVE_SOFTWARE_ENGINEERING/     ← Parent meta-prompt
├── Deployment_Engineering/              ← Companion: infrastructure
├── DevOps/                              ← Companion: operations
├── Database/                            ← Companion: data layer
├── UI-UX/                               ← Companion: interface design
├── Security_Engineering/                ← Companion: security
├── MLOps/                               ← Companion: ML operations
├── API_Design/                          ← Companion: API contracts
├── Testing_Strategy/                    ← Companion: test strategy
├── Documentation/                       ← Companion: documentation
└── Scrum/                               ← Companion: agile delivery
```

## Using This Repo as a Submodule

When this repository is added as a submodule to a parent project, copy the files from `templates/project-init/` to the parent project root. Each file contains instructions for its respective AI tool to discover and follow the bootstrap protocol.

Adjust `[META_PROMPTS_PATH]` in those files to match the actual submodule path (e.g., `meta_prompts/`).
