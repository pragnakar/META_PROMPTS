# SPEC.md — Project Specification
# Project: [PROJECT NAME]
# Version: 0.1 — Phase 1 Draft
# Last Updated: [DATE]

---

## Project Overview

[One paragraph: what this system does, who uses it, and what problem it solves.]

## Goals

1. [Primary goal — the single most important thing this system must do]
2. [Secondary goal]
3. [Success criterion: how will we know v1.0 is done?]

## Non-Goals (Explicit Exclusions)

- [What this system will NOT do in v1.0 — be specific]

## Architecture

### System Components

[List and briefly describe each major component. One sentence per component.]

### Data Flow

[How data enters, moves through, and exits the system.]

### Technology Decisions

| Decision | Choice | Rationale |
|---|---|---|
| Database | [choice] | [reason] |
| Language | [choice] | [reason] |
| Framework | [choice] | [reason] |

---

## Phase Plan

### Phase 1 — [Name] (CURRENT)

**Objective:** [One sentence: what gets built and why it's the right first phase.]

**Deliverables:**
- [ ] [Specific deliverable]
- [ ] [Specific deliverable]

**Acceptance Criteria:**
- [ ] [Criterion — specific, testable. e.g., "POST /users returns 201 with user object on valid input"]
- [ ] [Criterion — e.g., "All database queries use parameterized statements"]
- [ ] [Criterion — e.g., "Unit tests cover happy path, error path, boundary conditions"]

**Verification Prompt:**
> "Review the Phase 1 implementation against SPEC.md. Check each acceptance criterion. For each: state PASS or FAIL with specific evidence. List any items not yet implemented."

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

*Populated during build. Add entity definitions as they are designed.*

| Entity | Fields | Notes |
|---|---|---|
| [Entity] | id, created_at, updated_at, [fields] | [notes] |

---

## API Contracts

*Populated during build. Store full schemas in `.build/spec/schemas/`.*

| Method | Path | Request | Response | Status |
|---|---|---|---|---|
| [POST] | [/resource] | [schema] | [schema] | Planned |

---

## Open Questions

- [ ] [Question needing a decision before or during build]
