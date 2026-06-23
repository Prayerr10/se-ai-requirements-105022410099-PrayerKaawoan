# Raw AI Output — Skill 3: Requirements Elaboration and Specification

## Invocation

Read `outputs/reviewed/02-elicitation.md`, `CASE.md`, `inputs/assumptions.md`, and `skills/03-specification/SKILL.md`. Execute Requirements Elaboration and Specification. Save the first output as raw AI output. Draft requirements and user stories only; do not prioritize, validate, create diagrams, create traceability, or create change requests.

## Draft Artifact: outputs/reviewed/03-requirements.md

### Source Summary

Primary evidence: EL-01 through EL-09 from reviewed elicitation. Assumptions and unresolved policy gaps are retained from `inputs/assumptions.md`.

### Functional Requirements

#### FR-01 — Create assignment
- Statement: The system shall allow Lecturer to create an assignment record.
- Stakeholder: Lecturer
- Source: EL-01
- Status: FACT

#### FR-02 — Set assignment deadline
- Statement: The system shall allow Lecturer to set a deadline for an assignment.
- Stakeholder: Lecturer
- Source: EL-02
- Status: FACT

#### FR-03 — View assignment
- Statement: The system shall allow Student to view available assignments.
- Stakeholder: Student
- Source: EL-04
- Status: FACT

#### FR-04 — Submit file
- Statement: The system shall allow Student to submit a file for an assignment.
- Stakeholder: Student
- Source: EL-05
- Status: FACT

#### FR-05 — Monitor submission status
- Statement: The system shall allow Student to monitor assignment status.
- Stakeholder: Student
- Source: EL-06
- Status: FACT

#### FR-06 — Record grade
- Statement: The system shall allow Lecturer to record a grade for a Student submission.
- Stakeholder: Lecturer
- Source: EL-03
- Status: FACT

#### FR-07 — Record feedback
- Statement: The system shall allow Lecturer to record feedback for a Student submission.
- Stakeholder: Lecturer
- Source: EL-03
- Status: FACT

#### FR-08 — Manage users
- Statement: The system shall allow Administrator to manage users.
- Stakeholder: Administrator
- Source: EL-07
- Status: FACT

### Non-Functional Requirements

#### NFR-01 — Performance
- Statement: The system should respond quickly when Student views assignments.
- Measure and threshold: quickly
- Operating context: normal usage
- Verification method: not specified
- Source: ASSUMPTION-08
- Status: ASSUMPTION

#### NFR-02 — Security
- Statement: The system shall restrict role-specific actions to authorized users.
- Measure and threshold: 100% unauthorized role-action attempts denied in access-control tests.
- Operating context: role-based access test set
- Verification method: access-control test
- Source: FACT-08, CONSTRAINT-04
- Status: ASSUMPTION

#### NFR-03 — Reliability
- Statement: The system shall keep submission status available after a successful submission.
- Measure and threshold: 99% availability during test period.
- Operating context: test period not defined
- Verification method: reliability test
- Source: FACT-08, EL-06
- Status: ASSUMPTION

#### NFR-04 — Data integrity
- Statement: The system shall keep grades and feedback linked to the correct Student submission.
- Measure and threshold: 100% referential integrity in validation test set.
- Operating context: grade and feedback records
- Verification method: data integrity test
- Source: FACT-08, EL-03
- Status: ASSUMPTION

### Business Rules

#### BR-01 — Role-based activity boundary
- Rule: Users act through one of the known stakeholder roles: Lecturer, Student, or Administrator.
- Source: FACT-03
- Status: FACT

#### BR-02 — Assignment deadline existence
- Rule: An assignment should have a deadline before Student monitors deadline status.
- Source: EL-02, EL-06
- Status: ASSUMPTION

## Draft Artifact: outputs/reviewed/04-user-stories.md

### US-01 — Create assignment
- Story: As a Lecturer, I want to create an assignment, so that Students can receive assigned coursework.
- Supports: FR-01
- Source: EL-01
- Status: FACT
#### Acceptance Criteria
- AC-US01-01: Given a Lecturer, when the Lecturer saves an assignment record, then the system stores the assignment record.
- AC-US01-02: Given a stored assignment record, when the Lecturer inspects it, then the stored values match the submitted values.

### US-02 — Set deadline
- Story: As a Lecturer, I want to set an assignment deadline, so that assignment timing is recorded.
- Supports: FR-02
- Source: EL-02
- Status: FACT
#### Acceptance Criteria
- AC-US02-01: Given a Lecturer and an assignment, when the Lecturer saves a deadline, then the system stores the deadline for that assignment.
- AC-US02-02: Given a saved deadline, when the assignment record is inspected, then the stored deadline matches the submitted deadline value.

### US-03 — View assignment
- Story: As a Student, I want to view assignments, so that I can know assigned coursework.
- Supports: FR-03
- Source: EL-04
- Status: FACT
#### Acceptance Criteria
- AC-US03-01: Given a Student, when the Student opens available assignments, then the system displays assignment records available to that Student.
- AC-US03-02: Given no available assignment records, when the Student opens available assignments, then the system displays an empty state.

### US-04 — Submit file
- Story: As a Student, I want to submit a file, so that my work can be recorded for review.
- Supports: FR-04
- Source: EL-05
- Status: FACT
#### Acceptance Criteria
- AC-US04-01: Given a Student and an assignment, when the Student submits a file, then the system records a submission for that assignment.

### US-05 — Monitor status
- Story: As a Student, I want to monitor assignment status and deadline, so that I can track assignment progress.
- Supports: FR-05, FR-02
- Source: EL-06
- Status: FACT
#### Acceptance Criteria
- AC-US05-01: Given a Student and an assignment with status, when the Student opens the assignment, then the system displays the recorded status.
- AC-US05-02: Given a Student and an assignment with a deadline, when the Student opens the assignment, then the system displays the recorded deadline.

### US-06 — Manage users
- Story: As an Administrator, I want to manage users, so that system users can be administered.
- Supports: FR-08
- Source: EL-07
- Status: FACT
#### Acceptance Criteria
- AC-US06-01: Given an Administrator, when the Administrator saves a user record, then the system stores the user record.
- AC-US06-02: Given a stored user record, when the Administrator inspects it, then the stored values match the submitted values.

### Open Questions

- OPEN QUESTION: What exact threshold should replace “quickly” in NFR-01?
- OPEN QUESTION: What second acceptance criterion should be added to US-04?
