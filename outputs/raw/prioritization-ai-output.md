# Raw AI Output — Skill 4: Negotiation and Prioritization

## Invocation

Read `outputs/reviewed/03-requirements.md`, `outputs/reviewed/04-user-stories.md`, and `skills/04-prioritization/SKILL.md`. Execute Negotiation and Prioritization. Save the first output as raw AI output. Prioritize every FR with MoSCoW and record conflicts, dependencies, trade-offs, and decisions. Do not create validation, traceability, diagram, or change request files.

## Input Summary

- Requirements specification: `outputs/reviewed/03-requirements.md`
- User stories: `outputs/reviewed/04-user-stories.md`
- Scope: FR-01 through FR-10 from the reviewed requirements specification.

## Prioritization Criteria

- Must: Required for core assignment, submission, role administration, or unavoidable dependency.
- Should: High value but can be sequenced after core workflow.
- Could: Useful but lower urgency.
- Won't (this iteration): Explicitly deferred.

## Prioritized Functional Requirements

| FR ID | Summary | Stakeholder Evidence | Dependencies | MoSCoW | Rationale |
|---|---|---|---|---|---|
| FR-01 | Lecturer creates assignments | Lecturer need EL-01 | None | Must | Core Lecturer activity. |
| FR-02 | Lecturer sets deadlines | Lecturer need EL-02; Student monitoring EL-06 | FR-01 | Must | Deadlines support Student monitoring. |
| FR-03 | Student views assignments | Student need EL-04 | FR-01 | Must | Student must see assignments before acting. |
| FR-04 | Student submits files | Student need EL-05 | FR-01, FR-03 | Must | Core submission activity. |
| FR-05 | Student monitors status/deadlines | Student need EL-06 | FR-02, FR-04 | Must | Needed to track assignments. |
| FR-06 | Lecturer records grades | Lecturer need EL-03 | FR-04 | Should | Important after submission. |
| FR-07 | Lecturer records feedback | Lecturer need EL-03 | FR-04 | Must | Feedback is valuable to Student. |
| FR-08 | Administrator manages users | Administrator need EL-07 | None documented | Must | Users are needed for role access. |
| FR-09 | Administrator manages courses | Administrator need EL-08 | FR-01 | Must | Course context is needed for assignments. |
| FR-10 | Administrator manages configuration | Administrator need EL-09 | FR-08, FR-09 | Should | Configuration supports operation but details are unresolved. |

## Stakeholder Conflicts and Negotiation

| Conflict ID | Affected FRs | Lecturer impact | Student impact | Administrator impact | Evidence | Trade-off | Proposed outcome | Status |
|---|---|---|---|---|---|---|---|---|
| CF-01 | FR-06, FR-07 | Needs grade and feedback workflow | Needs visibility later | No documented impact | EL-03 and Student interests | Grade/feedback value vs incomplete visibility policy | Sequence after submissions | PROPOSED |
| CF-02 | FR-10 | Configuration changes may affect course operations | No documented impact | Needs control | EL-09 | Flexibility vs controlled configuration | Keep as Should until categories are clarified | PROPOSED |

## Dependency Analysis

| Source FR | Dependency Type | Target FR | Effect | Evidence |
|---|---|---|---|---|
| FR-02 | sequencing | FR-01 | Deadline belongs to an assignment. | EL-01, EL-02 |
| FR-04 | sequencing | FR-03 | Student submission depends on assignment access. | EL-04, EL-05 |
| FR-06 | prerequisite | FR-04 | Grade applies to a submission. | EL-03, EL-05 |
| FR-07 | prerequisite | FR-04 | Feedback applies to a submission. | EL-03, EL-05 |
| FR-10 | operational | FR-08, FR-09 | Configuration scope depends on users/courses. | EL-07, EL-08, EL-09 |

## Decision Log

| Decision ID | Affected IDs | Original state | Proposed change | Rationale | Status | Decision source |
|---|---|---|---|---|---|---|
| DEC-01 | FR-01 to FR-10 | Unprioritized | Apply MoSCoW categories above | First prioritization pass | PROPOSED | Skill 4 analysis |
| DEC-02 | FR-07 | Should candidate | Classify as Must | Feedback is part of official Lecturer activity | PROPOSED | Skill 4 analysis |

## ASSUMPTIONS

- `ASSUMPTION`: FR-08 user management is needed before role-specific access can be controlled.
- `ASSUMPTION`: FR-09 course management is needed before assignments can be organized by course.

## OPEN QUESTIONS

- `OPEN QUESTION`: Does feedback need to be available in the first release?
- `OPEN QUESTION`: Which configuration categories are included in FR-10?

## Quality Check Results

- Coverage: PASS, all FRs listed once.
- Classification: PASS, each FR has one MoSCoW category.
- Evidence: NEEDS REVIEW, some priorities rely on assumptions.
