# Use Case Specification

## Scope and Source

This use case specification is based only on the reviewed requirements in `outputs/reviewed/03-requirements.md`, user stories in `outputs/reviewed/04-user-stories.md`, and prioritization in `outputs/reviewed/05-prioritization.md`.

Actors used in this document:

- Lecturer
- Student
- Administrator

Rules for this document:

- No new functionality is introduced beyond existing FR items.
- Details not confirmed by the case remain marked as `ASSUMPTION` or `OPEN QUESTION`.
- Each use case references related FR IDs so it can be used as a basis for the use case diagram in the next stage.

## Use Case List

| Use Case ID | Use Case Name | Primary Actor | Related FR |
|---|---|---|---|
| UC-01 | Create Assignment | Lecturer | FR-01 |
| UC-02 | Set Assignment Deadline | Lecturer | FR-02 |
| UC-03 | View Assignments | Student | FR-03 |
| UC-04 | Submit Assignment File | Student | FR-04 |
| UC-05 | Monitor Assignment Status and Deadline | Student | FR-05 |
| UC-06 | Record Grade and Feedback | Lecturer | FR-06, FR-07 |
| UC-07 | Manage Users | Administrator | FR-08 |
| UC-08 | Manage Courses and System Configuration | Administrator | FR-09, FR-10 |

## UC-01 — Create Assignment

- Goal: Allow Lecturer to create an assignment record.
- Primary actor: Lecturer
- Related FR: FR-01
- Related user story: US-01
- Preconditions:
  - Lecturer is authorized to perform Lecturer activities.
  - Assignment information is available.
- Trigger: Lecturer chooses to create an assignment record.
- Main flow:
  1. Lecturer enters assignment information.
  2. Lecturer submits the assignment record.
  3. The system stores the assignment record.
  4. The system makes the stored assignment record available for verification.
- Alternative/failure flow:
  - `OPEN QUESTION`: Required assignment fields are not yet defined, so field-level validation rules must be confirmed before implementation.
- Postcondition:
  - Assignment record is stored.

## UC-02 — Set Assignment Deadline

- Goal: Allow Lecturer to set a deadline for an assignment.
- Primary actor: Lecturer
- Related FR: FR-02
- Related business rule: BR-02
- Related user story: US-02
- Preconditions:
  - Lecturer is authorized to perform Lecturer activities.
  - An assignment record exists.
- Trigger: Lecturer chooses to set a deadline for an assignment.
- Main flow:
  1. Lecturer selects an assignment record.
  2. Lecturer enters a deadline value.
  3. Lecturer saves the deadline.
  4. The system stores the deadline associated with the selected assignment.
- Alternative/failure flow:
  - If no assignment record exists, the deadline cannot be associated with an assignment.
  - `OPEN QUESTION`: Rules for changing a published deadline are not yet defined.
- Postcondition:
  - Deadline is stored and associated with the assignment record.

## UC-03 — View Assignments

- Goal: Allow Student to view assignment records available to that Student.
- Primary actor: Student
- Related FR: FR-03
- Related user story: US-03
- Preconditions:
  - Student is authorized to perform Student activities.
  - Assignment records may or may not be available to the Student.
- Trigger: Student opens the available assignments view.
- Main flow:
  1. Student requests available assignment records.
  2. The system retrieves assignment records available to that Student.
  3. The system displays the assignment records.
- Alternative/failure flow:
  - If no assignment records are available, the system displays an empty assignment state.
- Postcondition:
  - Student can see the available assignment records or an empty assignment state.

## UC-04 — Submit Assignment File

- Goal: Allow Student to submit a file for an assignment.
- Primary actor: Student
- Related FR: FR-04
- Related NFR: NFR-03
- Related user story: US-04
- Preconditions:
  - Student is authorized to perform Student activities.
  - An assignment record is available to the Student.
  - Student has a file to submit.
- Trigger: Student submits a file for an assignment.
- Main flow:
  1. Student selects an assignment.
  2. Student provides a file for submission.
  3. Student submits the file.
  4. The system records the submission associated with the Student and assignment.
  5. The system preserves the recorded Student-assignment association for verification.
- Alternative/failure flow:
  - `OPEN QUESTION`: Allowed file formats and size limits are not yet defined.
  - `OPEN QUESTION`: Late submission and resubmission rules are not yet defined.
- Postcondition:
  - Submission record is stored and linked to the Student and assignment.

## UC-05 — Monitor Assignment Status and Deadline

- Goal: Allow Student to view recorded assignment status and deadline.
- Primary actor: Student
- Related FR: FR-05
- Related user story: US-05
- Preconditions:
  - Student is authorized to perform Student activities.
  - Assignment status or deadline data exists for the selected assignment.
- Trigger: Student opens assignment status or deadline information.
- Main flow:
  1. Student selects an assignment.
  2. The system retrieves the recorded status for the assignment.
  3. The system retrieves the recorded deadline for the assignment.
  4. The system displays the recorded status and deadline to Student.
- Alternative/failure flow:
  - `OPEN QUESTION`: Exact status values are not yet defined.
  - If no deadline has been recorded, deadline display behavior requires confirmation.
- Postcondition:
  - Student can view the recorded status and deadline information available for the assignment.

## UC-06 — Record Grade and Feedback

- Goal: Allow Lecturer to record grade and feedback for a Student submission.
- Primary actor: Lecturer
- Related FR: FR-06, FR-07
- Related NFR: NFR-04
- Related user story: US-06
- Preconditions:
  - Lecturer is authorized to perform Lecturer activities.
  - A Student submission exists.
- Trigger: Lecturer reviews a Student submission and records evaluation information.
- Main flow:
  1. Lecturer selects a Student submission.
  2. Lecturer records a grade for the submission.
  3. Lecturer records feedback for the submission.
  4. The system stores the grade linked to the selected submission.
  5. The system stores the feedback linked to the selected submission.
- Alternative/failure flow:
  - `OPEN QUESTION`: Grade format or grading scale is not yet defined.
  - `OPEN QUESTION`: When Student can view grade and feedback is not yet defined.
- Postcondition:
  - Grade and feedback records are stored and linked to the correct Student submission.

## UC-07 — Manage Users

- Goal: Allow Administrator to manage user records.
- Primary actor: Administrator
- Related FR: FR-08
- Related business rule: BR-01
- Related NFR: NFR-02
- Related user story: US-07
- Preconditions:
  - Administrator is authorized to perform Administrator activities.
  - User information is available.
- Trigger: Administrator performs user management.
- Main flow:
  1. Administrator enters or updates user information.
  2. Administrator saves the user record.
  3. The system stores the user record.
  4. The system preserves the stored values for verification.
- Alternative/failure flow:
  - `ASSUMPTION`: Create, update, and deactivate are the user operations used for the current draft.
  - `OPEN QUESTION`: Exact allowed user operations are not yet confirmed.
- Postcondition:
  - User record is stored or updated according to the selected Administrator operation.

## UC-08 — Manage Courses and System Configuration

- Goal: Allow Administrator to manage course records and documented system configuration values.
- Primary actor: Administrator
- Related FR: FR-09, FR-10
- Related user story: US-08
- Preconditions:
  - Administrator is authorized to perform Administrator activities.
  - Course information or documented configuration value is available.
- Trigger: Administrator performs course management or system configuration management.
- Main flow:
  1. Administrator enters or updates course information.
  2. The system stores the course record.
  3. Administrator selects a documented configuration value.
  4. Administrator updates the configuration value.
  5. The system stores the updated configuration value.
- Alternative/failure flow:
  - `ASSUMPTION`: Create, update, and deactivate are the course operations used for the current draft.
  - `OPEN QUESTION`: Exact course data and configuration categories are not yet confirmed.
- Postcondition:
  - Course record or documented configuration value is stored according to the selected Administrator operation.

## Open Questions for Diagram Stage

- `OPEN QUESTION`: Whether grade recording and feedback recording should be drawn as separate use cases or one combined use case.
- `OPEN QUESTION`: Whether course management and system configuration should be drawn as separate use cases or one combined administrative use case.
- `OPEN QUESTION`: Whether reporting should appear in the use case diagram after reporting scope is clarified.
