# Runbook: [Procedure Name]

**Version:** 1.0  
**Owner:** [Team or individual responsible for maintaining this document]  
**Last reviewed:** [Date]  
**Approver:** [Name and title]  
**Classification:** [Internal / Restricted]

---

## Purpose

[One or two sentences describing what this runbook covers and why it exists. Be specific - a reader picking this up for the first time should immediately know whether this is the right document.]

**Example:** This runbook covers the procedure for responding to a storage capacity alert on [system name]. It is intended for use by on-call infrastructure engineers.

---

## Scope

**In scope:**
- [What this runbook covers]

**Out of scope:**
- [What this runbook does not cover - point to the relevant runbook if one exists]

---

## When to use this runbook

[Describe the trigger. This might be an alert, a scheduled task, an escalation from another team, or a specific error condition.]

- Triggered by: [alert name / ticket type / manual request]
- Typical frequency: [daily / weekly / on-demand / incident-driven]

---

## Prerequisites

### Access required

| System / Tool | Access level required | How to request if missing |
|---------------|----------------------|--------------------------|
| [System name] | [Read / Write / Admin] | [Link or contact] |

### Knowledge assumed

- [Any background knowledge the operator needs before following this runbook]
- [Link to relevant documentation if background reading is needed]

### Checks before starting

- [ ] Confirm you have the access listed above
- [ ] Confirm the relevant system is in the expected state before beginning
- [ ] Notify [team / stakeholder] that this procedure is starting (if applicable)

---

## Procedure

> Follow steps in order. Do not skip steps. If you encounter an unexpected state, stop and escalate rather than improvising.

### Step 1: [Step title]

**What to do:**  
[Clear, specific instructions. Use sub-bullets for options or variations.]

**Expected result:**  
[What should happen after completing this step]

**If this fails:**  
[What to do if the expected result is not observed - next diagnostic step or escalation]

---

### Step 2: [Step title]

**What to do:**  
[Instructions]

**Expected result:**  
[Expected state]

**If this fails:**  
[Next step]

---

### Step 3: [Step title]

[Continue pattern as needed]

---

## Verification

[How to confirm the procedure was completed successfully. Include specific checks, not just "confirm it's working."]

- [ ] [Specific check 1]
- [ ] [Specific check 2]
- [ ] [Specific check 3]

---

## Rollback

[If this procedure can be reversed, describe how. If it cannot be reversed, state that explicitly.]

**Rollback applicable:** Yes / No / Partial

**Rollback procedure:**

1. [Step]
2. [Step]

**Rollback verification:**  
[How to confirm the system is back to its previous state]

---

## Escalation

If you cannot complete this procedure or encounter an unexpected condition:

| Scenario | Escalate to | Contact method | Response time expectation |
|----------|-------------|----------------|--------------------------|
| [Scenario] | [Name / team] | [Contact] | [e.g., 30 minutes] |
| [Scenario] | [Name / team] | [Contact] | [e.g., 4 hours] |

**Do not continue** past Step [X] without escalating if [specific condition].

---

## Post-Completion

- [ ] Log the procedure in [ticketing system / log file / change record]
- [ ] Notify [stakeholder] of completion
- [ ] Record any unexpected findings in the notes section below
- [ ] Update this runbook if any step was inaccurate or incomplete

---

## Related documents

| Document | Location |
|----------|----------|
| [Related runbook or policy] | [Link] |
| [Architecture diagram] | [Link] |

---

## Change log

| Version | Date | Author | Summary of changes |
|---------|------|--------|--------------------|
| 1.0 | [Date] | [Author] | Initial version |

---

## Notes

[Operator notes, exceptions, or observations from recent executions of this procedure.]
