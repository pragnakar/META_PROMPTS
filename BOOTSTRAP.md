# Meta-Prompt Bootstrap Protocol

> **For AI agents:** This is an imperative initialization protocol. Read it completely before taking any action. Do not write code, create files, or make architectural decisions until the initialization sequence below is complete.

---

## STOP — Read before acting

When you encounter this file, you are operating inside the **Meta-Prompt Ecosystem** — a structured protocol system for AI-assisted software development.

Your job is not to start building. Your job is to initialize the environment in which building will happen.

**Do not:**
- Write application code
- Create project directories or files (other than `.build/`)
- Choose a technology stack
- Make architectural decisions
- Begin implementing anything

You will do all of those things — but only after this sequence is complete and the human has approved the specification.

---

## Step 1 — Check for existing project state

Before anything else, check whether a `.build/` directory exists in the project root.

**If `.build/` exists:** The project is already initialized. Skip to the **Resuming an Existing Project** section at the bottom of this file.

**If `.build/` does not exist:** This is a new project. Continue with Step 2.

---

## Step 2 — Gather project context

Ask the human the following questions. Do not proceed until you have answers to at least questions 1 and 4.

> "Before we start building, I need to understand the project. Please describe:
> 1. What does this system do? (one paragraph)
> 2. Who are the users?
> 3. What is the tech stack, or what constraints exist? (answer 'not decided yet' if unknown)
> 4. What does a successful first version look like? What are the 3 most important things it must do?"

---

## Step 3 — Load the relevant meta-prompts

The meta-prompts are located relative to this file. Always load the parent meta-prompt first.

**Always load:**
- `LLM_NATIVE_SOFTWARE_ENGINEERING/LLM_NATIVE_SOFTWARE_ENGINEERING.md`

**Load based on project description:**

| If the project... | Load this meta-prompt |
|---|---|
| Runs anywhere beyond a local machine | `Deployment_Engineering/Deployment_Engineering.md` |
| Persists any data | `Database/Database.md` |
| Exposes or consumes APIs | `API_Design/API_Design.md` |
| Has a user-facing interface | `UI-UX/UI-UX.md` |
| Has any security requirements (almost always) | `Security_Engineering/Security_Engineering.md` |
| Will run in production | `DevOps/DevOps.md` |
| Includes machine learning models | `MLOps/MLOps.md` |
| Needs tests (always) | `Testing_Strategy/Testing_Strategy.md` |
| Needs documentation (always) | `Documentation/Documentation.md` |
| Uses iterative sprint delivery | `Scrum/Scrum.md` |

Read the loaded meta-prompts. Internalize their principles, practices, and agent instructions. They govern how you behave during the build.

---

## Step 4 — Create the project scaffold

Create the following structure in the **project root** (not inside the meta-prompts directory):

```
.build/
├── AGENT.md
├── SPEC.md
├── BUILD_LOG.md
└── spec/
    └── schemas/
```

---

## Step 5 — Generate AGENT.md

Create `.build/AGENT.md` using the template below. Replace every `[PLACEHOLDER]` with project-specific content derived from the human's answers in Step 2.

```markdown
# AGENT.md — AI Directive
# Project: [PROJECT NAME]
# Version: 0.1 — Initialized [DATE]

---

## Identity

You are an AI coding agent operating under the LLM-Native Software Engineering protocol. Your role is to build [PROJECT NAME] according to the specification in SPEC.md, following the constraints in this directive. You do not make architectural decisions unilaterally. You build what the spec describes and verify before proceeding.

## Non-Negotiable Rules

1. **Spec first.** No code is written for a phase before that phase's specification is approved by the human.
2. **One phase at a time.** Complete and verify the current phase before beginning the next.
3. **Verify before asking to proceed.** Each phase ends with a verification prompt. Run it, collect evidence, and report results before requesting phase approval.
4. **No secrets in code.** Reference secrets by environment variable name only. Never hardcode credentials, tokens, API keys, or connection strings.
5. **Structured logging.** All services emit structured JSON logs with at minimum: `trace_id`, `service`, `severity`, and `message` fields.
6. **Tests are not optional.** Every function has unit tests covering happy path, error path, and boundary conditions. Integration tests exist for all external system boundaries.
7. **Fail secure.** Authentication and authorization failures default to denial. Never fail open on unexpected states.
8. **No breaking changes without a version boundary.** API contracts and data schemas are not modified in ways that break existing consumers without explicit versioning.

## Technology Stack

- **Language:** [e.g., Python 3.12, TypeScript 5.x, Go 1.22]
- **Framework:** [e.g., FastAPI, Next.js, Gin]
- **Database:** [e.g., PostgreSQL 16, MongoDB 7, none]
- **Infrastructure:** [e.g., Docker, Kubernetes, AWS, local only]
- **Testing:** [e.g., pytest, Jest, Go test]

## Phase Protocol

Each development phase follows this exact cycle:

1. **Prompt** — Human provides the phase objective and approves the phase spec
2. **Build** — Agent implements only what the current phase spec describes
3. **Verify** — Agent runs the phase verification prompt and reports evidence (test results, checklist items, failures)
4. **Approve** — Human reviews evidence and either approves or requests rework

No phase begins without human approval of its spec. No phase ends without verification evidence.

## Project-Specific Constraints

- [Add constraints here — architectural decisions, business rules, compliance requirements]
- [e.g., "All database queries must be parameterized — no string interpolation"]
- [e.g., "The system must handle X concurrent users"]

## Explicit Out of Scope (v1.0)

- [What this system will NOT do in the current version]
- [Explicitly list things that might seem obvious to build but are not in scope]
```

---

## Step 6 — Draft SPEC.md

Create `.build/SPEC.md` using the template below. Fill in what you know from the project description. Leave later phases as stubs — they are detailed when earlier phases complete.

```markdown
# SPEC.md — Project Specification
# Project: [PROJECT NAME]
# Version: 0.1 — Phase 1 Draft
# Last Updated: [DATE]

---

## Project Overview

[One paragraph: what this system does, who uses it, and what problem it solves. Should directly reflect the human's answer from Step 2 question 1.]

## Goals

1. [Primary goal — the single most important thing this system must do]
2. [Secondary goal]
3. [Success criterion: how will we know v1.0 is done?]

## Non-Goals (Explicit Exclusions)

- [What this system will NOT do in v1.0]
- [Be specific — vague non-goals get violated]

## Architecture

### System Components

[List and briefly describe each major component: services, databases, frontends, background workers, external integrations. One sentence per component.]

### Data Flow

[Describe how data enters the system, how it moves between components, and how it leaves or is stored. A numbered list or diagram description is fine.]

### Technology Decisions

| Decision | Choice | Rationale |
|---|---|---|
| [e.g., Database] | [e.g., PostgreSQL] | [e.g., relational data model, team familiarity] |
| [Language] | [Choice] | [Reason] |

---

## Phase Plan

### Phase 1 — [Name: e.g., "Foundation", "Core Data Model", "Auth"] (CURRENT)

**Objective:** [One sentence: what gets built and why it's the right first phase.]

**Deliverables:**
- [ ] [Specific deliverable — a file, endpoint, schema, component]
- [ ] [Specific deliverable]
- [ ] [Specific deliverable]

**Acceptance Criteria:**
- [ ] [Criterion 1 — specific, testable, not vague. e.g., "POST /users returns 201 with user object on valid input"]
- [ ] [Criterion 2 — e.g., "All database queries use parameterized statements — verified by code review"]
- [ ] [Criterion 3 — e.g., "Unit tests cover happy path, 400 errors, and 500 errors for all endpoints"]

**Verification Prompt:**
> "Review the Phase 1 implementation against SPEC.md. Check each acceptance criterion. For each: state PASS or FAIL with specific evidence (line numbers, test output, or observed behavior). List any items not yet implemented. Do not mark the phase complete until all criteria pass."

---

### Phase 2 — [Name] (PLANNED)

**Objective:** [One sentence — detail added when Phase 1 is approved]

*Spec to be detailed after Phase 1 approval.*

---

### Phase 3 — [Name] (PLANNED)

**Objective:** [One sentence]

*Spec to be detailed after Phase 2 approval.*

---

## Data Models

*Populated during Phase 1 build. Add entity definitions here as they are designed.*

| Entity | Fields | Notes |
|---|---|---|
| [Entity name] | id, created_at, updated_at, [fields] | [Notes] |

---

## API Contracts

*Populated during build. Add endpoint definitions here. Store schemas in `.build/spec/schemas/`.*

| Method | Path | Request | Response | Status |
|---|---|---|---|---|
| [POST] | [/resource] | [schema ref] | [schema ref] | [Planned / Built / Verified] |

---

## Open Questions

*Decisions needed before or during build. Close each with a decision and date.*

- [ ] [Question — e.g., "Do we need multi-tenancy in v1.0?"] — *Decision pending*
```

---

## Step 7 — Initialize BUILD_LOG.md

Create `.build/BUILD_LOG.md` using the template below.

```markdown
# BUILD_LOG.md — Build History
# Project: [PROJECT NAME]
# Started: [DATE]

---

## Log Entry Format

Each entry follows this structure:

```
[DATE] | [PHASE] | [ACTION]
---
Context: [What state the build was in before this entry]
Work:    [What was done in this session]
Result:  [What changed — files created, decisions made, problems encountered]
Next:    [What comes next — the immediate next action]
Evidence: [Test output, verification results, checksums, or links]
```

---

## Log

[DATE] | phase-0 | initialized
---
Context: New project. Meta-Prompts bootstrap protocol executed.
Work:    Created .build/ directory structure. Generated AGENT.md, SPEC.md, BUILD_LOG.md from bootstrap templates. Read meta-prompts: [list loaded meta-prompts].
Result:  Project scaffold in place. Phase 1 spec drafted. Awaiting human review and approval.
Next:    Human reviews SPEC.md Phase 1. On approval, begin Phase 1 build.
Evidence: Directory structure created. Control documents initialized. No code written yet.
```

---

## Step 8 — Present and confirm

Show the human exactly what was created and ask for spec approval before writing any code:

```
Initialization complete. Here's what was set up:

.build/
├── AGENT.md          — AI directive (rules, stack, phase protocol)
├── SPEC.md           — Phase 1 specification (draft — needs your review)
├── BUILD_LOG.md      — Build history initialized
└── spec/schemas/     — Ready for API and data model schemas

Meta-prompts loaded:
  ✓ LLM-Native Software Engineering (always)
  [list others loaded based on Step 3]

Please review .build/SPEC.md.

Specifically:
- Does the Project Overview correctly capture what we're building?
- Are the Phase 1 Deliverables and Acceptance Criteria right?
- Anything missing from Non-Goals?

Once you approve the spec, I'll begin Phase 1.
```

**Do not write a single line of application code until the human explicitly approves the Phase 1 spec.**

---

## Phase Execution Protocol

Once initialization is complete and Phase 1 is approved, follow this cycle for every phase:

### During the build
- Implement only what the current phase spec describes — nothing more
- Check AGENT.md constraints before every significant decision
- If a decision isn't covered by the spec, stop and ask — do not invent scope
- Log significant decisions, trade-offs, and problems in BUILD_LOG.md as you go
- When you encounter a conflict between what's easiest and what the spec requires, follow the spec and flag the conflict

### At the end of each phase
Run the verification prompt from SPEC.md verbatim. Produce evidence:
- Test results: pass/fail counts, coverage percentage
- Checklist items from the Quick-Start Checklists of loaded meta-prompts
- Any failing items with proposed resolution

### Requesting phase approval
Present verification evidence. State clearly: "Phase N verification complete. [N] criteria pass, [N] fail." Do not begin the next phase until the human explicitly approves.

### Updating the spec
If scope changes are needed during a phase, propose the change in SPEC.md, show the diff, and ask for approval before implementing. Do not silently expand scope.

---

## Resuming an Existing Project

If `.build/` already exists when you read this file:

1. Read `.build/AGENT.md` — this is your directive
2. Read `.build/SPEC.md` — find the current phase and its acceptance criteria
3. Read `.build/BUILD_LOG.md` — the last entry tells you exactly where the build left off
4. Report to the human: "Resuming [PROJECT NAME]. Last log entry: [last entry summary]. Current phase: [phase]. Ready to continue with: [next action from last log entry]."
5. Ask: "Is there anything that changed since the last session I should know about?"

Do not restart initialization. Do not re-create control documents. Pick up exactly where the build left off.

---

## Meta-Prompt Reference

| Meta-Prompt | Path (relative to this file) | Domain |
|---|---|---|
| LLM-Native Software Engineering | `LLM_NATIVE_SOFTWARE_ENGINEERING/LLM_NATIVE_SOFTWARE_ENGINEERING.md` | Parent protocol |
| Deployment Engineering | `Deployment_Engineering/Deployment_Engineering.md` | Infrastructure & CI/CD |
| DevOps | `DevOps/DevOps.md` | Operations & reliability |
| Database | `Database/Database.md` | Data persistence |
| UI/UX | `UI-UX/UI-UX.md` | Interface design |
| Security Engineering | `Security_Engineering/Security_Engineering.md` | Security |
| MLOps | `MLOps/MLOps.md` | ML systems |
| API Design | `API_Design/API_Design.md` | API contracts |
| Testing Strategy | `Testing_Strategy/Testing_Strategy.md` | Test architecture |
| Documentation | `Documentation/Documentation.md` | Technical documentation |
| Scrum | `Scrum/Scrum.md` | Sprint delivery |

---

*Bootstrap Protocol v1.0 — Part of the Meta-Prompt Ecosystem: https://github.com/pragnakar*
