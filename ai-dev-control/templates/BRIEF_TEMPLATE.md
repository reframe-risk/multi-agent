# Engineering Brief: [DC Identifier] — [Title]

**Date:** [YYYY-MM-DD]
**Delivery Candidate:** [DC identifier]
**Workstream:** [WS identifier and name]
**Priority:** [P1 / P2 / P3]
**Owner:** [name]
**Prerequisite:** [prior DC or "None"]
**Risk Level:** [LOW / MEDIUM / HIGH] ([N] systems affected)

---

## Problem Statement

[Measured, not estimated. State the root cause, not just the symptom. Include
specific numbers where available — false positive rate, row count, error rate, etc.
Do not describe what you want to build; describe what is broken and why.]

---

## Autonomous Execution Authority

Proceed without pausing for:
- Any read-only shell command: `grep`, `cat`, `ls`, `find`, `git log`, `git diff`,
  `git status`, `--help` flags, SELECT queries
- Reading any file in the repository
- Running existing test and measurement scripts in read-only mode
- Writing new files to: [specify paths for this brief]
- [Add brief-specific autonomous actions]

Stop and surface to human before:
- Applying any database migration to remote (Turso or equivalent)
- Modifying shared infrastructure files used across all pipeline runs
- Running the full pipeline for companies not specified in this brief
- Deleting any file
- Any action not described in this brief

---

## Phases

### Phase 1: [name]

**Task:** [what to do]

**Output:** [specific artifact — file path, query result, document name]

**Validation gate:** [how to confirm Phase 1 is correct before Phase 2 begins]

---

### Phase 2: [name]

**Task:** [what to do]

**Output:** [specific artifact]

**Validation gate:** [confirmation step]

---

### Phase 3: [name — typically verification]

**Task:** Run verification sequence (see below)

**Output:** Measurement results confirming success criteria

---

## Do Not

- Do not [most plausible wrong action for this specific task]
- Do not [second most plausible wrong action]
- Do not [scope creep the brief is most likely to attract]
- Do not apply changes to remote until local validation passes
- Do not re-open [specific closed DC or decision most likely to be re-examined]

---

## Verification

```bash
# [Step 1 — e.g. apply migration]
[command]

# [Step 2 — e.g. run pipeline]
[command]

# [Step 3 — e.g. measure against ground truth]
[command]
```

---

## Success Criteria

1. [Measurable outcome 1 — specific value or state]
2. [Measurable outcome 2]
3. [Measurable outcome 3]
4. [Regression check — confirm prior baselines not degraded]

---

## Self-Check Before Marking Complete

- [ ] [Verification step 1 — specific check]
- [ ] [Verification step 2]
- [ ] [Regression check — e.g. "LIT pipeline run confirms no new FPs"]
- [ ] Wave tracker updated
- [ ] [Remote sync completed / confirmed not needed]
- [ ] Handoff artifact produced (if handing to another agent)

---

## Change Impact Assessment

**Systems affected:**
- [System 1] — [what changes]
- [System 2] — [what changes]

**Risk level:** [LOW / MEDIUM / HIGH]
**Regression risk:** [what existing behaviour might be affected and how to check]

**Required governance document:** [SIM / CHANGE_IMPACT doc path if MEDIUM/HIGH]

---

## What This Does NOT Cover

- [Item 1 — likely follow-on that is explicitly deferred]
- [Item 2]
- [Item 3]

---

## Output Documents

When complete, produce:
1. [Document 1 — path]
2. [Document 2 — path]
3. Update [WAVE_TRACKER].md: [DC identifier] → ✅ COMPLETE

---

**Document Status:** ACTIVE — ready for implementation
**References:**
- [relevant architecture doc]
- [relevant audit or ground truth doc]
