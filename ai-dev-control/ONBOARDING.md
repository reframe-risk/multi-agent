# ONBOARDING.md — Start Here

**For:** CTO sessions arriving at this repo for the first time
**Repo:** https://github.com/reframe-risk/multi-agent
**Owner:** Simon Schwab

---

## What This Repo Is

This is the canonical standard for multi-agent AI development across all of Simon's
projects. It defines how AI agents collaborate — how they communicate, maintain state,
hand off work, and stay within scope.

It is not a project. It has no codebase. It is the reference that every project-level
`/control` directory is adapted from.

---

## If You Are a CTO Session — Read In This Order

### Step 1: Understand the standard (read once)

1. `control/VISION.md` — what this system is and why it exists (5 min read)
2. `control/AGENT_ROLES.md` — your role definition, authority, scope boundary,
   escalation triggers, and system prompt template. **Read your role section carefully.**
3. `control/AUTONOMOUS_EXECUTION.md` — what you can do without pausing.
   Cross-reference with your role definition.
4. `control/PROMPT_DISCIPLINE.md` — the 7 patterns. Reference when authoring briefs.
5. `control/GITHUB_STANDARD.md` — branch naming, commit format, PR schema, handoff format.
6. `control/CLAUDE_CODE_SETTINGS.md` — tooling layer. How permissions and auto-approval
   settings map to autonomous execution authority.

### Step 2: Understand the communication contracts

7. `schemas/handoff.schema.yaml` — the schema for every handoff artifact you produce.
   Read the comments — every field is explained.
8. `schemas/brief.schema.yaml` — the schema for every engineering brief you author.
9. `examples/HANDOFF_CTO_DEV_DC-W3-07D_2026-03-05.yaml` — a real populated handoff.
   This is what your session end output should look like.
10. `examples/DC_W3_07d_ENGINEERING_BRIEF.yaml` — a real populated brief.

### Step 3: Locate your project

11. `projects/README.md` — the projects layer overview
12. `projects/{your-project}/README.md` — project context, adaptation notes,
    CTO session load order, what's implemented vs pending
13. `projects/{your-project}/current_state.yaml` — current metrics, active DC,
    open blockers. This is your starting state.

### Step 4: Load project-level control documents

From the project repo itself (e.g. reframe-app):
- `docs/control/SESSION_HEADER.md` — immutable governance rules for this project
- `docs/control/SESSION_BOOTSTRAP_STABLE.md` — architectural invariants (once split is done)
- `docs/control/SESSION_BOOTSTRAP_CURRENT.md` — volatile current state (once split is done)
- Active brief (path in `current_state.yaml → active_work.brief_path`)

---

## What You Produce at Session End

Every CTO session closes with two committed artifacts:

1. **Handoff YAML** — following `schemas/handoff.schema.yaml`
   - Committed to: `projects/{project}/handoffs/HANDOFF_CTO_{TO}_{DC}_{DATE}.yaml`
   - Also committed to: `docs/handoffs/` in the project repo

2. **Updated `current_state.yaml`** — reflecting any state changes from this session
   - Committed to: `projects/{project}/current_state.yaml`

Do not close a session without both artifacts committed.

---

## Decisions Log

The `/decisions` directory records why the standard is the way it is.
Read before proposing changes to the standard.

| # | Decision | Date |
|---|---|---|
| 001 | Bootstrap split — stable vs current | 2026-03-05 |
| 002 | Structured YAML format for AI-to-AI communication | 2026-03-05 |
| 003 | Role definitions — full agent team | 2026-03-05 |

---

## Current Projects

| Project | Status | State file |
|---|---|---|
| reframe-app | Active — Wave 3 | `projects/reframe-app/current_state.yaml` |

---

## Key Rules (Non-Negotiable)

- Projects are adapted **toward** this standard, not the other way around
- Do not modify this repo to fit a specific project — adapt the project's copies
- Every session ends with a committed handoff artifact — no exceptions
- `human_loop.required_before_proceeding: true` means stop and wait — do not proceed
- Decisions are recorded in `/decisions` before changes are made to the standard

---

## If You Are Reviewing This Repo

If you have been asked to review and give feedback:

1. Read `decisions/` to understand the reasoning behind current design choices
2. Read `control/AGENT_ROLES.md` for your specific role section
3. Produce a written assessment — do not make changes
4. Commit your assessment to `projects/{project}/handoffs/` as a YAML handoff
   with `to_role: HUMAN` and your findings in the `decisions` array
5. Stop and await instruction
