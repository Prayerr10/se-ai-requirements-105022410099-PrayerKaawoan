# Raw AI Output — Skill 1: Project Inception and Stakeholder Discovery

## Invocation

Read `CASE.md`, `inputs/stakeholder-notes.md`, `inputs/assumptions.md`, and `skills/01-inception/SKILL.md`. Execute the Project Inception and Stakeholder Discovery skill exactly as written. Save the first output as raw AI output. Use Lecturer, Student, Administrator, FACT, ASSUMPTION, CONSTRAINT, and OPEN QUESTION consistently. Do not create requirements, user stories, diagrams, traceability, prioritization, validation, or change requests.

## Evidence Summary

| Source | Evidence Used | Label |
|---|---|---|
| CASE.md | Student Task Management System is a campus application for assignments, submissions, grading, deadlines, and reporting. | FACT |
| CASE.md | Lecturer, Student, and Administrator are directly named stakeholders. | FACT |
| inputs/stakeholder-notes.md | Lecturer, Student, and Administrator have needs and interests separated. | FACT / ASSUMPTION |
| inputs/assumptions.md | Information outside the official case must be labeled ASSUMPTION. | CONSTRAINT |

## Case Context

- `FACT`: Student Task Management System supports campus task-management activities.
- `FACT`: The named stakeholders are Lecturer, Student, and Administrator.
- `FACT`: The system context includes assignments, submissions, grading, deadlines, and reporting.

## Initial Objectives

- `FACT`: Support Lecturer activity around assignments, deadlines, grades, and feedback.
- `FACT`: Support Student activity around assignment viewing, file submission, status monitoring, and deadline monitoring.
- `FACT`: Support Administrator activity around users, courses, and system configuration.
- `FACT`: Consider usability, security, performance, reliability, and data integrity.

## Stakeholder Analysis

### Lecturer

#### Needs

- `FACT`: Create assignments.
- `FACT`: Set deadlines.
- `FACT`: Provide grades and feedback.

#### Interests

- `ASSUMPTION`: Keep assignment and grading work manageable.
- `ASSUMPTION`: Protect grade and feedback data from unauthorized changes.

#### Information Gaps

- `OPEN QUESTION`: Can a Lecturer revise a deadline after publishing an assignment?
- `OPEN QUESTION`: When can a Student see grades and feedback?

### Student

#### Needs

- `FACT`: View assignments.
- `FACT`: Submit files.
- `FACT`: Monitor status and deadlines.

#### Interests

- `ASSUMPTION`: Receive clear confirmation after submitting a file.
- `ASSUMPTION`: Understand deadline status clearly.

#### Information Gaps

- `OPEN QUESTION`: What submission statuses are required?
- `OPEN QUESTION`: Is resubmission allowed?

### Administrator

#### Needs

- `FACT`: Manage users.
- `FACT`: Manage courses.
- `FACT`: Manage system configuration.

#### Interests

- `ASSUMPTION`: Maintain accurate user and course data.
- `ASSUMPTION`: Control configuration changes.

#### Information Gaps

- `OPEN QUESTION`: Which configuration categories are in Administrator scope?
- `OPEN QUESTION`: Does Administrator access reporting data?

## Scope Boundaries

### In Scope

- `FACT`: Assignment management.
- `FACT`: Submission management.
- `FACT`: Grading and feedback.
- `FACT`: Deadline and status monitoring.
- `FACT`: User, course, and configuration management.

### Out of Scope

- Campus system integrations.

### Unresolved

- `OPEN QUESTION`: Specific reporting audience and format.
- `OPEN QUESTION`: Technical platform and integrations.
- `OPEN QUESTION`: Quality targets for usability, security, performance, reliability, and data integrity.

## Contradictions and Risks

- `OPEN QUESTION`: Deadline and resubmission policies are not defined.
- `OPEN QUESTION`: Reporting is named in the case but not tied to a stakeholder.

## Handoff to Elicitation

- Ask Lecturer about assignment publication, deadline changes, grading, and feedback visibility.
- Ask Student about status terminology, file submission confirmation, and resubmission expectations.
- Ask Administrator about user/course/configuration scope and reporting authority.
