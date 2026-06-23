# Requirements Validation

## Validation Scope

- Inputs reviewed: `outputs/reviewed/03-requirements.md`, `outputs/reviewed/04-user-stories.md`, and `outputs/reviewed/05-prioritization.md`.
- Selection rationale: Validate high-priority FRs, assumption-heavy administrative FRs, and a measurable NFR. Selected items: FR-01, FR-04, FR-07, FR-08, NFR-01.

## Validation Results

### FR-01

- Original statement: The system shall allow Lecturer to create an assignment record.
- Decision: No change.
- Clarity: PASS — actor and behavior are explicit.
- Completeness: OPEN QUESTION — required assignment fields are not defined.
- Consistency: PASS — aligns with EL-01 and US-01.
- Feasibility: PASS — no conflicting evidence is present.
- Testability: PASS — AC-US01-01 and AC-US01-02 verify record creation and stored values.
- Traceability: PASS — linked to Lecturer, EL-01, US-01, AC-US01-01, AC-US01-02, and Must priority.
- Proposed revision: None.
- Revision rationale: Field-level details are an open question, but the core requirement is supported.
- Affected artifacts: FR-01, US-01.

### FR-04

- Original statement: The system shall allow Student to submit a file for an assignment.
- Decision: No change.
- Clarity: PASS — actor and behavior are explicit.
- Completeness: OPEN QUESTION — allowed file formats, size limits, late submission, and resubmission policies are unknown.
- Consistency: PASS — aligns with EL-05 and US-04.
- Feasibility: OPEN QUESTION — file constraints and operational limits are not defined.
- Testability: PASS — AC-US04-01 and AC-US04-02 verify recorded submission association.
- Traceability: PASS — linked to Student, EL-05, US-04, AC-US04-01, AC-US04-02, and Must priority.
- Proposed revision: None.
- Revision rationale: Adding file constraints now would invent policy. Keep the core FACT and leave constraints open.
- Affected artifacts: FR-04, US-04, NFR-03.

### FR-07

- Original statement: The system shall allow Lecturer to record feedback for a Student submission.
- Decision: No change.
- Clarity: PASS — actor, behavior, and target object are explicit.
- Completeness: OPEN QUESTION — feedback visibility timing is unknown.
- Consistency: PASS — aligns with EL-03, US-06, and Should priority.
- Feasibility: PASS — no conflicting evidence is present.
- Testability: PASS — AC-US06-02 verifies feedback storage linked to a submission.
- Traceability: PASS — linked to Lecturer, EL-03, US-06, AC-US06-02, and Should priority.
- Proposed revision: None.
- Revision rationale: Visibility policy should be clarified separately without weakening the supported storage requirement.
- Affected artifacts: FR-07, US-06.

### FR-08

- Original statement: The system shall allow Administrator to create, update, or deactivate user records.
- Decision: Keep as ASSUMPTION.
- Clarity: PASS — actor and operations are explicit.
- Completeness: OPEN QUESTION — exact allowed user operations are not confirmed by official case.
- Consistency: PASS — aligns with Administrator user management in EL-07 and BR-01.
- Feasibility: PASS — no conflict is present.
- Testability: PASS — AC-US07-01 and AC-US07-02 verify stored user records.
- Traceability: PASS — linked to Administrator, EL-07, US-07, AC-US07-01, AC-US07-02, and Must priority.
- Proposed revision: None.
- Revision rationale: The operations are useful structure but remain ASSUMPTION until Administrator policy is confirmed.
- Affected artifacts: FR-08, US-07, BR-01.

### NFR-01

- Original statement: Under an agreed test workload, the system shall display the assignment list within 2 seconds for at least 95% of Student requests.
- Decision: Keep as ASSUMPTION.
- Clarity: PASS — metric and threshold are explicit.
- Completeness: OPEN QUESTION — agreed workload is not defined.
- Consistency: PASS — supports performance concern in FACT-08 and Student assignment viewing.
- Feasibility: OPEN QUESTION — feasibility depends on workload and platform decisions not yet supplied.
- Testability: PASS — performance test can verify the threshold once workload is defined.
- Traceability: PASS — linked to Student assignment viewing and EL-Q-10.
- Proposed revision: None.
- Revision rationale: The raw output’s vague “quickly” was replaced with a measurable ASSUMPTION; workload remains open.
- Affected artifacts: NFR-01, US-03.

## Unresolved Open Questions

- `OPEN QUESTION`: What required fields define an assignment record?
- `OPEN QUESTION`: What file formats, size limits, late-submission rules, and resubmission rules apply?
- `OPEN QUESTION`: When are grades and feedback visible to Student?
- `OPEN QUESTION`: Which user-management operations are officially allowed?
- `OPEN QUESTION`: What workload should be used to verify NFR-01?

## Validation Summary

- Five requirements were checked across clarity, completeness, consistency, feasibility, testability, and traceability.
- All selected items are usable for the assignment draft, but several remain partially assumption-based.
- No unsupported policy was added during validation.

## Human Review Status

Pending student confirmation. This validation draft does not establish a final baseline.
