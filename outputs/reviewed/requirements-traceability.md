# Requirements Traceability Matrix

## Purpose

This matrix traces each functional requirement for the Student Task Management System from stakeholder evidence through elicitation, user stories, acceptance criteria, prioritization, use cases, and validation evidence.

## Source Documents

- `CASE.md`
- `outputs/reviewed/01-inception.md`
- `outputs/reviewed/02-elicitation.md`
- `outputs/reviewed/03-requirements.md`
- `outputs/reviewed/04-user-stories.md`
- `outputs/reviewed/05-prioritization.md`
- `outputs/reviewed/06-use-case.md`
- `outputs/reviewed/07-validation.md`
- `outputs/reviewed/08-change-request.md`

## Traceability Matrix

| FR ID | Functional Requirement Summary | Stakeholder | Elicitation Source | User Story | Acceptance Criteria | Priority | Use Case | Validation Reference | Notes |
| ----- | ------------------------------ | ----------- | ------------------ | ---------- | ------------------- | -------- | -------- | -------------------- | ----- |
| FR-01 | Create assignment record | Lecturer | EL-01 | US-01 | AC-US01-01; AC-US01-02 | Must | UC-01 | `07-validation.md` — FR-01 | `OPEN QUESTION`: required assignment fields are not defined. |
| FR-02 | Set assignment deadline | Lecturer | EL-02; EL-06; EL-D-01 | US-02; US-05 | AC-US02-01; AC-US02-02; AC-US05-02 | Must | UC-02 | Not selected for detailed validation in `07-validation.md` | `OPEN QUESTION`: published deadline change policy is not defined. |
| FR-03 | View assignments | Student | EL-04 | US-03 | AC-US03-01; AC-US03-02 | Must | UC-03 | Not selected for detailed validation in `07-validation.md` | No traceability gap. |
| FR-04 | Submit assignment file | Student | EL-05 | US-04 | AC-US04-01; AC-US04-02 | Must | UC-04 | `07-validation.md` — FR-04 | `OPEN QUESTION`: file formats, size limits, late submission, and resubmission policy are not defined. Also affected by change request in `08-change-request.md`. |
| FR-05 | Monitor assignment status and deadline | Student | EL-06; EL-D-04 | US-05 | AC-US05-01; AC-US05-02 | Must | UC-05 | Not selected for detailed validation in `07-validation.md` | `OPEN QUESTION`: exact status values are not defined. Also affected by change request in `08-change-request.md`. |
| FR-06 | Record grade for Student submission | Lecturer | EL-03; EL-D-02 | US-06 | AC-US06-01 | Should | UC-06 | Not selected for detailed validation in `07-validation.md` | `OPEN QUESTION`: grading scale or grade format is not defined. |
| FR-07 | Record feedback for Student submission | Lecturer | EL-03; EL-D-02 | US-06 | AC-US06-02 | Should | UC-06 | `07-validation.md` — FR-07 | `OPEN QUESTION`: feedback visibility timing is not defined. |
| FR-08 | Manage user records | Administrator | EL-07; EL-Q-06 | US-07 | AC-US07-01; AC-US07-02 | Must | UC-07 | `07-validation.md` — FR-08 | `ASSUMPTION`: create, update, or deactivate are current draft operations. `OPEN QUESTION`: exact allowed user operations are not confirmed. |
| FR-09 | Manage course records | Administrator | EL-08; EL-Q-07 | US-08 | AC-US08-01 | Must | UC-08 | Not selected for detailed validation in `07-validation.md` | `ASSUMPTION`: create, update, or deactivate are current draft operations. `OPEN QUESTION`: exact course data is not confirmed. |
| FR-10 | Manage documented system configuration values | Administrator | EL-09; EL-Q-08 | US-08 | AC-US08-02 | Should | UC-08 | Not selected for detailed validation in `07-validation.md` | `ASSUMPTION`: editable configuration values exist. `OPEN QUESTION`: exact configuration categories are not confirmed. |

## Traceability Audit

| Audit Item | Count | Result |
|---|---:|---|
| FR mapped | 10 / 10 | PASS |
| FR with stakeholder | 10 / 10 | PASS |
| FR with elicitation source | 10 / 10 | PASS |
| FR with user story | 10 / 10 | PASS |
| FR with acceptance criteria | 10 / 10 | PASS |
| FR with priority | 10 / 10 | PASS |
| FR with use case | 10 / 10 | PASS |
| FR with detailed validation reference where selected | 4 / 4 selected FR | PASS |

### Gap Traceability

- No mandatory traceability gap remains for stakeholder, elicitation source, user story, acceptance criteria, priority, or use case.
- `OPEN QUESTION`: FR-01, FR-02, FR-04, FR-05, FR-06, FR-07, FR-08, FR-09, and FR-10 still contain unresolved policy or detail questions.
- `ASSUMPTION`: FR-08, FR-09, and FR-10 include administrative operation details that require stakeholder confirmation.

### Gap Decisions

- Keep unresolved details as `OPEN QUESTION` instead of inventing policy.
- Keep unconfirmed administrative operations as `ASSUMPTION`.
- Do not modify functional requirement wording only to simplify traceability.
- Use `07-validation.md` references only for requirements that were selected for detailed validation.
