# User Stories

## US-01 — Create assignment

- Story: As a Lecturer, I want to create an assignment record, so that coursework can be assigned to Students.
- Supports: FR-01
- Source: EL-01
- Status: FACT

### Acceptance Criteria

- AC-US01-01: Given a Lecturer and assignment information, when the Lecturer saves the assignment record, then the system stores the assignment record.
- AC-US01-02: Given a stored assignment record, when the record is inspected during verification, then the stored values match the values submitted by Lecturer.

## US-02 — Set assignment deadline

- Story: As a Lecturer, I want to set a deadline for an assignment, so that assignment timing is recorded.
- Supports: FR-02, BR-02
- Source: EL-02
- Status: FACT

### Acceptance Criteria

- AC-US02-01: Given a Lecturer and an assignment record, when the Lecturer saves a deadline, then the system stores the deadline for that assignment.
- AC-US02-02: Given an assignment with a stored deadline, when the assignment record is inspected during verification, then the stored deadline matches the value submitted by Lecturer.

## US-03 — View assignments

- Story: As a Student, I want to view assignment records available to me, so that I can know assigned coursework.
- Supports: FR-03
- Source: EL-04
- Status: FACT

### Acceptance Criteria

- AC-US03-01: Given a Student with available assignment records, when the Student opens available assignments, then the system displays those assignment records.
- AC-US03-02: Given a Student with no available assignment records, when the Student opens available assignments, then the system displays an empty assignment state.

## US-04 — Submit assignment file

- Story: As a Student, I want to submit a file for an assignment, so that my work can be recorded for review.
- Supports: FR-04, NFR-03
- Source: EL-05
- Status: FACT

### Acceptance Criteria

- AC-US04-01: Given a Student and an assignment record, when the Student submits a file for that assignment, then the system records a submission associated with that Student and assignment.
- AC-US04-02: Given a recorded submission, when the submission record is inspected during verification, then its Student and assignment association match the submitted context.

## US-05 — Monitor assignment status and deadline

- Story: As a Student, I want to view assignment status and deadline, so that I can track assignment progress.
- Supports: FR-05, FR-02
- Source: EL-06
- Status: FACT

### Acceptance Criteria

- AC-US05-01: Given a Student and an assignment with a recorded status, when the Student opens that assignment, then the system displays the recorded status.
- AC-US05-02: Given a Student and an assignment with a recorded deadline, when the Student opens that assignment, then the system displays the recorded deadline.

## US-06 — Record grade and feedback

- Story: As a Lecturer, I want to record a grade and feedback for a Student submission, so that evaluation information can be captured.
- Supports: FR-06, FR-07, NFR-04
- Source: EL-03
- Status: FACT

### Acceptance Criteria

- AC-US06-01: Given a Lecturer and a Student submission, when the Lecturer records a grade, then the system stores the grade linked to that submission.
- AC-US06-02: Given a Lecturer and a Student submission, when the Lecturer records feedback, then the system stores the feedback linked to that submission.

## US-07 — Manage users

- Story: As an Administrator, I want to manage user records, so that system users can be administered.
- Supports: FR-08, BR-01, NFR-02
- Source: EL-07, EL-Q-06
- Status: ASSUMPTION

### Acceptance Criteria

- AC-US07-01: Given an Administrator and user information, when the Administrator saves a user record, then the system stores the user record.
- AC-US07-02: Given a stored user record, when the Administrator inspects it during verification, then the stored values match the submitted values.

## US-08 — Manage courses and configuration

- Story: As an Administrator, I want to manage course records and documented configuration values, so that system administration data can be controlled.
- Supports: FR-09, FR-10
- Source: EL-08, EL-09, EL-Q-07, EL-Q-08
- Status: ASSUMPTION

### Acceptance Criteria

- AC-US08-01: Given an Administrator and course information, when the Administrator saves a course record, then the system stores the course record.
- AC-US08-02: Given an Administrator and a documented configuration value, when the Administrator updates the value, then the system stores the updated configuration value.

## Open Questions

- `OPEN QUESTION`: Which assignment fields, file formats, status values, grading formats, and configuration categories are authoritative?
- `OPEN QUESTION`: Which reviewed requirements should be split after policy details are confirmed?
