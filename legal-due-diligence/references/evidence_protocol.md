# Evidence and conclusions protocol (v0.2)

## Evidence registry
Assign immutable IDs `EV-001`, `EV-002`, ... to each document or factual assertion. Store:
- ID, document/statement title and issuing party
- acquisition method (user-supplied, official registry, disclosure, interview, etc.)
- document date, effective date if different, and retrieval date
- exact page / clause / URL / registry record identifier as actually available
- authenticity/independence checks actually completed (if none, say so)
- confidentiality classification (public, internal, restricted); never publish restricted material
- extracted factual proposition(s), scope/limitations, contradictory evidence IDs

## Claim status taxonomy
- `VERIFIED`: supported by relevant, reliable evidence whose stated proposition and currency were actually checked; name checks performed. A user assertion alone is not VERIFIED.
- `PROVIDED_UNVERIFIED`: supplied by user/third party but not independently corroborated.
- `INFERRED_CONDITIONAL`: logical or legal inference dependent on expressly stated conditions.
- `CONFLICTED`: contradictory evidence requiring reconciliation.
- `NOT_DETERMINABLE`: cannot conclude from available evidence.
- `LEGAL_SOURCE_NOT_VERIFIED`: legal text or version not independently checked where needed.

## Conclusion mapping
For each material conclusion assign `CL-001`, etc.: `conclusion | rule/profile | evidence_ids | chain_of_reasoning_summary | conditions | status | missing_evidence`. An inference is not the same as a recorded fact. Use explicit `NO_SUPPORTING_DOCUMENT` when none exists.

## Consistency checks
1. Compare equity percentages by ownership class, same company and cut-off date; do not sum across tiers or mix dates.
2. Voting rights may diverge; record each transfer, delegation and validity. Don't infer voting control solely from the product of ownership percentages.
3. Where 'other shareholders' is aggregate, ranking of individual shareholders is `NOT_DETERMINABLE` unless separately known.
4. If two documents disagree about a percentage, status or effective date, log both IDs and mark `CONFLICTED` pending reconciliation.
5. Avoid false precision and unverified 'current' descriptions; a historical filing is not necessarily current.
6. Legal claims require exact provision and applicable version; if unverified, mark it rather than inventing a citation.

## Missing-evidence requests
Use `P0` for issues that could reverse the central conclusion; `P1` for major due diligence gaps; `P2` for supporting/secondary gaps. For each request record owner, requested item, purpose and conclusion affected. These priorities are internal workflow conventions only.

## Publication safeguard
Use fictional data for public tests. Never publish client names, contracts, confidential reports, account details or identifiable private persons. Check metadata and Git history before publishing. Rewriting a current file does not necessarily remove secrets from past Git commits.
