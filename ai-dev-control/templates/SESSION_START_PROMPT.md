# SESSION_START_PROMPT.md

**Version:** 1.0
**Usage:** Paste at the start of every session (human or AI-assisted)

---

This session operates under the `/control` governance system.

Before proposing or executing any work:

## 1. Load Authoritative Context

Load in this order:

1. `docs/control/SESSION_BOOTSTRAP_STABLE.md` — Architectural invariants, completed
   waves, governance phase, what must not be re-opened. Load once; treat as permanent
   for this session.
2. `docs/control/SESSION_BOOTSTRAP_CURRENT.md` — Current baselines, active delivery
   candidate, open blockers, recent work (last 3–5 sessions). This is the volatile
   layer; it changes every session.
3. `docs/control/SESSION_HEADER.md` — Your role, autonomous execution authority,
   immutable governance rules, prohibited modifications.
4. `docs/control/DELIVERY_ROADMAP.md` — Anchor goal status, delivery waves.
5. `docs/control/[WAVE_TRACKER].md` — Active delivery candidate status.
6. `docs/control/GOVERNANCE_INDEX.md` — Navigation and references.
7. [PROJECT: add project-specific documents]

## 2. Load Canonical Architecture Diagrams

[PROJECT: list the canonical architecture reference documents for this project]

## 3. State Your Understanding

Before proposing any work, explicitly state:

### Current Delivery Status
- Anchor goal: [ACHIEVED / ACTIVE] — [one-line description]
- Waves complete: [list]
- Active wave: [name and status]

### Most Recently Completed Work
State the most recent bounded task from the tracker:
- What was completed
- When it was completed
- What it unblocked

### Active Delivery Candidate
- Which DC is currently IN PROGRESS or next PENDING
- Its current status and any blockers

### Current Session Scope
- What IS in scope (from the user's instruction)
- What IS NOT in scope (deferred items, completed work, out-of-brief)

## 4. DO NOT

- ❌ Re-open completed delivery candidates
- ❌ Propose work outside active workstreams
- ❌ Make code changes before confirming scope with user
- ❌ Infer intent beyond what is documented
- ❌ Pause for permission on actions covered by Autonomous Execution Authority
- ❌ [PROJECT: add project-specific prohibitions]

## 5. Treat DELIVERY_ROADMAP.md as System State Register

- If work is not marked COMPLETE, assume it is not settled
- If work is marked COMPLETE, treat it as closed ground
- Do not re-open completed delivery candidates
- Do not propose follow-on work without explicit user request

## 6. Before Acting

1. **Summarize** the next single bounded decision or task
2. **Confirm** alignment with anchor goal and open scope
3. **Check** whether the action is within Autonomous Execution Authority
4. **Execute** autonomously if authorized; surface if not

---

## Acknowledge When Ready

Respond with:

1. ✅ Control plane loaded
2. Anchor goal status
3. Most recent completed work
4. Active delivery candidate and status
5. What is in scope for this session
6. What you will NOT do

Then await user instruction.
