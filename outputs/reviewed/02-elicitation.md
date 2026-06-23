# Requirements Elicitation

## Input Sources

| Source ID | File | Location or Interview Item | Evidence Label |
|---|---|---|---|
| EL-SRC-01 | `outputs/reviewed/01-inception.md` | Stakeholder analysis, scope boundaries, handoff questions | FACT / ASSUMPTION / CONSTRAINT / OPEN QUESTION |
| EL-SRC-02 | `inputs/interview-answers.md` | Lecturer activities and outcomes | FACT / ASSUMPTION |
| EL-SRC-03 | `inputs/interview-answers.md` | Student activities and outcomes | FACT / ASSUMPTION |
| EL-SRC-04 | `inputs/interview-answers.md` | Administrator activities and outcomes | FACT / ASSUMPTION |
| EL-SRC-05 | `inputs/assumptions.md` | Registered facts, assumptions, constraints, and open questions | FACT / ASSUMPTION / CONSTRAINT / OPEN QUESTION |

## Elicitation Approach

| Technique | Target | Purpose | Rationale |
|---|---|---|---|
| Follow-up interview | Lecturer | Clarify assignment publication, deadline changes, grading, feedback, and visibility. | Lecturer policy decisions are unresolved. |
| Follow-up interview | Student | Clarify status terminology, file submission confirmation, accepted file constraints, and resubmission. | Student-facing submission details are unresolved. |
| Follow-up interview | Administrator | Clarify user, course, configuration, and reporting authority. | Administrator scope is only described broadly. |
| Document analysis | Administrator | Locate academic policies for deadlines, submissions, grades, and reports. | Policies should come from evidence, not AI inference. |

## Findings

| Finding ID | Stakeholder | Need or Observation | Explicit/Implicit | Evidence Label | Source ID | Confidence |
|---|---|---|---|---|---|---|
| EL-01 | Lecturer | Needs to create assignments. | Explicit | FACT | EL-SRC-02 | High |
| EL-02 | Lecturer | Needs to set assignment deadlines. | Explicit | FACT | EL-SRC-02 | High |
| EL-03 | Lecturer | Needs to provide grades and feedback. | Explicit | FACT | EL-SRC-02 | High |
| EL-04 | Student | Needs to view assignments. | Explicit | FACT | EL-SRC-03 | High |
| EL-05 | Student | Needs to submit files. | Explicit | FACT | EL-SRC-03 | High |
| EL-06 | Student | Needs to monitor assignment status and deadlines. | Explicit | FACT | EL-SRC-03 | High |
| EL-07 | Administrator | Needs to manage users. | Explicit | FACT | EL-SRC-04 | High |
| EL-08 | Administrator | Needs to manage courses. | Explicit | FACT | EL-SRC-04 | High |
| EL-09 | Administrator | Needs to manage system configuration. | Explicit | FACT | EL-SRC-04 | High |
| EL-10 | Lecturer | Wants assignment and grading work to avoid unnecessary administrative effort. | Implicit | ASSUMPTION | EL-SRC-02 | Medium |
| EL-11 | Student | Wants confirmation that a submitted file was recorded. | Implicit | ASSUMPTION | EL-SRC-03 | Medium |
| EL-12 | Administrator | Wants controlled and accurate user, course, and configuration management. | Implicit | ASSUMPTION | EL-SRC-04 | Medium |

## Conflicts and Dependencies

| Item ID | Related Finding IDs | Description | Status |
|---|---|---|---|
| EL-D-01 | EL-01, EL-02, EL-04, EL-06 | Student assignment and deadline visibility depends on assignment and deadline data created by Lecturer. | FACT |
| EL-D-02 | EL-03, EL-05 | Grading and feedback depend on Student submission existing first. | ASSUMPTION |
| EL-D-03 | EL-07, EL-08, EL-09 | User, course, and configuration management likely affect access control and operational setup. | ASSUMPTION |
| EL-D-04 | EL-02, EL-05, EL-06 | Deadline, late submission, and resubmission policies are unresolved and could conflict. | OPEN QUESTION |

## Information Gaps and Follow-up Questions

| Question ID | Target Stakeholder | Related Finding ID | Question | Technique | Status |
|---|---|---|---|---|---|
| EL-Q-01 | Lecturer | EL-01 | What information must be recorded when creating an assignment? | Follow-up interview | OPEN QUESTION |
| EL-Q-02 | Lecturer | EL-02 | Can a published assignment deadline be changed? | Follow-up interview | OPEN QUESTION |
| EL-Q-03 | Student | EL-05 | What file formats and size limits are allowed for submission? | Follow-up interview | OPEN QUESTION |
| EL-Q-04 | Student | EL-06 | Which status values should Student see? | Follow-up interview | OPEN QUESTION |
| EL-Q-05 | Lecturer | EL-03 | When are grades and feedback visible to Student? | Follow-up interview | OPEN QUESTION |
| EL-Q-06 | Administrator | EL-07 | What user operations are allowed: create, update, deactivate, delete, or assign roles? | Follow-up interview | OPEN QUESTION |
| EL-Q-07 | Administrator | EL-08 | What course data must be managed? | Follow-up interview | OPEN QUESTION |
| EL-Q-08 | Administrator | EL-09 | Which configuration categories are in scope? | Follow-up interview | OPEN QUESTION |
| EL-Q-09 | Administrator | EL-09 | What reports are required and who consumes them? | Follow-up interview | OPEN QUESTION |
| EL-Q-10 | Lecturer, Student, Administrator | EL-10, EL-11, EL-12 | What measurable targets should define usability, security, performance, reliability, and data integrity? | Workshop | OPEN QUESTION |

## Constraints

| Item ID | CONSTRAINT | Source ID |
|---|---|---|
| EL-C-01 | Only official case and prepared input files may be treated as factual evidence. | EL-SRC-05 |
| EL-C-02 | Additional interpretation must remain labeled ASSUMPTION until confirmed. | EL-SRC-05 |
| EL-C-03 | Lecturer, Student, and Administrator must be used consistently as stakeholder names. | EL-SRC-05 |

## Assumptions Requiring Validation

| Item ID | ASSUMPTION | Source ID | Validation Question |
|---|---|---|---|
| EL-A-01 | Lecturer wants to reduce unnecessary administrative effort. | EL-SRC-02 | Which assignment or grading steps currently create administrative effort? |
| EL-A-02 | Student wants explicit submission confirmation. | EL-SRC-03 | What confirmation information should Student see after submission? |
| EL-A-03 | Administrator wants controlled configuration changes. | EL-SRC-04 | What approval or audit expectations apply to configuration changes? |

## Elicitation Summary

- Confirmed findings: EL-01 through EL-09.
- Assumption findings requiring validation: EL-10 through EL-12.
- Unresolved `OPEN QUESTION` items: EL-Q-01 through EL-Q-10.
- Handoff notes for Skill 3: Build requirements only from confirmed findings or clearly labeled assumptions. Do not convert EL-Q items into final requirements without evidence.
