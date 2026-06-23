# Requirements Prioritization

## Input Summary

- Specification: `outputs/reviewed/03-requirements.md`
- User stories: `outputs/reviewed/04-user-stories.md`
- Scope: FR-01 through FR-10.
- Known unresolved gaps: file constraints, status values, grade format, configuration categories, quality test workload.

## Prioritization Criteria

- **Must**: Required for the core assignment-submission workflow, role administration, or an explicit dependency.
- **Should**: High value in the official case but can be sequenced after the minimum workflow.
- **Could**: Useful but lower urgency and no blocking dependency.
- **Won't (this iteration)**: Explicitly deferred for this iteration; no FR is currently deferred.

## Prioritized Functional Requirements

| FR ID | Summary | Stakeholder Evidence | Dependencies | MoSCoW | Rationale |
|---|---|---|---|---|---|
| FR-01 | Lecturer creates assignment records | EL-01 | None documented | Must | Assignment creation is the starting point for the assignment workflow. |
| FR-02 | Lecturer sets assignment deadlines | EL-02, EL-06 | FR-01 | Must | Deadline data supports Student deadline monitoring and is part of the official Lecturer activity. |
| FR-03 | Student views assignments | EL-04 | FR-01 | Must | Student must see assignments before submission or status monitoring has practical value. |
| FR-04 | Student submits assignment files | EL-05 | FR-01, FR-03 | Must | Submission is a core official activity in the case. |
| FR-05 | Student monitors status and deadline | EL-06 | FR-02, FR-04 | Must | Monitoring status and deadline is explicitly stated for Student. |
| FR-06 | Lecturer records grades | EL-03 | FR-04 | Should | Grading is official, but it depends on submissions and can be sequenced after the initial submission workflow. |
| FR-07 | Lecturer records feedback | EL-03 | FR-04 | Should | Feedback is official, but the timing and visibility policy remain unresolved. |
| FR-08 | Administrator manages users | EL-07, BR-01 | None documented | Must | User administration supports role-based access and system operation. |
| FR-09 | Administrator manages courses | EL-08 | FR-01 | Must | Course management is part of Administrator scope and provides context for coursework assignments. |
| FR-10 | Administrator manages system configuration | EL-09, EL-Q-08 | FR-08, FR-09 | Should | Configuration is official Administrator scope, but categories remain unresolved. |

## Stakeholder Conflicts and Negotiation

| Conflict ID | Affected FRs | Lecturer impact | Student impact | Administrator impact | Evidence | Trade-off | Proposed outcome | Status |
|---|---|---|---|---|---|---|---|---|
| CF-01 | FR-06, FR-07 | Needs grade and feedback entry | Needs eventual visibility, but timing is unknown | No documented impact | EL-03, EL-Q-05 | Evaluation value versus unresolved visibility policy | Keep FR-06 and FR-07 as Should until visibility policy is confirmed | PROPOSED |
| CF-02 | FR-10 | No documented impact | No documented impact | Needs configuration control | EL-09, EL-Q-08 | Administrative flexibility versus undefined configuration categories | Keep FR-10 as Should and validate categories with Administrator | PROPOSED |
| CF-03 | FR-04, FR-05 | Late/resubmission policy may affect grading workload | Student may want correction opportunity | Policy enforcement may need configuration | EL-Q-02, EL-Q-03 | Student flexibility versus policy clarity | Do not add resubmission behavior until policy is clarified | PROPOSED |

## Dependency Analysis

| Source FR | Dependency Type | Target FR | Effect | Evidence |
|---|---|---|---|---|
| FR-02 | sequencing | FR-01 | A deadline is associated with an assignment. | EL-01, EL-02, BR-02 |
| FR-03 | sequencing | FR-01 | Student views assignment records created by Lecturer. | EL-01, EL-04 |
| FR-04 | sequencing | FR-01, FR-03 | Submission is for an assignment Student can access. | EL-04, EL-05 |
| FR-05 | data dependency | FR-02, FR-04 | Status and deadline monitoring uses deadline and submission/status data. | EL-02, EL-06 |
| FR-06 | prerequisite | FR-04 | Grade applies to a Student submission. | EL-03, EL-05 |
| FR-07 | prerequisite | FR-04 | Feedback applies to a Student submission. | EL-03, EL-05 |
| FR-10 | operational | FR-08, FR-09 | Configuration details may depend on user and course setup. | EL-07, EL-08, EL-09 |

## Decision Log

| Decision ID | Affected IDs | Original state | Proposed change | Rationale | Status | Decision source |
|---|---|---|---|---|---|---|
| DEC-01 | FR-01 to FR-10 | Unprioritized | Assign MoSCoW categories in the priority table | Required by assignment and supported by reviewed requirements | ACCEPTED | Prioritization review |
| DEC-02 | FR-06, FR-07 | Candidate Must | Classify as Should | Official value is documented, but submission workflow and visibility policy come first | ACCEPTED | Prioritization review |
| DEC-03 | FR-10 | Candidate Must/Should | Classify as Should | Configuration categories are unresolved | ACCEPTED | Prioritization review |
| DEC-04 | Resubmission behavior | Not specified | Do not add as FR in prioritization | Deadline/resubmission policy is an OPEN QUESTION | ACCEPTED | Prioritization review |

## ASSUMPTIONS

- `ASSUMPTION`: FR-08 user management is needed before role-specific access can be controlled.
- `ASSUMPTION`: FR-09 course management provides context for assignments.
- `ASSUMPTION`: FR-10 can be sequenced after core user and course setup until configuration categories are clarified.

## OPEN QUESTIONS

- `OPEN QUESTION`: What exact status values should FR-05 display?
- `OPEN QUESTION`: Are late submissions or resubmissions allowed?
- `OPEN QUESTION`: Which configuration categories are in scope for FR-10?
- `OPEN QUESTION`: When are grades and feedback visible to Student?

## Quality Check Results

- Coverage: PASS — every FR from FR-01 through FR-10 appears exactly once.
- Classification: PASS — every FR has exactly one MoSCoW category.
- Evidence: PASS — each rationale cites stakeholder evidence, dependency, or labeled assumption.
- Dependency integrity: PASS — dependency direction is explicit.
- Conflict visibility: PASS — unresolved policy issues remain visible as OPEN QUESTION.
- Continuity: PASS — FR IDs are preserved for validation.
