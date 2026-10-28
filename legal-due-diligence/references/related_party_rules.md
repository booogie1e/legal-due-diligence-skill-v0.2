# Project-configurable related-party screening rules (v0.2)

## Status and priority
**This document is a configurable screening profile derived from a banking outsourcing due-diligence workflow. It is not a universally applicable statutory definition of “related party” or “related relationship”.** Always obtain the relevant transaction, regulator and commissioning institution's governing standard; record the selected profile, version and deviations. If law and project policy use different scopes, analyze them separately rather than silently merging them.

Profile ID: `BANK_OUTSOURCING_6_CLASSES_V0_2`  
Target: investigated service provider, designated `T`.  
Cut-off date: project-specific; default is `UNSPECIFIED`.  
Decision flags: `SCREENING_MATCH` / `POTENTIAL_MATCH` / `NOT_ENOUGH_INFORMATION` / `NOT_MATCH_ON_AVAILABLE_EVIDENCE`.

## Six screening classes
1. **R1 — Major shareholders / controlling persons of T:** direct or indirect shareholder(s) whose applicable holding meets **5% or more** under the project definition; controlling shareholder(s) of T; actual controller(s) of T. Record whether the threshold tests equity, voting rights or both. *Default profile interprets the 5% threshold as shareholding, while voting influence is independently examined for control; seek project confirmation if ambiguity matters.*
2. **R2 — Entities controlled by T's controlling shareholder or actual controller:** other legal persons or organizations controlled by those persons, beyond T itself.
3. **R3 — Entities controlled by T:** subsidiaries and other legal persons or organizations controlled by T, based on substantiated control criteria.
4. **R4 — Directors, supervisors and senior management of T:** named natural persons holding these roles as at the cut-off date, subject to the company’s applicable governance structure and project requirements.
5. **R5 — Close family members:** close family members of the controlling shareholder, actual controller, 5%+ shareholders and the natural persons in R4, as specifically defined by the project's applicable rules. **Never presume family connections or collect unnecessary personal data.** If the scope of 'close family' is not defined, tag `RULE_DEFINITION_MISSING`.
6. **R6 — Entities associated with R5/R4 or other listed related natural persons:** other legal persons or organizations controlled by those related natural persons, or in which those natural persons hold director or senior-management positions, subject to the commissioning standard. Clarify whether this includes natural persons within R1 and R5; record the scope explicitly.

## Decisions and boundaries
- A `SCREENING_MATCH` means the facts meet an active **project screening category**, not that a statutory legal conclusion has been established under every regulatory regime.
- Where a category is supported only by unverified client statements, label `POTENTIAL_MATCH / PROVIDED_UNVERIFIED` rather than unequivocally confirmed.
- 5% is **inclusive**: 5.0000% meets the default R1 holding test; 4.9999% does not meet the holding threshold alone.
- Do not collapse distinct individuals or companies under aggregate shareholder percentages.
- An entity owning 25% of T may match R1 (project threshold), but does **not** automatically become a statutory controller.
- If a voting proxy or concert-party agreement is relied upon, identify the contract, rights, validity, term, revocation and decision thresholds; keep ownership and voting rights separate.
- A company-level controller is not necessarily the ultimate natural-person controller. Trace until evidence stops and disclose the gap.
- R5/R6 should be flagged as `NOT_ENOUGH_INFORMATION` when personal relationship and position evidence is absent, not automatically 'none'.

## Per-party output fields
`subject_id | subject_name | class_codes | relationship_to_T | holding_pct | voting_pct | factual_test | evidence_ids | evidence_status | screening_decision | open_questions`

## Profile override example
`profile_id: BANK_OUTSOURCING_6_CLASSES_V0_2; threshold: 5% inclusive; close_family_definition: UNSPECIFIED; cut_off_date: YYYY-MM-DD; commissioning_standard: [document name/version]; overrides: []`.
