---
name: requirements-validation-change-management
description: Validate prioritized software requirements and evaluate proposed changes with explicit evidence, revision rationale, impact analysis, and a documented decision. Use after prioritization when preparing validation and change-management artifacts.
---

# Requirements Validation and Change Management

## Purpose

Validate a prioritized requirement set for clarity, completeness, consistency, feasibility, testability, and traceability. Record justified revisions and assess proposed changes without automatically accepting them. Produce repeatable drafts for `outputs/reviewed/07-validation.md` and `outputs/reviewed/08-change-request.md` for human review.

## When to Use

Use after Skill 4 has produced a prioritized requirement set. Run it before establishing or updating a requirements baseline, and rerun it whenever requirements, priorities, evidence, constraints, or a proposed change are updated.

## Inputs

Require:

- `outputs/reviewed/05-prioritization.md`, the output of Skill 4.
- `outputs/reviewed/03-requirements.md`.
- `outputs/reviewed/04-user-stories.md`.
- A change proposal containing its description and reason when change analysis is requested.

If any required input is missing, stop and report it. Do not infer its contents.

## Required Context

Read the required inputs and, when needed to verify provenance or unresolved information, read:

- `outputs/reviewed/01-inception.md`.
- `outputs/reviewed/02-elicitation.md`.
- `CASE.md`.
- `inputs/stakeholder-notes.md`.
- `inputs/interview-answers.md`.
- `inputs/assumptions.md`.

Preserve the exact identifiers and the terms `Lecturer`, `Student`, and `Administrator`. Interpret statements according to their labels: `FACT`, `ASSUMPTION`, `CONSTRAINT`, and `OPEN QUESTION`.

## Workflow

1. Verify that the prioritized requirements, requirements specification, and user stories are present, readable, and internally identifiable. Record missing or conflicting context instead of filling gaps.
2. Build an inventory of requirement IDs, related user-story and acceptance-criteria IDs, priority, stakeholder, source, and status. Preserve existing IDs.
3. Select at least five requirements for validation. Include riskier, higher-priority, conflicting, weakly sourced, or change-affected items when available, and state the selection rationale.
4. Validate each selected requirement independently for:
   - clarity: one interpretation, defined actors, and no vague qualifiers;
   - completeness: necessary condition, behavior, outcome, and applicable boundary information are present;
   - consistency: no conflict with another artifact, priority, `FACT`, or `CONSTRAINT`;
   - feasibility: no unsupported claim of technical, operational, schedule, or policy feasibility;
   - testability: observable result and verifiable acceptance criteria exist;
   - traceability: stakeholder, source, user story, acceptance criteria, and priority references are identifiable.
5. Assign each check `PASS`, `FAIL`, or `OPEN QUESTION`, with evidence. Do not treat an `ASSUMPTION` as confirmed evidence.
6. For every `FAIL`, propose a precise revision only when supported by existing context. Preserve the original text, show the revised text, give a revision rationale, and identify affected artifacts. If evidence is insufficient, create an `OPEN QUESTION` instead of inventing a revision.
7. Summarize the validation result, unresolved questions, and readiness for human approval. A validation draft does not establish the baseline by itself.
8. When a change proposal is supplied, identify affected requirements, user stories, acceptance criteria, priorities, stakeholders, dependencies, validation results, and relevant `CONSTRAINT` or `ASSUMPTION` entries.
9. Analyze the change impact on scope, consistency, feasibility, testability, traceability, and stakeholder interests. Distinguish verified impact from uncertain impact.
10. Recommend exactly one decision: `ACCEPT`, `REJECT`, `DEFER`, or `NEEDS CLARIFICATION`. Support it with evidence and conditions; never accept a change merely because it was requested.
11. List required follow-up updates without performing them. Recheck identifiers and cross-references, then format the two requested drafts.

## Output Format

Return two clearly separated Markdown drafts; do not write files unless explicitly asked.

Draft for `outputs/reviewed/07-validation.md`:

```markdown
    # Requirements Validation

    ## Validation Scope
- Inputs reviewed:
- Selection rationale:

    ## Validation Results
    ### <Requirement ID>
- Original statement:
- Clarity: <PASS|FAIL|OPEN QUESTION> — <evidence>
- Completeness: <PASS|FAIL|OPEN QUESTION> — <evidence>
- Consistency: <PASS|FAIL|OPEN QUESTION> — <evidence>
- Feasibility: <PASS|FAIL|OPEN QUESTION> — <evidence>
- Testability: <PASS|FAIL|OPEN QUESTION> — <evidence>
- Traceability: <PASS|FAIL|OPEN QUESTION> — <evidence>
- Proposed revision: <text|None>
- Revision rationale: <reason|None>
- Affected artifacts: <IDs or files|None>

    ## Unresolved Open Questions
    ## Validation Summary
    ## Human Review Status
```

Include at least five requirement result blocks.

Draft for `outputs/reviewed/08-change-request.md`:

```markdown
    # Requirement Change Request

    ## Change Description
    ## Reason and Source
    ## Classification
- Evidence labels: <FACT|ASSUMPTION|CONSTRAINT|OPEN QUESTION>

    ## Affected Artifacts
    ## Impact Analysis
- Scope:
- Consistency:
- Feasibility:
- Testability:
- Traceability:
- Stakeholder interests:
- Dependencies and priorities:

    ## Risks and Uncertainties
    ## Decision
- Recommendation: <ACCEPT|REJECT|DEFER|NEEDS CLARIFICATION>
- Rationale:
- Conditions:

    ## Required Follow-up Updates
    ## Human Approval Status
```

## Rules

- Do not invent facts, policies, measurements, stakeholder statements, or implementation details.
- Label every unsupported proposal as `ASSUMPTION`; preserve known `FACT`, `CONSTRAINT`, and `OPEN QUESTION` labels.
- Use `Lecturer`, `Student`, and `Administrator` consistently.
- Preserve existing requirement, user-story, acceptance-criteria, and source IDs; report missing IDs.
- Do not silently rewrite a requirement. Retain original text, revision, rationale, and affected references.
- Reject vague language such as “fast,” “easy,” or “secure” unless a measurable criterion is provided or the gap is marked `OPEN QUESTION`.
- Do not mark a requirement testable when its result cannot be objectively observed or verified.
- Do not claim traceability when any required link cannot be identified.
- Do not automatically accept a proposed change. Separate analysis from the human approval decision.
- Do not create final requirements, diagrams, a traceability matrix, raw AI output, or reviewed output files while defining or demonstrating this skill.

## Quality Checks

Before returning results, confirm that:

- At least five requirements were validated across all six quality dimensions.
- Every conclusion cites an input statement, identifier, or explicitly labeled information gap.
- Every failed check has either a supported revision or an `OPEN QUESTION`.
- Each revision retains original text, rationale, and affected artifacts.
- Change impact covers scope, consistency, feasibility, testability, traceability, stakeholder interests, dependencies, and priorities.
- The change recommendation is one allowed decision and includes evidence, risks, conditions, and human approval status.
- IDs and the stakeholder and evidence-label vocabulary remain consistent.
- No `ASSUMPTION` was presented as a `FACT`.

## Failure Conditions

Stop and request clarification when:

- Any mandatory input is missing, unreadable, or contains no identifiable requirements.
- Fewer than five requirements are available for the required minimum validation.
- Conflicting artifacts prevent a defensible validation result.
- A proposed revision requires an unknown policy, metric, or stakeholder decision.
- A change request lacks a description or reason.
- Impact cannot be traced to the available requirement artifacts.

Return the blocking file, identifier, conflict, or `OPEN QUESTION`; do not fabricate a workaround.

## Example Invocation

```text
Apply Requirements Validation and Change Management using:
- outputs/reviewed/05-prioritization.md
- outputs/reviewed/03-requirements.md
- outputs/reviewed/04-user-stories.md
- outputs/reviewed/01-inception.md and outputs/reviewed/02-elicitation.md for provenance

Validate at least five requirements. Then assess the supplied proposed change, identify impacts, and recommend ACCEPT, REJECT, DEFER, or NEEDS CLARIFICATION. Return drafts only; do not write output files.
```

## Expected Output Example

Illustrative excerpt only; it is not a final project artifact:

```markdown
    # Requirements Validation

    ## Validation Results
    ### FR-EX-01
- Original statement: After a successful upload, the system records the Student submission status and timestamp.
- Evidence label: ASSUMPTION
- Clarity: PASS — Actor, trigger, and recorded outcome are explicit.
- Completeness: OPEN QUESTION — The input does not define what qualifies as a successful upload.
- Consistency: PASS — No conflict is present in the supplied example inputs.
- Feasibility: OPEN QUESTION — Storage and operational constraints are not supplied.
- Testability: PASS — A tester can verify the status and timestamp after the stated trigger.
- Traceability: FAIL — No acceptance-criteria identifier is supplied.
- Proposed revision: None
- Revision rationale: Additional source evidence is required before revision.
- Affected artifacts: US-EX-01; missing acceptance-criteria reference

    # Requirement Change Request

    ## Change Description
`ASSUMPTION`: Permit a Student to replace a submitted file after the deadline.

    ## Decision
- Recommendation: NEEDS CLARIFICATION
- Rationale: The deadline and resubmission policies are `OPEN QUESTION`, so acceptance is not evidence-based.
- Conditions: Lecturer and Administrator policy decisions must be recorded and affected requirements revalidated.

    ## Human Approval Status
Pending; this recommendation does not approve the change.
```
