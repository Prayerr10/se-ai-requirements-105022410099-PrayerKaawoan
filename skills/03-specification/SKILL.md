---
name: requirements-elaboration-and-specification
description: Convert reviewed elicitation findings into structured, testable functional requirements, non-functional requirements, business rules, user stories, and acceptance criteria. Use after Requirements Elicitation and before prioritization.
---

# Requirements Elaboration and Specification

## Purpose

Transform validated elicitation findings into a consistent specification without inventing facts. Produce draft content for `outputs/reviewed/03-requirements.md` and `outputs/reviewed/04-user-stories.md` for human review in the next stage.

## When to Use

Use after Skill 2 has produced and a human has reviewed `outputs/reviewed/02-elicitation.md`. Run again whenever elicitation findings change or specification quality checks fail. Do not use this skill to prioritize, validate a baseline, create a diagram, build a traceability matrix, or process a change request.

## Inputs

- Required: `outputs/reviewed/02-elicitation.md`.
- Optional supporting context: `CASE.md`, `inputs/stakeholder-notes.md`, `inputs/interview-answers.md`, and `inputs/assumptions.md`.
- Any human-approved clarifications that identify their source and status as `FACT`, `ASSUMPTION`, `CONSTRAINT`, or `OPEN QUESTION`.

## Required Context

Read the complete reviewed Skill 2 output before drafting. Consult upstream files only to verify wording, source, stakeholder, or label; never use an upstream statement to override the reviewed elicitation result silently. Preserve the stakeholder names `Lecturer`, `Student`, and `Administrator`. Treat unresolved `OPEN QUESTION` entries as gaps, not requirements.

## Workflow

1. Load all supplied inputs and record missing, contradictory, or unresolved information.
2. Classify every usable statement as `FACT`, `ASSUMPTION`, or `CONSTRAINT`; keep `OPEN QUESTION` entries separate.
3. Extract candidate behavior, quality attributes, and governing rules. Retain the source and relevant stakeholder for each candidate.
4. Draft functional requirements with unique sequential IDs `FR-01`, `FR-02`, and so on. State one observable system behavior per requirement.
5. Draft non-functional requirements with unique sequential IDs `NFR-01`, `NFR-02`, and so on. Include a measurable condition, threshold, operating context, and verification method.
6. Draft business rules with unique sequential IDs `BR-01`, `BR-02`, and so on. Separate organizational policy from system behavior.
7. Draft user stories with unique sequential IDs `US-01`, `US-02`, and so on, using `As a <stakeholder>, I want <capability>, so that <value>.`
8. Add at least two independently testable acceptance criteria to every user story, using IDs scoped to the story such as `AC-US01-01`.
9. Map each story and acceptance criterion to supporting requirement IDs without creating a final traceability matrix.
10. Check coverage against the assignment minimums: at least 8 FR, 4 measurable NFR, 2 business rules, 6 user stories, and 2 acceptance criteria per story. Never fabricate content merely to reach a minimum; report a shortfall as an `OPEN QUESTION` or failure.
11. Run all quality checks. If a check fails, revise the draft and repeat the workflow; if evidence is insufficient or contradictory, stop and request clarification.

## Output Format

Return two clearly separated Markdown artifacts for later human review; do not write the files unless explicitly instructed.

For `outputs/reviewed/03-requirements.md`, use:

```markdown
Title: Requirements Specification
### Source Summary
### Functional Requirements
### FR-01 — <short name>
- Statement:
- Stakeholder:
- Source:
- Status: FACT | ASSUMPTION | CONSTRAINT
### Non-Functional Requirements
### NFR-01 — <short name>
- Statement:
- Measure and threshold:
- Operating context:
- Verification method:
- Source:
- Status: FACT | ASSUMPTION | CONSTRAINT
### Business Rules
### BR-01 — <short name>
- Rule:
- Source:
- Status: FACT | ASSUMPTION | CONSTRAINT
### Open Questions
```

For `outputs/reviewed/04-user-stories.md`, use:

```markdown
Title: User Stories
### US-01 — <short name>
- Story: As a <Lecturer | Student | Administrator>, I want <capability>, so that <value>.
- Supports: FR-xx[, NFR-xx]
- Source:
- Status: FACT | ASSUMPTION | CONSTRAINT
#### Acceptance Criteria
- AC-US01-01: Given <context>, when <event>, then <observable result>.
- AC-US01-02: Given <context>, when <event>, then <observable result>.
### Open Questions
```

## Rules

- Use only evidence in the supplied context; label every unsupported proposal `ASSUMPTION`.
- Never convert an `OPEN QUESTION` into a requirement, rule, story, or acceptance criterion.
- Preserve `CONSTRAINT` statements and distinguish them from required system behavior.
- Use only `Lecturer`, `Student`, and `Administrator` for known stakeholder roles unless an additional role is explicitly sourced.
- Keep each requirement atomic, necessary, unambiguous, feasible, testable, and source-linked.
- Avoid subjective terms such as “fast,” “easy,” “secure,” or “user-friendly” unless paired with a measurable criterion.
- Write NFRs with explicit measures and verification methods.
- Keep business rules separate from FRs and NFRs.
- Do not assign MoSCoW priorities; Skill 4 owns prioritization.
- Do not create final requirements, raw/reviewed files, diagrams, traceability matrices, validation reports, or change requests while authoring or testing this skill.

## Quality Checks

- Confirm IDs are unique, sequential, and use the correct prefix.
- Confirm every statement has a source, relevant stakeholder where applicable, and status label.
- Confirm all FRs describe observable behavior and all NFRs contain a measurable threshold and verification method.
- Confirm every user story expresses a stakeholder, capability, and value.
- Confirm every story has at least two testable acceptance criteria linked to requirement IDs.
- Confirm no `OPEN QUESTION` has been silently resolved and every unsupported statement is labeled `ASSUMPTION`.
- Confirm the specification has no contradictions, duplicates, undefined terms, or ambiguous qualifiers.
- Confirm assignment minimums are met through supported evidence or explicitly report the shortfall.
- Confirm the outputs contain no prioritization decisions or downstream artifacts.

## Failure Conditions

Stop and request clarification when `outputs/reviewed/02-elicitation.md` is missing, empty, unreviewed, or too incomplete to support testable statements; when sources conflict and no approved resolution exists; when a measurable NFR cannot be derived; or when meeting an assignment minimum would require invented facts. List the blocking item, affected artifact, available evidence, and the precise `OPEN QUESTION` to resolve. Do not guess.

## Example Invocation

Use this skill with `outputs/reviewed/02-elicitation.md` as the primary input. Consult `inputs/assumptions.md` only to preserve labels. Produce concise draft sections for the two specified reviewed outputs, keep unresolved items as `OPEN QUESTION`, and do not prioritize the requirements.

## Expected Output Example

```markdown
Artifact: outputs/reviewed/03-requirements.md

### FR-01 — Record a submission
- Statement: The system shall record a Student submission against the selected task.
- Stakeholder: Student
- Source: EL-02
- Status: FACT

### NFR-01 — Submission response time
- Statement: Under the stated test workload, the system shall confirm a submission within 3 seconds for at least 95% of attempts.
- Measure and threshold: Confirmation time <= 3 seconds for >= 95% of attempts
- Operating context: ASSUMPTION — test workload requires Lecturer confirmation
- Verification method: Performance test
- Source: EL-05
- Status: ASSUMPTION

Artifact: outputs/reviewed/04-user-stories.md

### US-01 — Submit task work
- Story: As a Student, I want to submit work for a task, so that my work can be recorded for review.
- Supports: FR-01
- Source: EL-02
- Status: FACT
#### Acceptance Criteria
- AC-US01-01: Given an identified Student and a selected task, when the Student submits work, then the system records the submission against that task.
- AC-US01-02: Given a recorded submission, when the Student views its status, then the system displays that submission as recorded.

### Open Questions
- OPEN QUESTION: What test workload should govern NFR-01?
```
