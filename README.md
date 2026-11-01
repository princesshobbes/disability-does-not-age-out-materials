# Disability Does Not Age Out: materials

These are the materials behind "Disability Does Not Age Out: An Umbrella Review and Evidence and Gap Map of Online Harms Across Disability and Mental Health Conditions" (Travis Gilly, Real Safety AI Foundation), version 2, November 1, 2026.

Full texts of the mapped studies are not included, because most are under publishers' copyright. Every record carries its DOI or a link to its source.

## How to cite

Gilly, T. (2026). *Materials for "Disability Does Not Age Out"* (Version 2) [Data set]. Real Safety AI Foundation. https://github.com/princesshobbes/disability-does-not-age-out-materials/releases/tag/v2

## Contents

- `data/Online_Harms_Disability_Evidence_Ledger.xlsx`: the evidence ledger of 2,874 records. It holds the condition and harm groups, key findings, flags, the companion shortlist, review overlap, and both screening sheets. The Read me tab gives the history of every change.
- `data/Umbrella_Review_Extraction_Appendix.xlsx`: the settled extraction of the 276 included reviews. It holds 708 findings, each with a locator and a verbatim quote of 25 words or fewer, along with AMSTAR 2 item ratings, the settling record, and the findings set aside with reasons.
- `data/evidence_map_data.json`: the data behind the interactive evidence map.
- `protocols/`: the screening rules (version 1.2) and the extraction rules (version 1.1).
- `logs/screening/`: each screener's decision on every meta-analysis and systematic review, plus the resolutions of disagreements.
- `logs/extraction/`: each extractor's blind extraction of every review before settling, plus the settling record and the findings set aside.
- `logs/version2_M184/`: the two blind screening decisions and the two blind extractions for the meta-analysis added in version 2 (Iregbu et al., 2026).
- `checks/`: the November 1, 2026 link check of every DOI and link on the map.

## Who did what

Travis Gilly designed and approved the methodology, the scope, the rule sets and the guidelines, and settled every screening and extraction disagreement.

Claude Opus 5.5 (Anthropic) did three things:
- wrote and ran the code;
- ran the screening and extraction agents, in a multi-agent blind review where separate agents received only the rules, the records and the instruction;
- decided the 37 extraction items that the rules did not settle, at the author's request. Each of those decisions is logged with its reason.
