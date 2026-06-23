---
name: project-inception-stakeholder-discovery
description: Analyze an official project case at requirements inception, establish goals, stakeholders, scope boundaries, constraints, assumptions, and open questions, and prepare a traceable inception draft for elicitation. Use before elicitation when CASE.md and initial stakeholder evidence are available.
---

# Project Inception and Stakeholder Discovery

## Purpose

Transform limited project evidence into a structured inception draft without inventing facts. Establish the problem context, initial objectives, stakeholder needs and interests, scope boundaries, `FACT`, `ASSUMPTION`, `CONSTRAINT`, and `OPEN QUESTION` entries needed by the elicitation skill.

## When to Use

Use at the beginning of Requirements Engineering, before interview planning or detailed requirement specification. Re-run whenever the official case or initial stakeholder evidence changes, then compare the new draft with the previous inception result.

## Inputs

- `CASE.md`: official case description, initial objectives, known facts, information boundaries, and open questions.
- Stakeholder notes or equivalent initial stakeholder evidence: initial needs, interests, and information gaps for the stakeholders named in the case.
- Assumptions register or equivalent context: registered `FACT`, `ASSUMPTION`, `CONSTRAINT`, and `OPEN QUESTION` entries.

## Required Context

Read all supplied input files completely before analysis. Treat `CASE.md` or the official case text as the case boundary and use the other files only to organize or qualify that evidence. Identify canonical stakeholder names from the supplied case instead of assuming fixed roles. For the Student Task Management System assignment, use Lecturer, Student, and Administrator exactly. If re-running the skill, also read the latest inception draft supplied by the user and identify changed source statements. Do not read later-stage requirements artefacts as evidence for inception.

## Workflow

1. Verify that every required input exists, is readable, and identifies its source or epistemic label.
2. Extract only statements supported by the inputs; preserve existing identifiers where present and record the source file for every substantive statement.
3. Normalize stakeholder names to the roles explicitly named in the case. For the Student Task Management System assignment, normalize to Lecturer, Student, and Administrator. Do not infer additional stakeholders; record them as `OPEN QUESTION` candidates unless a source confirms them.
4. Summarize the case context and initial objectives without converting them into functional requirements, non-functional requirements, user stories, or solution designs.
5. For each stakeholder, separate stated needs from interests and unresolved information gaps. Preserve `ASSUMPTION` labels on interpretations not directly supported by the official case.
6. Consolidate scope as `In Scope`, `Out of Scope`, or `Unresolved`. Place an item in `Out of Scope` only when a source explicitly excludes it; otherwise use `Unresolved`.
7. Consolidate all `FACT`, `ASSUMPTION`, `CONSTRAINT`, and `OPEN QUESTION` entries. Never promote an `ASSUMPTION` to `FACT` without explicit source evidence.
8. Detect duplicates, contradictions, missing provenance, vague wording, and unsupported certainty. Convert unresolved conflicts into `OPEN QUESTION` entries and cite both conflicting sources.
9. Rank open questions for the next elicitation activity using High, Medium, or Low urgency, with a short evidence-based rationale.
10. Run every quality check. If a failure condition applies, stop and request clarification instead of completing the draft.
11. Produce the draft using the required output format for later human review and eventual storage as `outputs/reviewed/01-inception.md`.

## Output Format

Return one Markdown draft with this structure:

```markdown
 # Project Inception and Stakeholder Discovery

 ## Evidence Summary
| Source | Evidence Used | Label |

 ## Case Context

 ## Initial Objectives

 ## Stakeholder Analysis
 ### <Stakeholder 1>
 #### Needs
 #### Interests
 #### Information Gaps
 ### <Stakeholder 2>
 #### Needs
 #### Interests
 #### Information Gaps
 ### <Stakeholder 3>
 #### Needs
 #### Interests
 #### Information Gaps

 ## Scope Boundaries
 ### In Scope
 ### Out of Scope
 ### Unresolved

 ## FACT
 ## ASSUMPTION
 ## CONSTRAINT
 ## OPEN QUESTION
| ID | Question | Urgency | Rationale | Source Gap |

 ## Contradictions and Risks
 ## Handoff to Elicitation
```

The output is a draft for human review, not an approved baseline. It must not contain requirement IDs, user stories, acceptance criteria, diagrams, prioritization decisions, traceability matrices, or change requests.

## Rules

- Use only evidence contained in the required inputs.
- Use the stakeholder names explicitly supplied by the case exactly and consistently; for the Student Task Management System assignment, use Lecturer, Student, and Administrator exactly.
- Prefix or otherwise visibly label every classified statement as `FACT`, `ASSUMPTION`, `CONSTRAINT`, or `OPEN QUESTION`.
- Never invent a fact. Label any interpretation not directly supported by the official case as `ASSUMPTION` and cite its source context.
- Keep objectives at the outcome level; do not write final functional or non-functional requirements.
- Do not turn quality concerns into measurable targets unless the inputs provide those targets.
- Preserve uncertainty. Do not answer an `OPEN QUESTION` using an `ASSUMPTION`.
- Avoid ambiguous claims such as “fast,” “easy,” or “secure” unless quoting a source and marking the need for clarification.
- Keep all statements traceable to a source file.
- Do not modify source documents or create downstream artefacts.

## Quality Checks

- All three required input files were read completely.
- Every substantive statement has a source and correct epistemic label.
- Sourced stakeholder names appear consistently, with needs separated from interests.
- Objectives, scope, assumptions, constraints, and open questions are internally consistent.
- No `ASSUMPTION` is presented as `FACT`.
- No unresolved item is silently placed in or out of scope.
- Open questions address missing or conflicting evidence and include urgency rationales.
- The output contains no final requirements, requirement IDs, user stories, acceptance criteria, diagrams, priorities, traceability matrices, or change requests.
- The handoff states what the elicitation skill must investigate next.

## Failure Conditions

Stop and request clarification without producing a complete inception draft when:

- any required input file is missing or unreadable;
- the official case cannot be distinguished from added interpretation;
- stakeholder terminology cannot be reconciled with the roles explicitly named in the case;
- critical input statements contradict each other and neither source has precedence;
- a requested conclusion requires inventing facts or resolving an `OPEN QUESTION` without evidence; or
- source provenance is insufficient to classify key statements.

When stopping, list the blocking item, affected source, missing clarification, and the safest partial result available.

## Example Invocation

```text
Run Project Inception and Stakeholder Discovery for the Student Task Management System.
Read CASE.md, inputs/stakeholder-notes.md, and inputs/assumptions.md completely.
Produce an inception draft using the mandated output format. Preserve all uncertainty,
label FACT, ASSUMPTION, CONSTRAINT, and OPEN QUESTION, and do not create requirements.
```

## Expected Output Example

```markdown
 # Project Inception and Stakeholder Discovery

 ## Evidence Summary
| Source | Evidence Used | Label |
|---|---|---|
| CASE.md | Student Task Management System is used in a campus context. | FACT |

 ## Case Context
- `FACT`: The case concerns campus task management.

 ## Stakeholder Analysis
 ### Lecturer
 #### Needs
- `FACT`: Create coursework assignments and set deadlines.
 #### Interests
- `ASSUMPTION`: Avoid unnecessary administrative burden; confirm during elicitation.
 #### Information Gaps
- `OPEN QUESTION`: Can Lecturer revise a deadline after publication?

 ## Scope Boundaries
 ### Unresolved
- `OPEN QUESTION`: Whether integration with another campus system is in scope.

 ## OPEN QUESTION
| ID | Question | Urgency | Rationale | Source Gap |
|---|---|---|---|---|
| OPEN-02 | What rules govern assignment publication? | High | The workflow cannot be understood without this policy. | CASE.md does not define it. |

 ## Handoff to Elicitation
- Ask Lecturer about assignment publication and deadline-change rules.
```
