# Raw AI Output — Skill 2: Requirements Elicitation

## Invocation

Read `outputs/reviewed/01-inception.md`, `inputs/interview-answers.md`, `inputs/assumptions.md`, and `skills/02-elicitation/SKILL.md`. Execute Requirements Elicitation after Skill 1. Save the first output as raw AI output. Preserve FACT, ASSUMPTION, CONSTRAINT, and OPEN QUESTION labels. Do not write final requirements or user stories.

## Input Sources

| Source ID | File | Location or Interview Item | Evidence Label |
|---|---|---|---|
| EL-SRC-01 | outputs/reviewed/01-inception.md | Stakeholder analysis and handoff questions | FACT / ASSUMPTION / OPEN QUESTION |
| EL-SRC-02 | inputs/interview-answers.md | Lecturer activities and outcomes | FACT / ASSUMPTION |
| EL-SRC-03 | inputs/interview-answers.md | Student activities and outcomes | FACT / ASSUMPTION |
| EL-SRC-04 | inputs/interview-answers.md | Administrator activities and outcomes | FACT / ASSUMPTION |
| EL-SRC-05 | inputs/assumptions.md | Facts, assumptions, constraints, and open questions | FACT / ASSUMPTION / CONSTRAINT / OPEN QUESTION |

## Elicitation Approach

| Technique | Target | Purpose | Rationale |
|---|---|---|---|
| Follow-up interview | Lecturer | Clarify assignment publication, deadline changes, grading, and feedback visibility. | These policies are unresolved. |
| Follow-up interview | Student | Clarify status terminology, file submission confirmation, and resubmission expectations. | Student status and submission details are unresolved. |
| Follow-up interview | Administrator | Clarify users, courses, configuration scope, and reporting authority. | Administrator authority is only described broadly. |
| Document analysis | Administrator | Identify any academic policy governing deadlines and submissions. | Policy decisions should not be invented. |

## Findings

| Finding ID | Stakeholder | Need or Observation | Explicit/Implicit | Evidence Label | Source ID | Confidence |
|---|---|---|---|---|---|---|
| EL-01 | Lecturer | Needs to create assignments. | Explicit | FACT | EL-SRC-02 | High |
| EL-02 | Lecturer | Needs to set assignment deadlines. | Explicit | FACT | EL-SRC-02 | High |
| EL-03 | Lecturer | Needs to provide grades and feedback. | Explicit | FACT | EL-SRC-02 | High |
| EL-04 | Student | Needs to view assignments. | Explicit | FACT | EL-SRC-03 | High |
| EL-05 | Student | Needs to submit files. | Explicit | FACT | EL-SRC-03 | High |
| EL-06 | Student | Needs to monitor status and deadlines. | Explicit | FACT | EL-SRC-03 | High |
| EL-07 | Administrator | Needs to manage users. | Explicit | FACT | EL-SRC-04 | High |
| EL-08 | Administrator | Needs to manage courses. | Explicit | FACT | EL-SRC-04 | High |
| EL-09 | Administrator | Needs to manage system configuration. | Explicit | FACT | EL-SRC-04 | High |
| EL-10 | Student | May need deadline reminders. | Implicit | ASSUMPTION | EL-SRC-03 | Low |
| EL-11 | Administrator | May need reporting access. | Implicit | ASSUMPTION | EL-SRC-01 | Low |

## Conflicts and Dependencies

| Item ID | Related Finding IDs | Description | Status |
|---|---|---|---|
| EL-D-01 | EL-02, EL-06 | Student deadline monitoring depends on how Lecturer deadlines are created or changed. | OPEN QUESTION |
| EL-D-02 | EL-05, EL-06 | Submission status depends on submission recording and status terminology. | OPEN QUESTION |
| EL-D-03 | EL-07, EL-08, EL-09 | User, course, and configuration management may affect access to other activities. | ASSUMPTION |

## Information Gaps and Follow-up Questions

| Question ID | Target Stakeholder | Related Finding ID | Question | Technique | Status |
|---|---|---|---|---|---|
| EL-Q-01 | Lecturer | EL-02 | Can a published assignment deadline be changed? | Follow-up interview | OPEN QUESTION |
| EL-Q-02 | Student | EL-05 | What file formats and size limits apply to submissions? | Follow-up interview | OPEN QUESTION |
| EL-Q-03 | Student | EL-06 | What statuses should Student see? | Follow-up interview | OPEN QUESTION |
| EL-Q-04 | Lecturer | EL-03 | When are grades and feedback visible to Student? | Follow-up interview | OPEN QUESTION |
| EL-Q-05 | Administrator | EL-09 | Which configuration categories can Administrator manage? | Follow-up interview | OPEN QUESTION |
| EL-Q-06 | Administrator | EL-11 | What reports are required and who uses them? | Follow-up interview | OPEN QUESTION |

## Constraints

| Item ID | CONSTRAINT | Source ID |
|---|---|---|
| EL-C-01 | Use only the official case as factual project evidence. | EL-SRC-05 |
| EL-C-02 | Treat additional information as ASSUMPTION until confirmed. | EL-SRC-05 |

## Elicitation Summary

- Confirmed findings: EL-01 through EL-09.
- Unresolved OPEN QUESTION items: EL-Q-01 through EL-Q-06.
- Handoff notes for Skill 3: Use only confirmed findings as FACT. Treat EL-10 and EL-11 as ASSUMPTION unless validated.
