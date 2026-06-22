# Validation and Change Management Examples

These examples demonstrate invocation and output shape. They are not final requirements, reviewed outputs, a change request, a diagram, or a traceability matrix for the Student Task Management System.

Preserve `FACT`, `ASSUMPTION`, `CONSTRAINT`, and `OPEN QUESTION` labels exactly; never promote one category to another without recorded evidence.

## Example Invocation

```text
Use skills/05-validation-change/SKILL.md.

Read outputs/reviewed/05-prioritization.md, outputs/reviewed/03-requirements.md, outputs/reviewed/04-user-stories.md, outputs/reviewed/01-inception.md, and outputs/reviewed/02-elicitation.md. Validate at least five requirements for clarity, completeness, consistency, feasibility, testability, and traceability.

Also analyze this illustrative proposal:
`ASSUMPTION`: Allow a Student to replace a submitted file after the deadline.

Return draft sections for outputs/reviewed/07-validation.md and outputs/reviewed/08-change-request.md. Do not write files and do not assume the change is accepted.
```

## Example Output

```markdown
# Requirements Validation

## Validation Scope
- Inputs reviewed: prioritized requirements, requirements specification, user stories, inception, and elicitation artifacts
- Selection rationale: five illustrative requirements selected by priority, uncertainty, and change exposure

## Validation Results
### FR-EX-01
- Original statement: After a successful upload, the system records the Student submission status and timestamp.
- Evidence label: ASSUMPTION
- Clarity: PASS — The Student, trigger, and recorded result are stated.
- Completeness: OPEN QUESTION — “Successful upload” is not defined in the example input.
- Consistency: PASS — No conflicting example statement is supplied.
- Feasibility: OPEN QUESTION — Applicable operational limits are unavailable.
- Testability: PASS — Status and timestamp are observable after the trigger.
- Traceability: FAIL — No acceptance-criteria ID is supplied.
- Proposed revision: None
- Revision rationale: Missing evidence must be resolved before changing the statement.
- Affected artifacts: US-EX-01; missing acceptance-criteria reference

## Unresolved Open Questions
- `OPEN QUESTION`: What conditions define a successful upload?

## Human Review Status
Pending.

# Requirement Change Request

## Change Description
`ASSUMPTION`: Allow a Student to replace a submitted file after the deadline.

## Impact Analysis
- Scope: Submission behavior would change.
- Consistency: Deadline rules may conflict; the policy is unavailable.
- Feasibility: `OPEN QUESTION` pending operational constraints.
- Testability: Replacement timing and permitted outcomes need measurable criteria.
- Traceability: Affected requirement and acceptance-criteria IDs must be identified.
- Stakeholder interests: Student, Lecturer, and Administrator decisions require confirmation.
- Dependencies and priorities: Reassess after affected IDs are known.

## Decision
- Recommendation: NEEDS CLARIFICATION
- Rationale: The proposal depends on deadline and resubmission policies that remain `OPEN QUESTION`.
- Conditions: Record policy decisions, update affected artifacts, and rerun validation.

## Human Approval Status
Pending; no change has been approved.
```

The complete run must contain at least five validation result blocks. The single block above is intentionally abbreviated to keep the example concise.
