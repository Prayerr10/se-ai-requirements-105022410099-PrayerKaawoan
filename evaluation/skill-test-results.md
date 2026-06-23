# Skill Test Results

## Test Objective

Pengujian ini dilakukan untuk membuktikan bahwa reusable AI skills dapat digunakan pada kasus berbeda tanpa mengubah artefak utama Student Task Management System. Test input dibuat terisolasi di dokumen ini. Pengujian dilakukan pada branch `development` menggunakan agent utama saja.

Artefak utama yang tidak diubah dalam Tahap G:

- `CASE.md`
- `inputs/`
- `outputs/`
- `diagrams/`
- `README.md`
- `skills/02-elicitation/`
- `skills/04-prioritization/`
- `skills/05-validation-change/`

## Test 1 — Skill 1: Clinic Appointment System

### Test Input

#### Official Case Text

- `FACT`: Patients request medical appointments.
- `FACT`: Doctors publish available appointment slots.
- `FACT`: Clinic staff manage doctor schedules and patient records.
- `FACT`: The system must reduce double booking and missed appointments.

#### Stakeholder Notes

- `FACT`: Patients need to request appointments.
- `FACT`: Doctors need to publish appointment slots.
- `FACT`: Clinic staff need to manage doctor schedules and patient records.
- `ASSUMPTION`: Patients may want appointment confirmation.
- `ASSUMPTION`: Doctors may want appointment slots to reflect actual availability.
- `ASSUMPTION`: Clinic staff may want schedule conflicts to be visible.

#### Assumptions Register

- `FACT`: The known stakeholders are Patients, Doctors, and Clinic staff.
- `CONSTRAINT`: Test output must not create requirements, user stories, diagrams, prioritization, traceability, validation, or change requests.
- `CONSTRAINT`: Additional details such as notification method, cancellation policy, appointment duration, or authentication method are not confirmed.
- `OPEN QUESTION`: What appointment confirmation method is used?
- `OPEN QUESTION`: What cancellation or rescheduling policy applies?
- `OPEN QUESTION`: What standard appointment duration is used?
- `OPEN QUESTION`: What authentication method is required?

### Invocation

Use `skills/01-inception/SKILL.md` to run Project Inception and Stakeholder Discovery for the Clinic Appointment System. Use only the isolated test input in this section. Preserve `FACT`, `ASSUMPTION`, `CONSTRAINT`, and `OPEN QUESTION`. Do not create requirements or downstream artifacts.

### Skill Version Before Revision

Tested version before revision was the Tahap C/D version of `skills/01-inception/SKILL.md`.

Relevant instruction behavior before revision:

- Inputs specifically referenced stakeholder notes for Lecturer, Student, and Administrator.
- Required context said to preserve Lecturer, Student, and Administrator.
- Workflow normalized stakeholder names to Lecturer, Student, and Administrator.
- Quality checks expected Lecturer, Student, and Administrator to appear consistently.

### Initial Result

Initial run was risky for a non-assignment case. The skill either had to stop because Clinic stakeholder terminology could not be reconciled with Lecturer, Student, and Administrator, or produce an incorrect draft by forcing Clinic roles into assignment roles.

Representative initial output risk:

```markdown
## Stakeholder Analysis
### Lecturer
- `FACT`: Doctors publish available appointment slots.

### Student
- `FACT`: Patients request medical appointments.

### Administrator
- `FACT`: Clinic staff manage doctor schedules and patient records.
```

The content above is not acceptable because it renames sourced Clinic stakeholders into assignment-specific roles.

### What Worked

- The skill correctly required evidence labels.
- The skill correctly prohibited downstream artifacts such as requirements, user stories, diagrams, traceability, prioritization, validation, and change requests.
- The skill correctly treated unconfirmed details such as cancellation policy and authentication method as `OPEN QUESTION`.
- The skill discouraged unsupported features such as reminders, telemedicine, payment, or insurance integration unless labeled.

### Problems or Failure Cases

- Stakeholder names were not reusable because the instructions were hardcoded to Lecturer, Student, and Administrator.
- A non-assignment case could fail even when it had clear stakeholders.
- The skill could encourage invalid role mapping from Patients to Student, Doctors to Lecturer, and Clinic staff to Administrator.

### Root Cause in Skill Instructions

The root cause was assignment-specific stakeholder wording in `Inputs`, `Required Context`, `Workflow`, `Output Format`, `Rules`, `Quality Checks`, and `Failure Conditions`. Those instructions were correct for the Student Task Management System assignment but too narrow for reusable skill testing.

### Skill Revision Applied

Revised `skills/01-inception/SKILL.md` and `skills/01-inception/examples.md`.

Changes applied:

- Replaced fixed stakeholder assumptions with "stakeholders named in the case."
- Preserved the special assignment rule: for Student Task Management System, use Lecturer, Student, and Administrator exactly.
- Changed output format placeholders from fixed role names to `<Stakeholder 1>`, `<Stakeholder 2>`, and `<Stakeholder 3>`.
- Updated quality checks and failure conditions so they validate sourced stakeholder consistency instead of fixed role names.
- Added a reuse example note warning not to add reminders, telemedicine, payment, or insurance integration unless sourced or explicitly labeled.

### Rerun Result

After revision, the skill produced a reusable inception draft using the Clinic roles as supplied.

Representative rerun output:

```markdown
# Project Inception and Stakeholder Discovery

## Case Context
- `FACT`: Clinic Appointment System supports appointment requests, doctor slot publication, schedule management, and patient record management.
- `FACT`: The system must reduce double booking and missed appointments.

## Stakeholder Analysis

### Patients
#### Needs
- `FACT`: Request medical appointments.
#### Interests
- `ASSUMPTION`: Receive appointment confirmation.
#### Information Gaps
- `OPEN QUESTION`: What confirmation method is used?

### Doctors
#### Needs
- `FACT`: Publish available appointment slots.
#### Interests
- `ASSUMPTION`: Keep published slots aligned with actual availability.
#### Information Gaps
- `OPEN QUESTION`: What appointment duration is used?

### Clinic staff
#### Needs
- `FACT`: Manage doctor schedules and patient records.
#### Interests
- `ASSUMPTION`: See possible schedule conflicts.
#### Information Gaps
- `OPEN QUESTION`: What cancellation or rescheduling policy applies?

## Scope Boundaries
### In Scope
- `FACT`: Appointment request.
- `FACT`: Doctor slot publication.
- `FACT`: Doctor schedule and patient record management.
- `FACT`: Reduction of double booking and missed appointments.

### Unresolved
- `OPEN QUESTION`: Notification method.
- `OPEN QUESTION`: Cancellation policy.
- `OPEN QUESTION`: Appointment duration.
- `OPEN QUESTION`: Authentication method.

## Handoff to Elicitation
- Ask Patients about appointment request and confirmation expectations.
- Ask Doctors about slot publication and appointment duration rules.
- Ask Clinic staff about schedule conflict handling and patient record management.
```

The rerun did not add reminders, telemedicine, payment, or insurance integration as facts.

### Comparison Before and After

| Aspect | Before Revision | After Revision |
|---|---|---|
| Stakeholder names | Forced or expected Lecturer, Student, Administrator | Preserves Patients, Doctors, Clinic staff |
| Reusability | Weak for non-assignment cases | Stronger for sourced stakeholder roles |
| Unsupported features | Generally discouraged | Explicitly warns not to add Clinic-specific unsupported features |
| Output status | Risk of invalid role mapping | Clear FACT/ASSUMPTION/CONSTRAINT/OPEN QUESTION separation |

### Student Review Decision

Accept the revision. The change improves reusable behavior without weakening assignment compliance because the Student Task Management System rule remains explicit.

## Test 2 — Skill 3: Library Reservation System

### Test Input

#### Reviewed Elicitation Summary

- `FACT`: Members search library materials.
- `FACT`: Members reserve available materials.
- `FACT`: Librarians manage catalog records and reservation status.
- `FACT`: The system must prevent duplicate reservations for the same available item.

#### Elicitation Findings

| Finding ID | Stakeholder | Need or Observation | Evidence Label |
|---|---|---|---|
| LIB-EL-01 | Member | Search library materials. | FACT |
| LIB-EL-02 | Member | Reserve available materials. | FACT |
| LIB-EL-03 | Librarian | Manage catalog records. | FACT |
| LIB-EL-04 | Librarian | Manage reservation status. | FACT |
| LIB-EL-05 | Member, Librarian | Prevent duplicate reservations for the same available item. | FACT |

#### Constraints and Open Questions

- `CONSTRAINT`: Test output must create only requirements and user story drafts.
- `CONSTRAINT`: Do not create prioritization, validation, diagrams, traceability, or change requests.
- `ASSUMPTION`: A reservation confirmation may be shown after a reservation is recorded.
- `ASSUMPTION`: Account verification may be needed before reservation.
- `OPEN QUESTION`: What reservation period applies?
- `OPEN QUESTION`: What fine policy applies?
- `OPEN QUESTION`: What notification method is used?
- `OPEN QUESTION`: What account verification method is required?

### Invocation

Use `skills/03-specification/SKILL.md` to run Requirements Elaboration and Specification for the Library Reservation System. Use only the isolated test input in this section as reviewed elicitation evidence. Produce draft requirements and user stories only. Do not prioritize, validate, create diagrams, create traceability, or create change requests.

### Skill Version Before Revision

Tested version before revision was the Tahap C/D version of `skills/03-specification/SKILL.md`.

Relevant instruction behavior before revision:

- Required context said to preserve Lecturer, Student, and Administrator.
- User story template restricted role examples to `<Lecturer | Student | Administrator>`.
- Rules allowed additional roles only if explicitly sourced, but this conflicted with earlier assignment-specific wording.

### Initial Result

Initial run was structurally strong but risky for stakeholder naming in a different domain.

Representative initial output risk:

```markdown
### US-01 — Search materials
- Story: As a Student, I want to search library materials, so that I can find items to reserve.
```

The role `Student` is not present in the Library test input. The sourced role is `Member`.

### What Worked

- The skill generated sequential FR IDs.
- The skill required NFRs to include measurable thresholds and verification methods.
- The skill required at least two business rules.
- The skill required user stories in `As a... I want... so that...` format.
- The skill required at least two acceptance criteria per user story.
- The skill prohibited prioritization, validation, diagrams, traceability, and change requests.

### Problems or Failure Cases

- The user story template could lead to wrong role names for Library Reservation System.
- The Required Context wording could make a reusable test case appear invalid because it did not contain Lecturer, Student, and Administrator.
- The instruction conflict increased risk of false certainty or role substitution.

### Root Cause in Skill Instructions

The root cause was assignment-specific stakeholder wording in `Required Context`, `Output Format`, and `Rules`. The skill already had strong NFR and ambiguity checks, so no revision was needed for measurable/testable wording.

### Skill Revision Applied

Revised `skills/03-specification/SKILL.md` and `skills/03-specification/examples.md`.

Changes applied:

- Required stakeholder roles to be preserved exactly from reviewed elicitation evidence.
- Kept the Student Task Management System special case: Lecturer, Student, and Administrator.
- Changed user story template from assignment-specific role choices to `<sourced stakeholder role>`.
- Added quality check that every user story uses a stakeholder role from reviewed elicitation.
- Added failure condition when stakeholder roles cannot be identified from reviewed evidence.
- Added reuse example note for Library Reservation System using Member and Librarian.

### Rerun Result

After revision, the skill produced Library requirements using sourced roles and kept unsupported details labeled.

Representative rerun output:

```markdown
Artifact: outputs/reviewed/03-requirements.md

### FR-01 — Search library materials
- Statement: The system shall allow Member to search library materials.
- Stakeholder: Member
- Source: LIB-EL-01
- Status: FACT

### FR-02 — Reserve available material
- Statement: The system shall allow Member to reserve an available library material.
- Stakeholder: Member
- Source: LIB-EL-02
- Status: FACT

### FR-03 — Manage catalog records
- Statement: The system shall allow Librarian to manage catalog records.
- Stakeholder: Librarian
- Source: LIB-EL-03
- Status: FACT

### FR-04 — Manage reservation status
- Statement: The system shall allow Librarian to manage reservation status.
- Stakeholder: Librarian
- Source: LIB-EL-04
- Status: FACT

### BR-01 — Duplicate reservation prevention
- Rule: The system shall not allow duplicate reservations for the same available item.
- Source: LIB-EL-05
- Status: FACT

### NFR-01 — Search response time
- Statement: Under an agreed test workload, the system shall return search results within 2 seconds for at least 95% of search requests.
- Measure and threshold: Response time <= 2 seconds for >= 95% of search requests.
- Operating context: `ASSUMPTION` — workload is not yet defined.
- Verification method: Performance test using agreed workload.
- Source: LIB-EL-01
- Status: ASSUMPTION
```

```markdown
Artifact: outputs/reviewed/04-user-stories.md

### US-01 — Search library materials
- Story: As a Member, I want to search library materials, so that I can find items to reserve.
- Supports: FR-01
- Source: LIB-EL-01
- Status: FACT
#### Acceptance Criteria
- AC-US01-01: Given a Member and search criteria, when the Member submits the search, then the system displays matching library materials.
- AC-US01-02: Given no matching materials, when the Member submits the search, then the system displays an empty result state.
```

The rerun did not create fine policy, notification method, account verification method, or reservation period as facts. Those remained `ASSUMPTION` or `OPEN QUESTION`.

### Comparison Before and After

| Aspect | Before Revision | After Revision |
|---|---|---|
| Stakeholder names | Risk of Student/Lecturer/Administrator substitution | Preserves Member and Librarian |
| FR IDs | Sequential | Sequential |
| NFR quality | Measurable/testable | Measurable/testable |
| Unsupported features | Generally labeled | More clearly guarded by sourced-role rule |
| User story roles | Risk of wrong role vocabulary | Uses roles from reviewed elicitation |

### Student Review Decision

Accept the revision. The change fixes a reusable-skill weakness and keeps all original quality checks for sequential IDs, measurable NFRs, business rules, user stories, and acceptance criteria.

## Overall Findings

- Skill 1 can be reused after revision because it now derives stakeholder names from the case instead of assuming only Lecturer, Student, and Administrator.
- Skill 3 can be reused after revision because it now preserves stakeholder roles from reviewed elicitation evidence.
- The most important quality improvement was replacing assignment-specific stakeholder constraints with sourced stakeholder constraints while preserving the special Student Task Management System rule.
- Human review is still required to decide whether assumptions should become confirmed requirements.
- Missing policy details such as cancellation rules, reservation period, notification method, authentication method, account verification, and fine policy must remain `ASSUMPTION` or `OPEN QUESTION`.
- Main Student Task Management System artifacts were not changed during Tahap G.
