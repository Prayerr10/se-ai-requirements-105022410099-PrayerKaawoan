# Inception Skill Examples

## Example Invocation

```text
Use skills/01-inception/SKILL.md to analyze the Student Task Management System.
Read CASE.md, inputs/stakeholder-notes.md, and inputs/assumptions.md.
Create only a structured inception draft for human review. Use Lecturer, Student,
and Administrator consistently; preserve FACT, ASSUMPTION, CONSTRAINT, and
OPEN QUESTION labels; do not create requirements or downstream artefacts.
```

## Example Output Excerpt

```markdown
# Project Inception and Stakeholder Discovery

## Evidence Summary
| Source | Evidence Used | Label |
|---|---|---|
| CASE.md | The system is intended for a campus context. | FACT |
| inputs/stakeholder-notes.md | Student wants confirmation that a submission was recorded. | ASSUMPTION |

## Initial Objectives
- `FACT`: Support management of coursework assignments, submissions, grading, deadlines, and reporting.

## Stakeholder Analysis

### Student

#### Needs
- `FACT`: View assignments, submit files, and monitor status and deadlines.

#### Interests
- `ASSUMPTION`: Receive clear confirmation that a submitted file was recorded; confirm during elicitation.

#### Information Gaps
- `OPEN QUESTION`: Which submission statuses must Student see?

### Administrator

#### Needs
- `FACT`: Manage users, courses, and system configuration.

#### Information Gaps
- `OPEN QUESTION`: Which configurations are controlled by Administrator?

## Scope Boundaries

### Unresolved
- `OPEN QUESTION`: Whether another campus system must be considered.

## CONSTRAINT
- `CONSTRAINT`: Information outside the official case cannot be treated as fact.

## Handoff to Elicitation
- Investigate submission-status terminology with Student.
- Clarify configuration authority with Administrator.
```

This excerpt illustrates the required classification and handoff. It is not a final inception output and does not establish requirements, user stories, priorities, diagrams, traceability, or change decisions.
