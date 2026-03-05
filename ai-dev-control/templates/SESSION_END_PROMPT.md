# SESSION_END_PROMPT.md

**Version:** 1.0
**Usage:** Paste at the end of every session (human or AI-assisted)

---

End-of-session governance check. Complete all sections before this session is closed.

## 1. Summarize Session Work

### What Was Completed
- [List all work completed — past tense, specific and concrete]

### What Was Explicitly NOT Addressed
- [Items discussed but deferred]
- [Items explicitly out of scope]
- [Unresolved items]

---

## 2. Bounded Task Status

### Is This a Bounded Task?

**If YES:**
- Name the task clearly
- State what it unblocked
- State what is now safe to assume
- State what remains explicitly out of scope

**If NO:**
- State: "No bounded task was completed"
- Explain why (exploration, debugging, partial work, etc.)

---

## 3. /control Document Updates

### SESSION_BOOTSTRAP_CURRENT.md (MANDATORY UPDATE)

Always update SESSION_BOOTSTRAP_CURRENT.md at the end of every session.

Update:
1. **Last Updated** — today's date and one-line session summary
2. **Current System State** — update any metrics that changed this session
3. **Most Recently Completed Work** — add this session as a new entry; remove oldest
   if window exceeds 5 sessions
4. **Active Delivery Candidate** — update to reflect current IN PROGRESS or next PENDING
5. **Open Blockers** — add new blockers; remove resolved ones
6. **Urgent Operational Items** — update or clear time-sensitive flags

### SESSION_BOOTSTRAP_STABLE.md (CONDITIONAL UPDATE)

Update ONLY IF one of the following occurred this session:
- A Wave or Workstream was marked complete
- A new architectural invariant was established (owner-approved)
- A governance phase changed
- A new item was added to "What Must Not Be Re-Opened"
- Infrastructure configuration changed

If none apply: state "SESSION_BOOTSTRAP_STABLE.md not updated — no stable content
changed this session."

### SESSION_BOOTSTRAP.md (REDIRECT STUB)

Do not update — this file is a redirect stub only. It points to STABLE and CURRENT.

### Other /control Documents

List any other /control docs requiring updates:
- SESSION_HEADER.md (governance rules changed?)
- DELIVERY_ROADMAP.md (new items or status changes?)
- [WAVE_TRACKER].md (DC status changed?)
- GOVERNANCE_INDEX.md (navigation changed?)
- Architecture diagrams (structural changes?)

If none: "No other /control updates required."

---

## 4. Wave Tracker Update (mandatory if any DC was worked on)

For each delivery candidate worked on:

- **If complete:** Change status to ✅ COMPLETE, add output doc path, add date, add
  one-line outcome note
- **If started but not finished:** Change status to 🔄 IN PROGRESS, add note on what remains
- **If blocked:** Change status to ❌ BLOCKED, add reason

Do NOT update rows you did not work on.

If no DC was worked on: "No tracker update required."

---

## 5. Handoff Artifact (mandatory if another agent picks up from here)

If this session's output will be consumed by another agent session, produce a handoff
artifact following the schema in `docs/control/GITHUB_STANDARD.md`.

Save to: `docs/handoffs/HANDOFF_{FROM}_{TO}_{DC}_{DATE}.md`

If no handoff: "No handoff artifact required — session ends with human."

---

## 6. Version Control

### Commit Required?

**If YES:**
- Commit message: `{type}({scope}): {description}` (see GITHUB_STANDARD.md)
- Files changed: [list]
- Push to remote: YES / NO / CHECKPOINT REQUIRED

**If NO:**
- State: "No commit required"
- Reason: [exploration only / no changes / etc.]

---

## 7. New Resting State

### What Next Session Should Assume as True
- [System capabilities now available]
- [Data integrity guarantees]
- [Pipeline behaviours]

### What Must NOT Be Re-Opened
- [Completed DCs from this session]
- [Settled decisions]

---

## 8. Stop

- ❌ Do NOT propose next steps
- ❌ Do NOT suggest follow-on work
- ❌ Do NOT expand scope
- ❌ Do NOT add future roadmap items

Await explicit instruction.

---

## Governance Compliance Checklist

- [ ] All changes align with anchor goal
- [ ] No new goals or systems introduced without architectural review
- [ ] System Impact Matrix created if MEDIUM/HIGH risk
- [ ] Owner approvals obtained if required
- [ ] Documentation reflects actual system state
- [ ] SESSION_BOOTSTRAP_CURRENT.md updated ⭐ MANDATORY
- [ ] Wave tracker updated if any DC was worked on ⭐ MANDATORY
- [ ] Commit message follows convention
- [ ] Handoff artifact produced if needed

---

## Acknowledge When Complete

Respond with:

1. ✅ Session summary provided
2. ✅ Bounded task status identified
3. ✅ /control updates specified and applied
4. ✅ Wave tracker updated (if applicable)
5. ✅ Handoff artifact produced (if applicable)
6. ✅ Version control actions specified
7. ✅ New resting state documented
8. **STOPPED** — awaiting explicit instruction
