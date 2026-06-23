# AI Output Review

## Skill 1 — Project Inception and Stakeholder Discovery

### 1. Skill

Project Inception and Stakeholder Discovery.

### 2. Invocation and input files

Invocation: Read `CASE.md`, `inputs/stakeholder-notes.md`, `inputs/assumptions.md`, and `skills/01-inception/SKILL.md`. Execute the Project Inception and Stakeholder Discovery skill exactly as written. Save the first output as raw AI output. Use Lecturer, Student, Administrator, FACT, ASSUMPTION, CONSTRAINT, and OPEN QUESTION consistently. Do not create requirements, user stories, diagrams, traceability, prioritization, validation, or change requests.

Input files:

- `CASE.md`
- `inputs/stakeholder-notes.md`
- `inputs/assumptions.md`
- `skills/01-inception/SKILL.md`

### 3. Raw AI output file

`outputs/raw/inception-ai-output.md`

### 4. Problems found by AI review

- Raw output placed campus integrations in Out of Scope even though the case does not explicitly exclude integrations.
- Raw output did not fully separate reporting as a confirmed case area from unresolved reporting details.
- Raw output did not preserve all registered FACT, ASSUMPTION, CONSTRAINT, and OPEN QUESTION items in a complete final structure.

### 5. Student review decision

Revise before accepting as reviewed inception output.

### 6. Student corrections applied

- Moved integrations from Out of Scope to Unresolved.
- Added explicit statement that no item is confirmed out of scope by the official case.
- Expanded FACT, ASSUMPTION, CONSTRAINT, and OPEN QUESTION sections.
- Added clearer handoff questions for Lecturer, Student, and Administrator.

### 7. Reason for each correction

- Out-of-scope claims require explicit source evidence; none was provided for integrations.
- Reporting is mentioned by the official case, but audience, format, and period are unknown.
- Skill 2 needs a structured and traceable handoff, not just a general narrative.

### 8. Final reviewed output file

`outputs/reviewed/01-inception.md`

## Skill 2 — Requirements Elicitation

### 1. Skill

Requirements Elicitation.

### 2. Invocation and input files

Invocation: Read `outputs/reviewed/01-inception.md`, `inputs/interview-answers.md`, `inputs/assumptions.md`, and `skills/02-elicitation/SKILL.md`. Execute Requirements Elicitation after Skill 1. Save the first output as raw AI output. Preserve FACT, ASSUMPTION, CONSTRAINT, and OPEN QUESTION labels. Do not write final requirements or user stories.

Input files:

- `outputs/reviewed/01-inception.md`
- `inputs/interview-answers.md`
- `inputs/assumptions.md`
- `skills/02-elicitation/SKILL.md`

### 3. Raw AI output file

`outputs/raw/elicitation-ai-output.md`

### 4. Problems found by AI review

- Raw output included deadline reminders as an implicit Student need, but reminders are not part of the official case.
- Raw output did not fully distinguish confirmed findings from assumption findings requiring validation.
- Raw output listed dependencies but did not clearly classify which dependencies were FACT, ASSUMPTION, or OPEN QUESTION.

### 5. Student review decision

Keep confirmed findings, but revise unsupported implicit findings into assumptions or follow-up questions.

### 6. Student corrections applied

- Removed deadline reminders as a finding.
- Added validated assumption table for EL-A-01 through EL-A-03.
- Classified dependencies and gaps more explicitly.
- Expanded follow-up questions for assignment fields, file limits, status values, visibility, administration, reports, and quality targets.

### 7. Reason for each correction

- Reminder behavior would be a new feature unless confirmed by stakeholder evidence.
- Skill 3 needs a clean boundary between confirmed FACT findings and ASSUMPTION candidates.
- Open questions must remain visible to avoid accidental conversion into requirements.

### 8. Final reviewed output file

`outputs/reviewed/02-elicitation.md`

## Skill 3 — Requirements Elaboration and Specification

### 1. Skill

Requirements Elaboration and Specification.

### 2. Invocation and input files

Invocation: Read `outputs/reviewed/02-elicitation.md`, `CASE.md`, `inputs/assumptions.md`, and `skills/03-specification/SKILL.md`. Execute Requirements Elaboration and Specification. Save the first output as raw AI output. Draft requirements and user stories only; do not prioritize, validate, create diagrams, create traceability, or create change requests.

Input files:

- `outputs/reviewed/02-elicitation.md`
- `CASE.md`
- `inputs/assumptions.md`
- `skills/03-specification/SKILL.md`

### 3. Raw AI output file

`outputs/raw/requirements-ai-output.md`

### 4. Problems found by AI review

- Raw output had only eight FR and did not cover course or configuration management as separate Administrator functions.
- NFR-01 used ambiguous wording: “respond quickly.”
- NFR verification context and thresholds were incomplete.
- US-04 had only one acceptance criterion.
- Administrative operations were too broad and needed ASSUMPTION status.

### 5. Student review decision

Revise requirements and user stories before accepting final specification.

### 6. Student corrections applied

- Expanded FR list to FR-01 through FR-10.
- Replaced ambiguous NFR wording with measurable thresholds and verification methods.
- Added FR-09 for course management and FR-10 for system configuration.
- Added complete acceptance criteria for every user story.
- Marked unconfirmed administrative operations and NFR thresholds as ASSUMPTION.

### 7. Reason for each correction

- Assignment requires at least 8 FR; separating official Administrator activities improves clarity.
- NFRs must be measurable and testable.
- Every user story must have at least two acceptance criteria.
- Information not directly confirmed by the case must remain labeled ASSUMPTION.

### 8. Final reviewed output file

- `outputs/reviewed/03-requirements.md`
- `outputs/reviewed/04-user-stories.md`

## Skill 4 — Negotiation and Prioritization

### 1. Skill

Negotiation and Prioritization.

### 2. Invocation and input files

Invocation: Read `outputs/reviewed/03-requirements.md`, `outputs/reviewed/04-user-stories.md`, and `skills/04-prioritization/SKILL.md`. Execute Negotiation and Prioritization. Save the first output as raw AI output. Prioritize every FR with MoSCoW and record conflicts, dependencies, trade-offs, and decisions. Do not create validation, traceability, diagram, or change request files.

Input files:

- `outputs/reviewed/03-requirements.md`
- `outputs/reviewed/04-user-stories.md`
- `skills/04-prioritization/SKILL.md`

### 3. Raw AI output file

`outputs/raw/prioritization-ai-output.md`

### 4. Problems found by AI review

- Raw output treated FR-07 feedback as Must without enough rationale for first-iteration priority.
- Raw output did not fully align prioritization with updated FR-09 and FR-10 details.
- Raw decision log did not clearly mark accepted prioritization decisions.

### 5. Student review decision

Revise MoSCoW classifications and decision log before accepting final prioritization.

### 6. Student corrections applied

- Classified FR-06 and FR-07 as Should rather than Must.
- Preserved FR-01, FR-02, FR-03, FR-04, FR-05, FR-08, and FR-09 as Must.
- Classified FR-10 as Should because configuration categories remain unresolved.
- Added accepted decisions DEC-01 through DEC-04.
- Added CF-03 for late/resubmission policy conflict.

### 7. Reason for each correction

- Grade and feedback are official, but depend on submission and unresolved visibility policy.
- Configuration management is official but details are not confirmed.
- Resubmission behavior must not be added during prioritization because the policy is an OPEN QUESTION.

### 8. Final reviewed output file

`outputs/reviewed/05-prioritization.md`

## Skill 5 — Requirements Validation and Change Management

### 1. Skill

Requirements Validation and Change Management.

### 2. Invocation and input files

Invocation: Read `outputs/reviewed/03-requirements.md`, `outputs/reviewed/04-user-stories.md`, `outputs/reviewed/05-prioritization.md`, and `skills/05-validation-change/SKILL.md`. Execute Requirements Validation and Change Management. Save the first output as raw AI output. Validate at least five requirements and analyze one change request. Do not create traceability, diagrams, use-case output, skill testing, GitHub issues, CHANGELOG, or reflection.

Input files:

- `outputs/reviewed/03-requirements.md`
- `outputs/reviewed/04-user-stories.md`
- `outputs/reviewed/05-prioritization.md`
- `skills/05-validation-change/SKILL.md`

### 3. Raw AI output file

`outputs/raw/validation-ai-output.md`

### 4. Problems found by AI review

- Raw validation marked several incomplete items as PASS without sufficiently preserving OPEN QUESTION status.
- Raw change request recommended ACCEPT for post-deadline resubmission even though deadline and resubmission policies are unresolved.
- Raw change request reason was an ASSUMPTION but was not treated cautiously enough.

### 5. Student review decision

Keep the change request as evidence, but revise the recommendation to NEEDS CLARIFICATION.

### 6. Student corrections applied

- Validated five selected items across all six dimensions and added explicit decisions.
- Kept open policy gaps visible for FR-01, FR-04, FR-07, FR-08, and NFR-01.
- Changed resubmission recommendation from ACCEPT to NEEDS CLARIFICATION.
- Added affected artifacts, impact analysis, risks, uncertainties, and required follow-up updates.

### 7. Reason for each correction

- Validation must not approve requirements by hiding incomplete evidence.
- Resubmission after deadline is outside the official case unless confirmed by policy.
- A change request must include impact analysis and a proposed decision grounded in evidence.

### 8. Final reviewed output file

- `outputs/reviewed/07-validation.md`
- `outputs/reviewed/08-change-request.md`
