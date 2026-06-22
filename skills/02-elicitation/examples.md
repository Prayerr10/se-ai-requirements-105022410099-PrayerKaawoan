# Requirements Elicitation Examples

## Example Invocation

```text
Use skills/02-elicitation/SKILL.md. Read outputs/reviewed/01-inception.md and inputs/interview-answers.md. Use CASE.md only to verify official case facts. Prepare content for outputs/reviewed/02-elicitation.md, keeping FACT, ASSUMPTION, CONSTRAINT, and OPEN QUESTION distinct. Identify needs and follow-up questions for Lecturer, Student, and Administrator without producing final requirements.
```

## Example Output

```markdown
# Requirements Elicitation

## Input Sources
| Source ID | File | Location or Interview Item | Evidence Label |
|---|---|---|---|
| EL-SRC-01 | inputs/interview-answers.md | Student answer about viewing tasks and monitoring deadlines | FACT |
| EL-SRC-02 | inputs/interview-answers.md | Administrator answer about system configuration | FACT |

## Elicitation Approach
| Technique | Target | Purpose | Rationale |
|---|---|---|---|
| Follow-up interview | Student | Clarify how deadline status is interpreted | The existing answer identifies a need but not the relevant status details. |
| Document analysis | Administrator | Identify existing configuration rules | Existing documentation may establish rules without inventing them. |

## Findings
| Finding ID | Stakeholder | Need or Observation | Explicit/Implicit | Evidence Label | Source ID | Confidence |
|---|---|---|---|---|---|---|
| EL-01 | Student | Needs to view tasks and monitor deadlines. | Explicit | FACT | EL-SRC-01 | High |
| EL-02 | Administrator | Needs to manage system configuration. | Explicit | FACT | EL-SRC-02 | High |
| EL-03 | Lecturer | May need to revise a deadline after publishing an assignment. | Implicit | ASSUMPTION | EL-SRC-01 | Low |

## Conflicts and Dependencies
| Item ID | Related Finding IDs | Description | Status |
|---|---|---|---|
| EL-D-01 | EL-01, EL-03 | Student deadline monitoring could depend on whether Lecturer deadline revisions are permitted. | OPEN QUESTION |

## Information Gaps and Follow-up Questions
| Question ID | Target Stakeholder | Related Finding ID | Question | Technique | Status |
|---|---|---|---|---|---|
| EL-Q-01 | Lecturer | EL-03 | May a published assignment deadline be revised? | Follow-up interview | OPEN QUESTION |
| EL-Q-02 | Administrator | EL-02 | Which configuration categories are currently managed by the Administrator? | Follow-up interview | OPEN QUESTION |

## Constraints
| Item ID | CONSTRAINT | Source ID |
|---|---|---|
| EL-C-01 | Available evidence does not define the deadline revision policy. | EL-SRC-01 |

## Assumptions Requiring Validation
| Item ID | ASSUMPTION | Source ID | Validation Question |
|---|---|---|---|
| EL-A-01 | Lecturer may revise a published deadline. | EL-SRC-01 | May a published assignment deadline be revised? |

## Elicitation Summary
- Confirmed findings: EL-01 and EL-02.
- Unresolved OPEN QUESTION items: EL-Q-01 and EL-Q-02.
- Handoff notes for Skill 3: Do not specify EL-03 until EL-Q-01 is answered.
```

The example stops at elicitation findings. It does not define final requirements, user stories, acceptance criteria, priorities, diagrams, traceability, or change requests.
