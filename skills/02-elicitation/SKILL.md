---
name: requirements-elicitation
description: Elicit and organize stakeholder needs, interview evidence, gaps, and follow-up questions after project inception. Use when preparing an evidence-based elicitation record before requirements specification.
---

# Requirements Elicitation

## Purpose

Produce a structured, evidence-based elicitation record for the Student Task Management System. Identify explicit needs, cautiously infer implicit needs, expose conflicts and gaps, and prepare focused follow-up questions without writing final requirements.

## When to Use

Use after Project Inception and Stakeholder Discovery has produced an inception record and before Requirements Elaboration and Specification begins. Run again whenever interview evidence or an inception decision changes.

## Inputs

- `outputs/reviewed/01-inception.md`: approved project problem, goals, scope, stakeholders, constraints, assumptions, and open questions from Skill 1.
- `inputs/interview-answers.md`: current interview answers from Lecturer, Student, and Administrator.

If either input has multiple versions, use only the version explicitly identified as current.

## Required Context

Read both required inputs completely before analysis. When available, use these supporting sources only to check provenance and terminology:

- `CASE.md`
- `inputs/stakeholder-notes.md`
- `inputs/assumptions.md`

Treat the official case and explicit stakeholder statements as `FACT`; retain all labels already assigned as `ASSUMPTION`, `CONSTRAINT`, or `OPEN QUESTION`. Do not silently promote an assumption or interview interpretation to fact.

## Workflow

1. Confirm that both required inputs exist, are readable, identify Lecturer, Student, and Administrator, and do not contain unresolved version conflicts.
2. Build a source register that assigns a stable source ID such as `EL-SRC-01` to each relevant interview answer or cited source passage.
3. Extract explicit stakeholder needs without rewriting their meaning. Assign stable finding IDs such as `EL-01` and record stakeholder, source ID, evidence label, and confidence.
4. Identify implicit needs only when supported by evidence. Label each inference `ASSUMPTION`, cite its source, state the reasoning, and create a validation question.
5. Group findings by stakeholder and activity while preserving each finding's source and label.
6. Detect duplicates, conflicts, missing detail, unclear terms, dependencies, and out-of-scope requests. Do not resolve conflicts without stakeholder evidence.
7. Select an appropriate elicitation technique for every gap: follow-up interview, document analysis, observation, workshop, or questionnaire. Explain briefly why it fits.
8. Draft neutral, non-leading follow-up questions addressed to Lecturer, Student, or Administrator. Each question must reference the finding or gap it can clarify.
9. Record unresolved items as `OPEN QUESTION` and known limitations as `CONSTRAINT`. Keep `FACT`, `ASSUMPTION`, `CONSTRAINT`, and `OPEN QUESTION` distinct.
10. Run all quality checks. If a failure condition applies, stop and request clarification; otherwise write the elicitation record in the required format.
11. On repeat runs, preserve unchanged IDs, update affected findings, and note which input evidence caused each change.

## Output Format

Prepare content for `outputs/reviewed/02-elicitation.md` using this structure; do not create or edit that file unless the caller explicitly requests execution of the skill:

```markdown
 # Requirements Elicitation

 ## Input Sources
| Source ID | File | Location or Interview Item | Evidence Label |

 ## Elicitation Approach
| Technique | Target | Purpose | Rationale |

 ## Findings
| Finding ID | Stakeholder | Need or Observation | Explicit/Implicit | Evidence Label | Source ID | Confidence |

 ## Conflicts and Dependencies
| Item ID | Related Finding IDs | Description | Status |

 ## Information Gaps and Follow-up Questions
| Question ID | Target Stakeholder | Related Finding ID | Question | Technique | Status |

 ## Constraints
| Item ID | CONSTRAINT | Source ID |

 ## Assumptions Requiring Validation
| Item ID | ASSUMPTION | Source ID | Validation Question |

 ## Elicitation Summary
- Confirmed findings:
- Unresolved OPEN QUESTION items:
- Handoff notes for Skill 3:
```

Do not include functional requirements, non-functional requirements, user stories, acceptance criteria, prioritization, diagrams, traceability matrices, or change requests.

## Rules

- Use Lecturer, Student, and Administrator exactly and consistently.
- Preserve the labels `FACT`, `ASSUMPTION`, `CONSTRAINT`, and `OPEN QUESTION` in uppercase.
- Never invent stakeholder statements, policies, workflows, quantities, thresholds, or decisions.
- Label every unsupported but useful inference as `ASSUMPTION` and pair it with a validation question.
- Cite a source ID for every finding, conflict, constraint, and assumption.
- Separate stakeholder needs from proposed solutions; record unsolicited solution ideas as observations, not approved scope.
- Keep questions neutral, singular, answerable, and linked to a specific gap.
- Do not convert findings into final requirements or assign requirement IDs.
- Do not resolve contradictory evidence by guessing; record the conflict as an `OPEN QUESTION`.
- Preserve stable IDs across repeated runs when the underlying item is unchanged.

## Quality Checks

- Both required inputs were read and listed in the source register.
- Lecturer, Student, and Administrator are each represented, or their missing evidence is an `OPEN QUESTION`.
- Every finding is explicit or implicit, has a stakeholder, evidence label, source ID, and confidence.
- Every implicit finding is labeled `ASSUMPTION` and has a validation question.
- Conflicting statements, unclear terms, and missing decision details are visible rather than silently reconciled.
- Follow-up questions are non-leading, ask one issue at a time, and identify the intended stakeholder.
- All findings can be handed to Skill 3 without being mistaken for approved requirements.
- The output contains none of the prohibited downstream artefacts.

## Failure Conditions

Stop and request clarification without producing a completed elicitation record when:

- `outputs/reviewed/01-inception.md` or `inputs/interview-answers.md` is missing, unreadable, or empty.
- The active version of either required input cannot be identified.
- Stakeholder names or project scope irreconcilably contradict the inception record.
- Evidence cannot be mapped to a source or distinguished from generated content.
- A requested conclusion would require inventing an unlabelled fact or resolving a conflict without stakeholder confirmation.

Report the blocking condition, affected source or finding, and the exact clarification needed.

## Example Invocation

```text
Use the Requirements Elicitation skill. Read outputs/reviewed/01-inception.md and inputs/interview-answers.md, with CASE.md and inputs/assumptions.md as supporting context. Prepare the structured elicitation record for outputs/reviewed/02-elicitation.md. Preserve evidence labels, expose gaps, and do not generate final requirements.
```

## Expected Output Example

```markdown
 # Requirements Elicitation

 ## Input Sources
| Source ID | File | Location or Interview Item | Evidence Label |
|---|---|---|---|
| EL-SRC-01 | inputs/interview-answers.md | Lecturer answer about assignment creation and deadlines | FACT |

 ## Findings
| Finding ID | Stakeholder | Need or Observation | Explicit/Implicit | Evidence Label | Source ID | Confidence |
|---|---|---|---|---|---|---|
| EL-01 | Lecturer | Needs to create assignments and set deadlines. | Explicit | FACT | EL-SRC-01 | High |
| EL-02 | Student | May need deadline reminders. | Implicit | ASSUMPTION | EL-SRC-01 | Low |

 ## Information Gaps and Follow-up Questions
| Question ID | Target Stakeholder | Related Finding ID | Question | Technique | Status |
|---|---|---|---|---|---|
| EL-Q-01 | Student | EL-02 | Which deadline notifications, if any, would help you monitor assignments? | Follow-up interview | OPEN QUESTION |

 ## Elicitation Summary
- Confirmed findings: EL-01.
- Unresolved OPEN QUESTION items: EL-Q-01.
- Handoff notes for Skill 3: Treat EL-02 as unvalidated; do not specify it as a requirement.
```
