# Requirement Change Request

## Change Description

`ASSUMPTION`: Allow Student to resubmit a file after the assignment deadline.

## Reason and Source

- Reason: `ASSUMPTION`: Student may need a correction opportunity after an initial submission.
- Source: Raw validation output proposed acceptance, but reviewed evidence shows deadline and resubmission policies remain unresolved.
- Evidence labels: `ASSUMPTION`, `OPEN QUESTION`.

## Classification

- Type: Requirement change proposal.
- Status: Not approved.
- Evidence labels: ASSUMPTION / OPEN QUESTION.

## Affected Artifacts

- Requirements: FR-02, FR-04, FR-05.
- User stories: US-04, US-05.
- Prioritization: CF-03, DEC-04.
- Validation: FR-04 open questions.

## Impact Analysis

- Scope: Would extend submission behavior beyond the confirmed ability to submit a file.
- Consistency: May conflict with deadline policy because late submission and resubmission rules are not defined.
- Feasibility: Unknown until file handling, deadline rules, and operational constraints are confirmed.
- Testability: Requires measurable rules for when resubmission is permitted, what replaces the prior file, and how status changes.
- Traceability: Current evidence traces to Student interest and open questions, not to a confirmed policy.
- Stakeholder interests: Student may benefit; Lecturer grading workload and Administrator policy/configuration impact require confirmation.
- Dependencies and priorities: Affects Must requirements FR-02, FR-04, and FR-05, so it cannot be accepted casually.

## Risks and Uncertainties

- `OPEN QUESTION`: Are late submissions allowed?
- `OPEN QUESTION`: Are resubmissions allowed before or after deadline?
- `OPEN QUESTION`: How should Lecturer see revised submissions?
- `OPEN QUESTION`: Does Administrator configure late/resubmission policy?

## Decision

- Recommendation: NEEDS CLARIFICATION.
- Rationale: The requested behavior depends on academic policy that is not supplied in the official case or current inputs.
- Conditions: Confirm policy with Lecturer and Administrator, update affected requirements and user stories, then rerun prioritization and validation.

## Required Follow-up Updates

- If accepted later, revise FR-04 and FR-05.
- Add or revise acceptance criteria in US-04 and US-05.
- Reassess MoSCoW priority and dependencies.
- Revalidate affected requirements for completeness, consistency, and testability.

## Human Approval Status

Pending. This document recommends clarification, not acceptance.
