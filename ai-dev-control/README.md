# ai-dev-control

The standard for multi-agent AI development teams. This repository defines how AI agents collaborate on software projects — how they communicate, maintain state, hand off work, and stay within scope.

It is not tied to any specific project. Project-level `/control` directories are adapted from this standard.

---

## What Problem This Solves

Multi-agent AI development fails for five consistent reasons:

1. **Inconsistent state** — each session starts with a different understanding of what is true and what is in scope
2. **Scope creep** — agents default to being helpful, doing more than asked when instructions are ambiguous
3. **Cascading errors** — mistakes in early phases propagate silently with no validation gate
4. **Human bottlenecks** — agents pause for permission on decisions that should have been pre-authorized
5. **Handoff loss** — state and decisions made by one agent are not reliably available to the next

This system addresses all five through structure, not cleverness.

---

## Repository Structure

```
/control        — the standard itself
/schemas        — YAML schemas for structured AI-to-AI communication
/templates      — ready-to-adapt files for new project /control directories
/examples       — populated examples showing schemas in use
/decisions      — record of decisions that shaped this standard
```

---

## Core Principle: Structured over Prose

Free-text prompts are the right format for human-to-AI communication. They are not the right format for AI-to-AI communication — prose requires interpretation, and interpretation is where variance enters.

This system uses two communication formats:

**Structured YAML** — for anything an agent must act on: briefs, handoffs, session state, metrics. Typed fields, required vs optional explicit, no implicit structure.

**Markdown prose** — for anything a human must understand: governance rules, architectural rationale, role definitions, decisions. Prose is appropriate here; agents read it for context, not instruction.

---

## Key Documents

### The Standard (`/control`)

| File | Purpose |
|---|---|
| `VISION.md` | What this system is, why it exists, design principles |
| `AGENT_ROLES.md` | Role definitions — authority, scope boundary, escalation triggers |
| `PROMPT_DISCIPLINE.md` | The 7 prompt engineering patterns applied throughout this system |
| `AUTONOMOUS_EXECUTION.md` | Pre-authorized action classes by role — eliminates unnecessary permission pauses |
| `GITHUB_STANDARD.md` | Branch naming, commit format, PR schema, handoff artifact standard |

### The Schemas (`/schemas`)

| File | Purpose |
|---|---|
| `handoff.schema.yaml` | Canonical schema for AI-to-AI handoff artifacts |
| `brief.schema.yaml` | Canonical schema for engineering briefs |

### The Templates (`/templates`)

Ready to copy into a new project's `docs/control/` directory. Fields marked `[PROJECT: ...]` are filled in per project.

| File | Purpose |
|---|---|
| `SESSION_HEADER.md` | Governance constitution — role, autonomous authority, immutable rules |
| `SESSION_BOOTSTRAP_STABLE.md` | Load-once invariants — anchor goal, completed waves, architectural facts |
| `SESSION_BOOTSTRAP_CURRENT.md` | Volatile session state — current metrics, active DC, open blockers |
| `SESSION_START_PROMPT.md` | Paste at session start — load order, role declaration, scope confirmation |
| `SESSION_END_PROMPT.md` | Paste at session end — updates, handoff, commit, stop |
| `BRIEF_TEMPLATE.yaml` | Structured engineering brief — all 7 prompt discipline patterns built in |
| `HANDOFF_TEMPLATE.yaml` | Structured handoff artifact — produced by outgoing agent, read by incoming |

### The Examples (`/examples`)

Both schemas populated with real data from a production session, so any agent has a concrete reference.

---

## How the Human Stays in the Loop

The human is the decision gate, not the data pipe.

**Old model:** Human copies prompt from CTO session → pastes to Dev terminal → copies output back. Human is the relay.

**This model:** CTO commits a YAML handoff file. Dev reads it at session start. The `human_loop.required_before_proceeding` field in the handoff declares whether human review is needed before Dev acts. Open questions with `owner: HUMAN` surface explicitly. Everything else proceeds autonomously within the agent's pre-authorized scope.

The human is pulled in at escalation points — not at every handoff.

---

## How to Start a New Project

1. Copy `/templates` into the new project's `docs/control/` directory
2. Fill in all `[PROJECT: ...]` fields
3. Create `docs/briefs/` and `docs/handoffs/` directories in the project repo
4. Read `control/AGENT_ROLES.md` and adapt authority boundaries to the project's risk profile
5. Record adaptation decisions in the project's own `/decisions` directory
6. Do not modify this repository to fit the project — adapt the copies, preserve the standard

---

## Decisions

| # | Decision | Date |
|---|---|---|
| 001 | Bootstrap split — stable vs current session state | 2026-03-05 |
| 002 | Structured YAML format for AI-to-AI communication | 2026-03-05 |

---

## Current Status

**Standard version:** 1.0
**Roles defined:** CTO (full definition)
**Roles pending:** Dev, PM, Reviewer
**Projects using this standard:** reframe-app (adaptation in progress)
