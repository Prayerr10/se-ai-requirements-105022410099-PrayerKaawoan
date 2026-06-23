---
name: negotiation-and-prioritization
description: Prioritize specified functional requirements with MoSCoW, reconcile Lecturer, Student, and Administrator interests, identify dependencies and trade-offs, and record evidence-based rationales. Use after requirements specification and before validation.
---

# Negotiation and Prioritization

## Purpose

Convert an agreed specification into a transparent, reviewable priority proposal. Classify every functional requirement (FR) with MoSCoW, identify stakeholder conflicts and dependencies, document trade-offs, and preserve the original meaning of each requirement unless an explicit decision authorizes a change.

## When to Use

Use after Skill 3 has produced the requirements specification and user stories, and before Skill 5 validates the prioritized baseline. Run again whenever the specification, stakeholder evidence, dependencies, constraints, or prioritization decisions change.

## Inputs

- `outputs/reviewed/03-requirements.md`: functional requirements, non-functional requirements, business rules, sources, and known constraints produced by Skill 3.
- `outputs/reviewed/04-user-stories.md`: user stories and acceptance criteria produced by Skill 3.
- A prioritization request that identifies the intended decision scope and any newly supplied stakeholder evidence.

Do not proceed from file names alone. Confirm that every FR has a unique ID and enough source information to evaluate value, urgency, risk, and dependency.

## Required Context

Read both Skill 3 outputs in full. Preserve their terminology, identifiers, and links among requirements, user stories, and acceptance criteria. Use `CASE.md`, `inputs/stakeholder-notes.md`, `inputs/interview-answers.md`, and `inputs/assumptions.md` only when the Skill 3 outputs cite them or additional context is needed to resolve provenance. Treat statements according to their recorded labels: `FACT`, `ASSUMPTION`, `CONSTRAINT`, or `OPEN QUESTION`.

## Workflow

1. Parse every FR, related user story, acceptance criterion, stakeholder source, business rule, NFR, and `CONSTRAINT`. Report missing or duplicate IDs before prioritizing.
2. Build a working inventory with one row per FR. Do not silently add, remove, combine, split, or rewrite requirements.
3. For each FR, record the supported interests of Lecturer, Student, and Administrator. Write `No documented interest` when evidence is absent; do not infer support.
4. Identify prerequisite, sequencing, and operational dependencies. Cite the related requirement ID and explain the direction of each dependency.
5. Detect conflicts among stakeholder interests, constraints, feasibility, timing, or competing requirements. Separate documented conflicts from suspected conflicts; label unsupported interpretations `ASSUMPTION` and unresolved matters `OPEN QUESTION`.
6. Assign exactly one MoSCoW category to every FR:
   - **Must**: indispensable for the documented project objective, an explicit `CONSTRAINT`, or a prerequisite without which the agreed scope cannot operate.
   - **Should**: high documented value but a viable temporary workaround or deferral exists.
   - **Could**: documented value with lower urgency or impact and no blocking dependency.
   - **Won't (this iteration)**: explicitly deferred from the current iteration, not rejected permanently.
7. Give a requirement-specific rationale grounded in cited stakeholder evidence, dependency, risk, or constraint. Do not use circular rationales such as "high priority because it is important."
8. Record each trade-off and proposed negotiation outcome, including affected IDs, stakeholder impact, evidence, unresolved concerns, and decision status (`PROPOSED`, `ACCEPTED`, or `REJECTED`).
9. If prioritization requires changing a requirement, preserve its current text and record the proposed change and rationale in the decision log. Apply no textual change without an `ACCEPTED` decision.
10. Run the quality checks. If a failure condition applies, stop the affected decision, list precise clarification questions, and retain `UNRESOLVED` rather than inventing an answer.
11. Write the result using the specified output structure for later storage as `outputs/reviewed/05-prioritization.md`. On a repeated run, compare inputs with the previous result, reassess only affected decisions, and retain an audit trail of changed priorities.

## Output Format

Produce Markdown suitable for `outputs/reviewed/05-prioritization.md` with these sections:

1. `# Requirements Prioritization`
2. `## Input Summary` — input files, versions or commit references when available, scope, and unresolved input gaps.
3. `## Prioritization Criteria` — operational definitions of MoSCoW used in this run.
4. `## Prioritized Functional Requirements` — table with `FR ID`, `Summary`, `Stakeholder Evidence`, `Dependencies`, `MoSCoW`, and `Rationale`. Include every FR exactly once.
5. `## Stakeholder Conflicts and Negotiation` — conflict ID, affected FRs, Lecturer impact, Student impact, Administrator impact, evidence, trade-off, proposed outcome, and status.
6. `## Dependency Analysis` — source FR, dependency type, target FR, effect, and evidence.
7. `## Decision Log` — decision ID, affected IDs, original state, proposed change, rationale, status, and decision source.
8. `## ASSUMPTIONS` — numbered assumptions with validation owner or method.
9. `## OPEN QUESTIONS` — numbered questions, affected IDs, intended respondent, and blocking effect.
10. `## Quality Check Results` — pass/fail result and evidence for each quality check.

Do not create the output file while defining or demonstrating this skill.

## Rules

- Use `Lecturer`, `Student`, and `Administrator` exactly; do not replace them with synonyms.
- Preserve and visibly use the labels `FACT`, `ASSUMPTION`, `CONSTRAINT`, and `OPEN QUESTION`.
- Prioritize all and only the FRs present in `outputs/reviewed/03-requirements.md`.
- Assign exactly one MoSCoW category to every FR and provide a specific, evidence-based rationale.
- Treat `Won't` as `Won't (this iteration)` and state the deferral boundary.
- Do not invent stakeholder positions, deadlines, costs, dependencies, risks, or technical limitations. Label a necessary unsupported proposition `ASSUMPTION`.
- Do not convert an `OPEN QUESTION` into a decision without new evidence.
- Do not change requirement text, identifiers, user stories, or acceptance criteria without recording the proposed change and an `ACCEPTED` decision.
- Keep NFRs and business rules visible as constraints or decision evidence, but do not misclassify them as FRs.
- Use measurable, testable language in examples and proposed clarifications; avoid terms such as "fast", "easy", or "user-friendly" without a defined measure.
- Do not produce final project requirements, diagrams, a traceability matrix, raw AI output, reviewed output files, or a change request while authoring or illustrating this skill.

## Quality Checks

- **Coverage:** every input FR appears exactly once in the priority table.
- **Classification:** every FR has exactly one valid MoSCoW category.
- **Evidence:** each priority rationale cites documented stakeholder evidence, a dependency, risk, business rule, NFR, or `CONSTRAINT`; unsupported reasoning is labeled `ASSUMPTION`.
- **Consistency:** priorities do not contradict known dependencies or `ACCEPTED` decisions.
- **Dependency integrity:** prerequisite direction is explicit and no circular dependency is left unexplained.
- **Conflict visibility:** competing Lecturer, Student, and Administrator interests are recorded without fabricating consensus.
- **Decision integrity:** requirement wording changes occur only after an `ACCEPTED` decision and remain auditable.
- **Terminology:** required stakeholder names and information labels are used consistently.
- **Clarity and testability:** rationales and proposed clarifications avoid ambiguous, non-verifiable claims.
- **Continuity:** the output retains FR IDs and enough context for Skill 5 to validate the prioritized artifacts.

## Failure Conditions

Stop the affected prioritization decision and request clarification when:

- either required Skill 3 output is missing or unreadable;
- no FRs exist, FR IDs are missing or duplicated, or related artifacts contradict one another;
- an FR lacks enough source information to distinguish documented value from speculation;
- two requirements or stakeholder decisions conflict and no authorized decision resolves them;
- a dependency cannot be determined without inventing system behavior;
- a requested priority depends on an unanswered `OPEN QUESTION` or unsupported deadline, cost, risk, or policy;
- the requester asks to alter requirement meaning without a recorded decision; or
- not every FR can receive a defensible MoSCoW classification.

Continue with unaffected FRs only when partial completion is explicitly allowed. Mark blocked items `UNRESOLVED`, state the reason, and ask targeted questions.

## Example Invocation

> Apply the Negotiation and Prioritization skill. Read `outputs/reviewed/03-requirements.md` and `outputs/reviewed/04-user-stories.md`. Classify every FR with MoSCoW, analyze Lecturer, Student, and Administrator interests, identify dependencies and conflicts, and record decision rationales. Treat undocumented claims as `ASSUMPTION` and unanswered matters as `OPEN QUESTION`. Return Markdown in the required format without writing any project file.

## Expected Output Example

```markdown
  # Requirements Prioritization

  ## Prioritized Functional Requirements

  | FR ID | Summary | Stakeholder Evidence | Dependencies | MoSCoW | Rationale |
  |---|---|---|---|---|---|
  | FR-01 | Student submits a task file before its recorded deadline | Student need documented in the input; Lecturer need documented in the input | None documented | Must | The input identifies submission as part of the system's core task-management purpose. |
  | FR-02 | Lecturer records feedback for a submitted task | Lecturer need documented in the input; Student interest documented in the input | FR-01 | Should | Feedback has documented value, but the input does not establish it as a prerequisite for submission. |

  ## Stakeholder Conflicts and Negotiation

  | Conflict ID | Affected FRs | Lecturer impact | Student impact | Administrator impact | Evidence | Trade-off | Proposed outcome | Status |
  |---|---|---|---|---|---|---|---|---|
  | CF-01 | FR-02 | Feedback workflow effort | Access to feedback | No documented impact | Skill 3 artifacts | Prioritize feedback value against implementation sequence | Place after submission capability | PROPOSED |

  ## ASSUMPTIONS

  - `ASSUMPTION A-01`: FR-02 can be delivered after FR-01 without preventing task submission. Validate with Lecturer and Student before accepting the sequence.

  ## OPEN QUESTIONS

  - `OPEN QUESTION OQ-01`: Is feedback required in the first release? Affects FR-02; ask Lecturer; blocks final acceptance of its priority.
```

The IDs and classifications above demonstrate structure only. Recalculate them from the actual Skill 3 outputs on every run.
