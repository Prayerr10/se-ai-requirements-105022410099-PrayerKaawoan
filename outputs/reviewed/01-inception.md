# Project Inception and Stakeholder Discovery

## Evidence Summary

| Source | Evidence Used | Label |
|---|---|---|
| `CASE.md` | Student Task Management System is a campus application for assignments, submissions, grading, deadlines, and reporting. | FACT |
| `CASE.md` | Lecturer, Student, and Administrator are directly named stakeholders. | FACT |
| `CASE.md` | The system must consider usability, security, performance, reliability, and data integrity. | FACT |
| `inputs/stakeholder-notes.md` | Stakeholder interests include several unconfirmed interpretations. | ASSUMPTION |
| `inputs/assumptions.md` | Additional information outside the case must remain labeled ASSUMPTION. | CONSTRAINT |

## Case Context

`FACT`: Student Task Management System is a campus application used by Lecturer, Student, and Administrator to support assignment-related activities.

`FACT`: The official case covers coursework assignment management, submission, grading, deadline handling, feedback, reporting, user management, course management, and system configuration.

`CONSTRAINT`: The assignment does not provide detailed academic policy, technology, workflow, integration, workload, platform, budget, or schedule information.

## Initial Objectives

- `FACT`: Support Lecturer in creating assignments, setting deadlines, grading submissions, and giving feedback.
- `FACT`: Support Student in viewing assignments, submitting files, and monitoring status and deadlines.
- `FACT`: Support Administrator in managing users, courses, and system configuration.
- `FACT`: Consider usability, security, performance, reliability, and data integrity during requirements work.

## Stakeholder Analysis

### Lecturer

#### Needs

- `FACT`: Create assignments.
- `FACT`: Set deadlines.
- `FACT`: Provide grades.
- `FACT`: Provide feedback.

#### Interests

- `ASSUMPTION`: Keep assignment and grading work manageable.
- `ASSUMPTION`: Protect grade and feedback data from unauthorized changes.
- `ASSUMPTION`: Use organized submission information when grading.

#### Information Gaps

- `OPEN QUESTION`: Can a Lecturer revise a deadline after publishing an assignment?
- `OPEN QUESTION`: What information must an assignment contain?
- `OPEN QUESTION`: When are grades and feedback visible to Student?

### Student

#### Needs

- `FACT`: View assignments.
- `FACT`: Submit files.
- `FACT`: Monitor assignment status.
- `FACT`: Monitor deadlines.

#### Interests

- `ASSUMPTION`: Receive clear confirmation that a submission was recorded.
- `ASSUMPTION`: Understand task and deadline information clearly.
- `ASSUMPTION`: Protect submitted files and academic information from unauthorized access.

#### Information Gaps

- `OPEN QUESTION`: Which submission and assignment statuses must Student see?
- `OPEN QUESTION`: Are late submissions or resubmissions allowed?
- `OPEN QUESTION`: What file formats and size limits are allowed?

### Administrator

#### Needs

- `FACT`: Manage users.
- `FACT`: Manage courses.
- `FACT`: Manage system configuration.

#### Interests

- `ASSUMPTION`: Keep user and course data accurate.
- `ASSUMPTION`: Control configuration changes.
- `ASSUMPTION`: Support system reliability and data integrity.

#### Information Gaps

- `OPEN QUESTION`: Which user and course operations are allowed?
- `OPEN QUESTION`: Which configuration categories are in Administrator scope?
- `OPEN QUESTION`: Does Administrator manage reporting access or report definitions?

## Scope Boundaries

### In Scope

- `FACT`: Assignment management.
- `FACT`: File submission.
- `FACT`: Grading and feedback.
- `FACT`: Status and deadline monitoring.
- `FACT`: User, course, and configuration management.
- `FACT`: Reporting as a case area, with details unresolved.

### Out of Scope

- No item is confirmed out of scope by the official case.

### Unresolved

- `OPEN QUESTION`: Whether integration with other campus systems is in scope.
- `OPEN QUESTION`: Reporting audience, report content, and report frequency.
- `OPEN QUESTION`: Measurable targets for usability, security, performance, reliability, and data integrity.

## FACT

- `FACT-01`: The project is Student Task Management System.
- `FACT-02`: The system is for a campus context.
- `FACT-03`: The directly named stakeholders are Lecturer, Student, and Administrator.
- `FACT-04`: Lecturer activities include creating assignments, setting deadlines, giving grades, and giving feedback.
- `FACT-05`: Student activities include viewing assignments, submitting files, and monitoring status and deadlines.
- `FACT-06`: Administrator activities include managing users, courses, and configuration.
- `FACT-07`: The system must consider usability, security, performance, reliability, and data integrity.

## ASSUMPTION

- `ASSUMPTION-01`: Lecturer wants assignment and grading workflows to avoid unnecessary administrative effort.
- `ASSUMPTION-02`: Student wants submission confirmation.
- `ASSUMPTION-03`: Administrator wants controlled configuration changes.
- `ASSUMPTION-04`: Role-based access is needed to protect role-specific activities.

## CONSTRAINT

- `CONSTRAINT-01`: Use only the official case and prepared inputs as factual evidence.
- `CONSTRAINT-02`: Treat unconfirmed elaboration as `ASSUMPTION`.
- `CONSTRAINT-03`: Use Lecturer, Student, and Administrator consistently.
- `CONSTRAINT-04`: AI draft output requires human review before becoming baseline.

## OPEN QUESTION

| ID | Question | Urgency | Rationale | Source Gap |
|---|---|---|---|---|
| OPEN-01 | What is the current process problem to solve first? | High | Business problem clarity affects scope. | CASE.md provides broad context only. |
| OPEN-02 | What rules govern assignment publication and deadline changes? | High | Affects Lecturer and Student workflows. | Policy not provided. |
| OPEN-03 | Are late submissions or resubmissions allowed? | High | Affects submission and status handling. | Policy not provided. |
| OPEN-04 | What file formats and size limits are allowed? | Medium | Affects submission handling. | File rules not provided. |
| OPEN-05 | When can Student view grades and feedback? | Medium | Affects grading and feedback visibility. | Visibility policy not provided. |
| OPEN-06 | What reports are required? | Medium | Reporting is mentioned but not detailed. | Report audience/content not provided. |
| OPEN-07 | What are measurable quality targets? | High | NFRs require testable thresholds. | Quality concerns are named without measures. |

## Contradictions and Risks

- No direct contradiction was found among the prepared inputs.
- `OPEN QUESTION`: Reporting is in the official case but has no defined stakeholder, content, or frequency.
- `OPEN QUESTION`: Quality concerns are official facts but lack measurable targets.

## Handoff to Elicitation

- Ask Lecturer about assignment publication, deadline modification, grading, feedback, and visibility policies.
- Ask Student about submission confirmation, allowed files, status terms, deadlines, late submission, and resubmission.
- Ask Administrator about user/course/configuration operations and reporting authority.
- Preserve every unresolved policy or quality target as `OPEN QUESTION` until confirmed.
