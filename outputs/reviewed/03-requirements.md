# Requirements Specification

## Source Summary

Requirements in this document are derived from reviewed elicitation findings in `outputs/reviewed/02-elicitation.md`, supported by `CASE.md` and `inputs/assumptions.md`. Items not directly confirmed by the official case remain labeled `ASSUMPTION`. Unresolved policy and measurement gaps remain `OPEN QUESTION`.

## Functional Requirements

### FR-01 — Create assignment

- Statement: The system shall allow Lecturer to create an assignment record.
- Stakeholder: Lecturer
- Source: EL-01
- Status: FACT

### FR-02 — Set assignment deadline

- Statement: The system shall allow Lecturer to set a deadline for an assignment.
- Stakeholder: Lecturer
- Source: EL-02
- Status: FACT

### FR-03 — View assignments

- Statement: The system shall allow Student to view assignment records available to that Student.
- Stakeholder: Student
- Source: EL-04
- Status: FACT

### FR-04 — Submit assignment file

- Statement: The system shall allow Student to submit a file for an assignment.
- Stakeholder: Student
- Source: EL-05
- Status: FACT

### FR-05 — Monitor assignment status and deadline

- Statement: The system shall allow Student to view the recorded status and deadline for an assignment.
- Stakeholder: Student
- Source: EL-06
- Status: FACT

### FR-06 — Record grade

- Statement: The system shall allow Lecturer to record a grade for a Student submission.
- Stakeholder: Lecturer
- Source: EL-03
- Status: FACT

### FR-07 — Record feedback

- Statement: The system shall allow Lecturer to record feedback for a Student submission.
- Stakeholder: Lecturer
- Source: EL-03
- Status: FACT

### FR-08 — Manage users

- Statement: The system shall allow Administrator to create, update, or deactivate user records.
- Stakeholder: Administrator
- Source: EL-07, EL-Q-06
- Status: ASSUMPTION

### FR-09 — Manage courses

- Statement: The system shall allow Administrator to create, update, or deactivate course records.
- Stakeholder: Administrator
- Source: EL-08, EL-Q-07
- Status: ASSUMPTION

### FR-10 — Manage system configuration

- Statement: The system shall allow Administrator to update documented system configuration values.
- Stakeholder: Administrator
- Source: EL-09, EL-Q-08
- Status: ASSUMPTION

## Non-Functional Requirements

### NFR-01 — Assignment view response time

- Statement: Under an agreed test workload, the system shall display the assignment list within 2 seconds for at least 95% of Student requests.
- Measure and threshold: Response time <= 2 seconds for >= 95% of Student assignment-list requests.
- Operating context: `ASSUMPTION` — agreed test workload is not yet defined.
- Verification method: Performance test using the agreed workload.
- Source: FACT-07, EL-Q-10
- Status: ASSUMPTION

### NFR-02 — Role-based access control

- Statement: The system shall deny 100% of tested attempts to perform Lecturer, Student, or Administrator actions by an unauthorized role.
- Measure and threshold: 100% unauthorized role-action attempts denied in the access-control test suite.
- Operating context: Known roles are Lecturer, Student, and Administrator.
- Verification method: Role-based access-control tests.
- Source: FACT-03, FACT-07, CONSTRAINT-04
- Status: ASSUMPTION

### NFR-03 — Submission record availability

- Statement: During the agreed reliability test period, at least 99% of successfully recorded Student submissions shall remain retrievable by their assignment and Student association.
- Measure and threshold: >= 99% retrievability during agreed test period.
- Operating context: `ASSUMPTION` — reliability test period is not yet defined.
- Verification method: Reliability test and retrieval audit.
- Source: FACT-07, EL-05, EL-06
- Status: ASSUMPTION

### NFR-04 — Grade and feedback data integrity

- Statement: In the data-integrity test set, 100% of grade and feedback records shall remain linked to the correct Student submission.
- Measure and threshold: 100% referential integrity for grade-feedback-submission links in the test set.
- Operating context: Grade and feedback records created by Lecturer for Student submissions.
- Verification method: Referential integrity test.
- Source: FACT-07, EL-03
- Status: ASSUMPTION

## Business Rules

### BR-01 — Role-based activity boundary

- Rule: Lecturer, Student, and Administrator shall perform only activities assigned to their stakeholder role unless a future confirmed policy states otherwise.
- Source: FACT-03, CONSTRAINT-04
- Status: ASSUMPTION

### BR-02 — Deadline must be associated with an assignment

- Rule: A deadline shall be associated with one assignment record before Student deadline monitoring can display that deadline.
- Source: EL-02, EL-06, EL-D-01
- Status: ASSUMPTION

## Open Questions

- `OPEN QUESTION`: What required fields define a complete assignment record?
- `OPEN QUESTION`: What file formats and size limits are allowed for submission?
- `OPEN QUESTION`: What exact status values should Student see?
- `OPEN QUESTION`: What grading scale or grade format is used?
- `OPEN QUESTION`: Which configuration values are documented and editable by Administrator?
- `OPEN QUESTION`: What workload, test period, and data volume should be used for NFR verification?
