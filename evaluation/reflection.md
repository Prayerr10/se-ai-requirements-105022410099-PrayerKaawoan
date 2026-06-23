# Reflection

## 1. What did AI do best in the Requirements Engineering process?

AI was most useful for producing structured drafts and keeping the Requirements Engineering workflow organized across several artifacts. The repository evidence shows that AI helped generate draft outputs for inception, elicitation, requirements specification, prioritization, validation, and change management in `outputs/raw/`. It also helped organize reviewed artifacts in `outputs/reviewed/`, including functional requirements, non-functional requirements, business rules, user stories, use cases, prioritization, validation, change request analysis, and the traceability matrix.

AI was also useful as a review aid. `evaluation/ai-output-review.md` documents that AI output review helped identify issues such as unsupported scope exclusions, reminder behavior without source evidence, vague NFR wording, incomplete acceptance criteria, and premature validation decisions. These findings made the review process more systematic.

## 2. What errors or assumptions did AI make most often?

The most common problem was treating unsupported or unclear information too confidently. `evaluation/ai-output-review.md` records several examples:

- Raw inception output placed campus integrations in Out of Scope even though the case did not explicitly exclude integrations.
- Raw elicitation output included deadline reminders as an implicit Student need even though reminder functionality was not in the official case.
- Raw specification output used vague wording such as "respond quickly" and needed measurable NFR thresholds and verification methods.
- Raw prioritization output treated feedback as Must without enough rationale for first-iteration priority.
- Raw validation and change-management output recommended accepting post-deadline resubmission even though deadline and resubmission policy remained unresolved.

`evaluation/skill-test-results.md` also shows that reusable skills initially contained assignment-specific role assumptions. Skill 1 risked forcing Clinic Appointment System stakeholders into Lecturer, Student, and Administrator. Skill 3 risked using `Student` for a Library Reservation System user story even when the sourced role was `Member`.

## 3. How did changes to SKILL.md improve output quality?

The Tahap G skill revisions improved reusable behavior by removing assignment-specific stakeholder assumptions while preserving the Student Task Management System rule for the main assignment.

For Skill 1, `skills/01-inception/SKILL.md` was revised so stakeholder names are derived from the supplied case. The rerun documented in `evaluation/skill-test-results.md` preserved Patients, Doctors, and Clinic staff for the Clinic Appointment System instead of forcing Lecturer, Student, and Administrator.

For Skill 3, `skills/03-specification/SKILL.md` was revised so user stories use stakeholder roles from reviewed elicitation evidence. The rerun preserved Member and Librarian for the Library Reservation System. The revision also added checks to prevent user stories from using roles that are not supported by the reviewed evidence.

These changes improved output quality because the skills became more reusable, reduced unsupported role substitution, and made stakeholder terminology more traceable.

## 4. Why is human review still required even when AI follows workflow and quality checks?

Human review is still required because several decisions depend on judgment and source interpretation, not only formatting. In this project, the student review rejected unsupported features, preserved uncertainty, and decided which corrections should be applied.

Examples from `evaluation/ai-output-review.md` include:

- The student rejected deadline reminders as a confirmed need because the official case did not mention reminders.
- The student required vague NFR wording to be replaced with measurable thresholds and verification methods.
- The student kept administrative operations and NFR thresholds labeled as `ASSUMPTION` where the case did not confirm details.
- The student changed the resubmission change request recommendation from ACCEPT to NEEDS CLARIFICATION because the policy was not confirmed.

AI can draft and check structure, but the student remains responsible for the reviewed baseline, evidence interpretation, and final submission quality.

## 5. How does traceability help maintain consistency across requirements artifacts?

Traceability helps show whether each requirement is connected to evidence and downstream artifacts. `outputs/reviewed/requirements-traceability.md` maps every FR from FR-01 through FR-10 to stakeholder, elicitation source, user story, acceptance criteria, MoSCoW priority, use case, and validation reference where available.

This makes consistency easier to maintain because a change to one requirement can be checked against related artifacts. For example, the late submission and resubmission change request affects FR-02, FR-04, FR-05, US-04, US-05, prioritization entries CF-03 and DEC-04, use cases UC-04 and UC-05, validation, and traceability. Without a traceability matrix, those dependencies would be easier to miss.

Traceability also keeps unresolved information visible. Several rows in the matrix include `OPEN QUESTION` or `ASSUMPTION` notes so unconfirmed details are not accidentally treated as final requirements.

## Student Accountability Statement

AI was used to generate drafts and assist with review. Raw AI outputs were stored in `outputs/raw/` and were not edited after creation. The reviewed outputs in `outputs/reviewed/` document student-directed review decisions, corrections, and final artifacts.

The student reviewed AI-generated material, decided which corrections to accept or reject, directed revisions, and remains responsible for the final repository contents and assignment submission.
