# Negotiation and Prioritization Examples

These examples demonstrate the reusable instruction contract. They do not define final project requirements or create `outputs/reviewed/05-prioritization.md`.

## Example Invocation

```text
Use skills/04-prioritization/SKILL.md.

Read:
- outputs/reviewed/03-requirements.md
- outputs/reviewed/04-user-stories.md

Prioritize every FR with exactly one MoSCoW category. Record the documented interests of Lecturer, Student, and Administrator, requirement dependencies, stakeholder conflicts, trade-offs, and requirement-specific rationales. Preserve FACT, ASSUMPTION, CONSTRAINT, and OPEN QUESTION labels. Do not alter a requirement unless an ACCEPTED decision is recorded. Return the required Markdown structure in the response only.
```

## Example Output

```markdown
# Requirements Prioritization

## Input Summary

- Specification: `outputs/reviewed/03-requirements.md`
- User stories: `outputs/reviewed/04-user-stories.md`
- Scope: all FRs found in the specification

## Prioritized Functional Requirements

| FR ID | Summary | Stakeholder Evidence | Dependencies | MoSCoW | Rationale |
|---|---|---|---|---|---|
| FR-01 | Student submits a task file before its recorded deadline | Student need and Lecturer task-management interest are documented in the input | None documented | Must | Submission directly supports the documented project purpose. |
| FR-02 | Administrator manages user records | Administrator need documented in the input | None documented | Should | The need is documented, but the input does not establish it as a prerequisite for FR-01. |

## Stakeholder Conflicts and Negotiation

| Conflict ID | Affected FRs | Lecturer impact | Student impact | Administrator impact | Evidence | Trade-off | Proposed outcome | Status |
|---|---|---|---|---|---|---|---|---|
| CF-01 | FR-02 | No documented impact | No documented impact | Later access to management capability | Skill 3 artifacts | Core submission sequence versus administration value | Schedule after FR-01 pending confirmation | PROPOSED |

## Decision Log

| Decision ID | Affected IDs | Original state | Proposed change | Rationale | Status | Decision source |
|---|---|---|---|---|---|---|
| DEC-01 | FR-02 | Unprioritized | Classify as Should | Documented Administrator value; no blocking dependency documented | PROPOSED | Prioritization analysis |

## ASSUMPTIONS

- `ASSUMPTION A-01`: Deferring FR-02 does not prevent Student submission. Validate with Administrator before accepting DEC-01.

## OPEN QUESTIONS

- `OPEN QUESTION OQ-01`: Does any `CONSTRAINT` require user administration before submission is available? Ask Administrator; affects FR-02 and DEC-01.

## Quality Check Results

- Coverage: PASS for the two illustrative FRs shown.
- Classification: PASS; each illustrative FR has one MoSCoW category.
- Evidence: PASS with one explicitly labeled `ASSUMPTION` awaiting validation.
```

The example IDs, wording, classifications, and decision are illustrative. Replace them with evidence from the actual Skill 3 outputs on each run.
