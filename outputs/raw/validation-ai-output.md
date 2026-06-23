# Raw AI Output — Skill 5: Requirements Validation and Change Management

## Invocation

Read `outputs/reviewed/03-requirements.md`, `outputs/reviewed/04-user-stories.md`, `outputs/reviewed/05-prioritization.md`, and `skills/05-validation-change/SKILL.md`. Execute Requirements Validation and Change Management. Save the first output as raw AI output. Validate at least five requirements and analyze one change request. Do not create traceability, diagrams, use-case output, skill testing, GitHub issues, CHANGELOG, or reflection.

# Requirements Validation

## Validation Scope

- Inputs reviewed: requirements specification, user stories, prioritization.
- Selection rationale: Validate high-priority and assumption-heavy items: FR-01, FR-04, FR-07, FR-08, NFR-01.

## Validation Results

### FR-01
- Original statement: The system shall allow Lecturer to create an assignment record.
- Decision: PASS.
- Clarity: PASS — actor and behavior are clear.
- Completeness: PASS — enough for current level.
- Consistency: PASS — matches Lecturer need.
- Feasibility: PASS — no conflict identified.
- Testability: PASS — creation of assignment record is observable.
- Traceability: PASS — linked to EL-01 and US-01.
- Proposed revision: None.

### FR-04
- Original statement: The system shall allow Student to submit a file for an assignment.
- Decision: PASS.
- Clarity: PASS — actor and behavior are clear.
- Completeness: OPEN QUESTION — accepted file constraints are unknown.
- Consistency: PASS — matches Student need.
- Feasibility: PASS.
- Testability: PASS.
- Traceability: PASS — linked to EL-05 and US-04.
- Proposed revision: None.

### FR-07
- Original statement: The system shall allow Lecturer to record feedback for a Student submission.
- Decision: PASS.
- Clarity: PASS.
- Completeness: PASS.
- Consistency: PASS.
- Feasibility: PASS.
- Testability: PASS.
- Traceability: PASS.
- Proposed revision: None.

### FR-08
- Original statement: The system shall allow Administrator to manage users.
- Decision: PASS.
- Clarity: PASS.
- Completeness: OPEN QUESTION — allowed user operations are not defined.
- Consistency: PASS.
- Feasibility: PASS.
- Testability: PASS.
- Traceability: PASS.
- Proposed revision: None.

### NFR-01
- Original statement: The system shall display assignment lists within 2 seconds for 95% of requests under an agreed test workload.
- Decision: PASS.
- Clarity: PASS.
- Completeness: OPEN QUESTION — test workload still needs confirmation.
- Consistency: PASS.
- Feasibility: PASS.
- Testability: PASS.
- Traceability: PASS.
- Proposed revision: None.

## Validation Summary

- All selected requirements can proceed.
- Some open questions remain.

# Requirement Change Request

## Change Description

Allow Student to resubmit a file after the assignment deadline.

## Reason and Source

Student may need correction opportunities.

## Classification

- Evidence labels: ASSUMPTION / OPEN QUESTION

## Affected Artifacts

- FR-02, FR-04, FR-05, US-04, US-05

## Impact Analysis

- Scope: Changes submission behavior.
- Consistency: Could conflict with deadline policy.
- Feasibility: Unknown.
- Testability: Need rules for allowed timing and outcomes.
- Traceability: Affected IDs listed.
- Stakeholder interests: Student benefits; Lecturer and Administrator policy impact unclear.
- Dependencies and priorities: Affects Must requirements.

## Decision

- Recommendation: ACCEPT
- Rationale: Resubmission helps Student.
- Conditions: Define policy later.
