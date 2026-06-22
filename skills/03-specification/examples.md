# Requirements Elaboration and Specification Examples

## Example Invocation

```text
Apply the Requirements Elaboration and Specification skill.
Primary input: outputs/reviewed/02-elicitation.md
Supporting context: inputs/assumptions.md
Draft the required structures for outputs/reviewed/03-requirements.md and
outputs/reviewed/04-user-stories.md. Preserve FACT, ASSUMPTION, CONSTRAINT,
and OPEN QUESTION labels. Do not prioritize or create downstream artifacts.
```

## Example Output

```markdown
Artifact: outputs/reviewed/03-requirements.md

### FR-01 — Record task details
- Statement: The system shall record task details entered by a Lecturer.
- Stakeholder: Lecturer
- Source: EL-01
- Status: FACT

### NFR-01 — Task-view response time
- Statement: Under the agreed test workload, the system shall display a task view within 2 seconds for at least 95% of requests.
- Measure and threshold: Response time <= 2 seconds for >= 95% of requests
- Operating context: ASSUMPTION — workload remains an OPEN QUESTION
- Verification method: Performance test
- Source: EL-04
- Status: ASSUMPTION

Artifact: outputs/reviewed/04-user-stories.md

## US-01 — Enter task details
- Story: As a Lecturer, I want to enter task details, so that Students can understand the assigned work.
- Supports: FR-01
- Source: EL-01
- Status: FACT
### Acceptance Criteria
- AC-US01-01: Given a Lecturer entering sourced task details, when the Lecturer saves them, then the system records those details for the task.
- AC-US01-02: Given recorded task details, when a Student opens the task, then the system displays the recorded details.

## Open Questions
- OPEN QUESTION: What workload must be used to verify NFR-01?
```

This abbreviated example demonstrates structure only. A real run must satisfy the assignment minimums using supported evidence; it must not invent content to fill gaps.
