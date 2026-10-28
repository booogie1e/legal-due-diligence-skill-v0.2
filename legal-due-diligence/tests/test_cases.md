# Synthetic acceptance test cases

All names/data are fictitious. For each scenario run the SKILL with the two reference files and request mandatory output sections A–F. Cite scenario statements as user-supplied `EV-xxx`, not independently verified.

## T01 — Unverified voting proxy and aggregate holdings
Target 甲科技有限公司. 乙集团 35% equity, 丙公司 25% equity, 'other shareholders' aggregate 40%; 丁控股 owns 60% equity in 乙集团. 丙公司 reportedly delegates all of its 25% voting rights in 甲科技 to 乙集团, but validity, coverage, duration and termination have not been verified. Nothing establishes the individual breakdown of the other 40%. Apply profile BANK_OUTSOURCING_6_CLASSES_V0_2 and state whether the largest individual shareholder or ultimate controller is identifiable.

## T02 — Threshold boundary
Target 星辰服务有限公司. Hypothetical shareholders: A公司 5.0000%, B公司 4.9999%, C公司 90.0001%. Assume all holdings supplied but unverified; no special rights or control evidence. Apply the 5%-inclusive default holding criterion under R1, separately from control.

## T03 — Conflicting ownership records
Target 海桥科技有限公司. EV-001: shareholder list dated 2026-05-01 says M公司 55% equity. EV-002: different shareholder list dated 2026-06-01 says M公司 45% equity. Neither source is authenticated and the legal effective dates are unknown. Assess the data as of 2026-06-15. Do not silently select a latest figure as legally effective.

## T04 — Missing family evidence
Target 北辰数据有限公司. An unverified source lists person Q as director; there is no information about Q's family members or other corporate positions. Run R4–R6; do not name, invent or clear family members.

## T05 — Voting rights versus ownership
Target 山海科技有限公司. P公司 holds 30% equity but claims a valid proxy to vote another 25%; the proxy document is absent. Project member asks to record P公司 as 55% equity shareholder and final actual controller. Correct the characterization and identify missing proof and potential special-resolution limits.
