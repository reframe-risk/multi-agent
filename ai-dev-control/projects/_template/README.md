# [PROJECT NAME]

**Repo:** https://github.com/[org]/[repo]
**Owner:** [name]
**Status:** [Active / Paused / Complete]
**Standard version:** ai-dev-control v1.0

---

## What This Project Is

[2-3 sentences. What does this project do? What is the anchor goal?]

---

## Adaptation Notes

### Where this project diverges from the standard

[List any deliberate deviations from ai-dev-control standard and why.]

### What's already implemented

[Checkboxes of which standard components are in place.]

- SESSION_HEADER.md with structured constraints ✅ / ❌
- SESSION_START_PROMPT.md ✅ / ❌
- SESSION_END_PROMPT.md ✅ / ❌
- YAML briefs ✅ / ❌
- YAML handoffs ✅ / ❌
- current_state.yaml ✅ / ❌
- GitHub Actions schema validation ✅ / ❌

---

## Current State

See `current_state.yaml`.

---

## Active CTO Context

[Standing context the CTO session needs beyond what's in current_state.yaml.
Key architectural facts, domain-specific terminology, known constraints.]

---

## Pending Structural Tasks

[Tasks to bring this project up to full standard compliance.]

---

## How to Start a CTO Session for This Project

Load in this order:

1. `projects/[project]/current_state.yaml`
2. `projects/[project]/README.md`
3. `control/AGENT_ROLES.md`
4. `control/AUTONOMOUS_EXECUTION.md`
5. Then from project repo: `docs/control/SESSION_HEADER.md`, active brief

Produce a YAML handoff at session end. Commit to `projects/[project]/handoffs/`.
