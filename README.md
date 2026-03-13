# Meta-Prompts

## A Protocol System for AI-Assisted Software Development

Meta-prompts are structured protocol documents that initialize AI-assisted development environments before task execution begins. Instead of starting with ad-hoc prompts, a meta-prompt establishes workflow structure, behavioral constraints, verification discipline, and quality standards — creating a reliable, repeatable foundation for building software with AI agents.

This repository is the index and entry point for the Meta-Prompt Ecosystem.

---

## The Core Idea

LLMs are strong implementers but unreliable architects. They produce locally correct code that violates global design. The solution is explicit coordination protocols — documents that define culture, contracts, and memory for AI-assisted development.

Software engineering with AI is becoming a **protocol problem**, not a coding problem.

---

## The Ecosystem

Each meta-prompt is an independent, evolving repository covering a distinct domain of the software lifecycle. They work together as a composable system — the parent meta-prompt invokes companions as project needs arise.

```
┌───────────────────────────────────────────────────────────────────────┐
│  LLM-Native Software Engineering                                      │
│  (Architecture, development methodology,                              │
│   verification discipline, build protocols)                           │
│                                                                        │
│  Invokes companion meta-prompts as needed:                            │
└──┬──────┬──────┬──────┬──────┬──────┬──────┬──────┬──────┬──────┬────┘
   │      │      │      │      │      │      │      │      │      │
   ▼      ▼      ▼      ▼      ▼      ▼      ▼      ▼      ▼      ▼
┌──────┐┌──────┐┌──────┐┌─────┐┌──────┐┌─────┐┌─────┐┌─────┐┌─────┐┌─────┐
│Deploy││DevOps││  DB  ││UI/UX││ Sec  ││MLOps││ API ││ Test││ Doc ││Scrum│
│ Eng  ││      ││      ││     ││ Eng  ││     ││Design││Strat││     ││     │
└──────┘└──────┘└──────┘└─────┘└──────┘└─────┘└─────┘└─────┘└─────┘└─────┘
```

| Meta-Prompt | Purpose | Repository |
|---|---|---|
| **LLM-Native Software Engineering** | Architecture, phased development, verification protocols, build-state tracking, Agent Development Runtime | [GitHub](https://github.com/pragnakar/LLM_NATIVE_SOFTWARE_ENGINEERING) |
| **Deployment Engineering** | Docker environments, Kubernetes, CI/CD pipelines, infrastructure as code, secrets management | [GitHub](https://github.com/pragnakar/Deployment_Engineering) |
| **DevOps** | Runtime operations, monitoring, alerting, incident response, reliability engineering | [GitHub](https://github.com/pragnakar/DevOps) |
| **Database** | Technology selection, schema design, indexing, query optimization, backup and recovery, data security | [GitHub](https://github.com/pragnakar/Database) |
| **UI/UX** | User-centered design, information architecture, accessibility, responsive design, design systems | [GitHub](https://github.com/pragnakar/UI-UX) |
| **Security Engineering** | Threat modeling, secure coding, input validation, cryptography, dependency security, secrets management | [GitHub](https://github.com/pragnakar/Security_Engineering) |
| **MLOps** | Experiment tracking, data versioning, training pipelines, model registry, drift monitoring, ML governance | [GitHub](https://github.com/pragnakar/MLOps) |
| **API Design** | Resource modeling, versioning, error handling, pagination, rate limiting, OpenAPI specifications | [GitHub](https://github.com/pragnakar/API_Design) |
| **Testing Strategy** | Test architecture, coverage strategy, performance testing, contract testing, AI-specific verification | [GitHub](https://github.com/pragnakar/Testing-Strategy) |
| **Documentation** | Technical writing, ADRs, API docs, architecture docs, runbooks, documentation-as-code | [GitHub](https://github.com/pragnakar/Documentation) |
| **Scrum** | Agile planning, sprint cycle management, ceremonies, and agile accountability | [GitHub](https://github.com/pragnakar/Scrum) |

---

## How It Works

### For a New Project

1. Start with **LLM-Native Software Engineering** — it defines the development methodology: how to write specifications, structure phases, verify builds, and track state across sessions.

2. When your project needs infrastructure, invoke **Deployment Engineering** to establish containerized environments, CI/CD pipelines, and infrastructure as code.

3. When your project needs a data layer, invoke **Database** to guide technology selection, schema design, and data management practices.

4. When your project has a user interface, invoke **UI/UX** to establish design principles, accessibility standards, and interaction patterns.

5. When your project approaches production, invoke **DevOps** to establish monitoring, alerting, incident response, and reliability practices.

6. When security is a requirement (it always is), invoke **Security Engineering** to define threat models, secure coding patterns, and vulnerability management.

7. When your project includes machine learning, invoke **MLOps** to establish reproducible training pipelines, model registry, drift monitoring, and serving infrastructure.

8. When designing APIs, invoke **API Design** to ensure consistent resource modeling, versioning, error handling, and documentation.

9. When defining test strategy, invoke **Testing Strategy** to establish the test pyramid, coverage targets, performance testing, and CI pipeline configuration.

10. When documentation is a deliverable, invoke **Documentation** to define documentation architecture, ADRs, and documentation-as-code pipelines.

11. When your project uses iterative delivery, invoke **Scrum** to establish sprint cycles, backlog management, ceremonies, velocity tracking, and Definitions of Done.

### For an AI Coding Agent

Paste the relevant meta-prompt into your agent's context before beginning work. The meta-prompt initializes the environment — establishing rules, constraints, and verification standards — so that subsequent task prompts execute within a structured, disciplined framework.

```
meta-prompt (environment initialization)
     ↓
task prompt (what to build)
     ↓
AI execution within that structured environment
```

The meta-prompt concept is platform-agnostic. It works with Claude Code, Cursor, GitHub Copilot, Windsurf, Aider, or any LLM-based coding system.

---

## Key Concepts

### Three Control Documents

Every project governed by this methodology uses three files:

| Document | Function | Analogy |
|---|---|---|
| **AGENT.md** (Directive) | Defines agent behavior, constraints, and project culture | Runtime policy |
| **SPEC.md** (Specification) | Complete technical design — what to build | Interface contract |
| **BUILD_LOG.md** (Build Log) | Persistent memory across sessions — where we are | System state |

### Phase Protocol

Software is built in sequential phases, each following an identical protocol:

```
Phase Prompt → Build → Verify → Approve → Next Phase
```

The **verification step** between phases is the methodology's strongest innovation — it catches cross-boundary integration bugs that unit tests miss.

### Agent Development Runtime

As the methodology matures, the `.build` directory evolves from static documents into an orchestration layer — and eventually into a full runtime environment for coordinating AI agents in software development. This concept is detailed in the parent meta-prompt.

---

## Origin

This ecosystem was developed through the construction of [Project SAGE](https://github.com/pragnakar/Project_Sage) — an MCP server that gives LLMs certified mathematical optimization capabilities. The methodology was born from solving real problems: context loss between sessions, architectural drift during implementation, silent integration bugs, and the absence of institutional memory when AI coding agents start fresh.

Every element in these meta-prompts earned its place by catching a defect, preventing a regression, or saving significant rework during that build.

---

## Structure

```
Meta_Prompts/
├── BOOTSTRAP.md                         ← AI entry point — imperative initialization protocol
├── AGENTS.md                            ← Cross-agent entry point
├── README.md                            ← You are here
├── templates/                           ← Ready-to-use templates
│   ├── AGENT.md                         ← Control doc: AI directive
│   ├── SPEC.md                          ← Control doc: specification
│   ├── BUILD_LOG.md                     ← Control doc: build history
│   └── project-init/                    ← Copy to parent project root (submodule use)
│       ├── CLAUDE.md
│       ├── AGENTS.md
│       ├── .windsurfrules
│       ├── .github/copilot-instructions.md
│       └── .cursor/rules/meta-prompts.md
├── LLM_NATIVE_SOFTWARE_ENGINEERING/     ← Parent meta-prompt
│   ├── LLM_NATIVE_SOFTWARE_ENGINEERING.md
│   └── README.md
├── Deployment_Engineering/              ← Companion: infrastructure
│   ├── Deployment_Engineering.md
│   └── README.md
├── DevOps/                              ← Companion: operations
│   ├── DevOps.md
│   └── README.md
├── Database/                            ← Companion: data layer
│   ├── Database.md
│   └── README.md
├── UI-UX/                               ← Companion: interface design
│   ├── UI-UX.md
│   └── README.md
├── Security_Engineering/                ← Companion: security
│   ├── Security_Engineering.md
│   └── README.md
├── MLOps/                               ← Companion: ML operations
│   ├── MLOps.md
│   └── README.md
├── API_Design/                          ← Companion: API design
│   ├── API_Design.md
│   └── README.md
├── Testing_Strategy/                    ← Companion: testing
│   ├── Testing_Strategy.md
│   └── README.md
├── Documentation/                       ← Companion: documentation
│   ├── Documentation.md
│   └── README.md
└── Scrum/                               ← Companion: agile process
    ├── Scrum.md
    └── README.md
```

Each subdirectory is an independent git repository (submodule). They evolve separately but are designed to work together through cross-references and consistent structure.

---

## Canonical Meta-Prompt Structure

Every companion meta-prompt follows the same canonical structure:

| Section | Purpose |
|---|---|
| **Thesis** | Why this domain matters |
| **When Invoked** | Trigger conditions for using the meta-prompt |
| **Scope** | What it covers and explicitly does NOT cover |
| **Principles** | Non-negotiable rules for the domain |
| **Practices** | Concrete implementation guidance |
| **Agent Instructions** | Do / Do NOT / Verify checklists for LLM agents |
| **Integration Points** | How it connects to every other meta-prompt |
| **Anti-Patterns** | Common mistakes and why they are harmful |
| **Quick-Start Checklist** | Actionable setup checklist |

This consistency means an LLM agent that understands one meta-prompt can navigate all of them.

---

## Getting Started

### For AI Agents

Point your AI agent at `BOOTSTRAP.md`. It contains the full imperative initialization sequence — the agent reads it, asks you about the project, selects the relevant companion meta-prompts, creates the `.build/` directory with `AGENT.md`, `SPEC.md`, and `BUILD_LOG.md`, and does not write a line of code until you approve the spec.

```
BOOTSTRAP.md  ←  start here
```

### Using This Repo as a Submodule

Add this repo as a submodule to your project, then copy the integration files for your AI tool from `templates/project-init/` to your project root. Replace `[META_PROMPTS_PATH]` in each file with the actual submodule path.

| Tool | File to copy |
|---|---|
| Claude Code | `templates/project-init/CLAUDE.md` |
| Any agent (universal) | `templates/project-init/AGENTS.md` |
| Cursor | `templates/project-init/.cursor/rules/meta-prompts.md` |
| Windsurf | `templates/project-init/.windsurfrules` |
| GitHub Copilot | `templates/project-init/.github/copilot-instructions.md` |

```bash
# Add as submodule
git submodule add https://github.com/pragnakar/META_PROMPTS meta_prompts

# Copy your tool's entry point to project root (example for Claude Code)
cp meta_prompts/templates/project-init/CLAUDE.md .
# Then replace [META_PROMPTS_PATH] with meta_prompts in the copied file
```

### For a New Project (manual setup)

1. Read `BOOTSTRAP.md` — it walks through the full setup
2. Or use the standalone templates in `templates/` to create `.build/AGENT.md`, `.build/SPEC.md`, `.build/BUILD_LOG.md` directly
3. Invoke companion meta-prompts as your project's needs expand

### Exploring the methodology

Start with the parent meta-prompt at `LLM_NATIVE_SOFTWARE_ENGINEERING/LLM_NATIVE_SOFTWARE_ENGINEERING.md`. It contains the complete philosophy, the evidence from the SAGE build, and the full ecosystem reference.

---

## Contributing

Each meta-prompt repository accepts contributions independently. If you've applied this methodology to a project and discovered improvements, gaps, or new patterns, contributions are welcome.

Areas of particular interest:

- Real-world case studies beyond the SAGE build
- Adaptations for specific tech stacks or domains
- Automation tooling for the .build system
- New companion meta-prompts for uncovered domains
- Integration patterns with CI/CD systems and planning tools

---

## License

MIT

## Author

Pragnakar Pedapenki ( https://x.com/pragnakar )

GitHub: [github.com/pragnakar](https://github.com/pragnakar)
