# Data extraction rules, umbrella review of online harms and disability (v1.1, October 31, 2026)

v1.1 changes after the four-review pilot: which conditions count, which subgroup results to record, how to handle reviews without a meta-analysis, and which column to copy from multi-number tables.

You are one of two extractors working independently. Extract data from each included review assigned to you, using only the text file given for that review. Never guess or fill in from memory. If something is not reported, write null (numbers) or "not reported" (text).

## What you read

Each review has one file in /home/claude/work/extract/texts/<ID>.txt. It holds the record header (ID, DOI, title, the map cells the review was placed in), the abstract from screening, and then either the full text (reference list removed) or a note that only the abstract is available.

- Read the whole full text where there is one. Use the abstract only when the file says no full text is available.
- Do not open any other file except these rules. Do not use the web or any network tool. Do not look in /home/claude/work/extract/out or any other extractor's work.

## What to extract (one JSON object per review)

```
{
 "id": "M001",
 "source_used": "full text" | "abstract only",
 "review_type": "meta-analysis" | "systematic review without meta-analysis" | "scoping review" | "other review",
 "conditions": ["as the review names them"],
 "online_exposures": ["as the review names them, e.g. problematic internet use, cyberbullying victimization"],
 "population_age": "children" | "adolescents" | "children and adolescents" | "young adults" | "adults" | "all ages" | "not reported",
 "population_notes": "short: clinical vs community samples, countries, special groups",
 "last_search_date": "as reported, e.g. 'March 2023'",
 "k_included_total": 42,
 "n_participants_total": 15000,
 "primary_designs": "e.g. 38 cross-sectional, 4 longitudinal",
 "findings": [
   {
    "label": "short name of this result",
    "condition": "the condition in this result",
    "online_side": "the online exposure or outcome in this result",
    "direction": "condition linked to online harm" | "online exposure linked to condition outcome" | "association, no direction" | "prevalence" | "group difference",
    "metric": "r" | "OR" | "RR" | "SMD" | "Hedges g" | "Cohen d" | "prevalence %" | "beta" | "other: <name>",
    "estimate": 0.33,
    "ci_low": 0.25,
    "ci_high": 0.41,
    "p": "as reported, or null",
    "k": 12,
    "n": 5400,
    "i2": 87.5,
    "model": "random effects" | "fixed effect" | "not reported",
    "publication_bias": "test and result, short, or 'not assessed'",
    "certainty": "GRADE or similar rating the authors gave, or 'not rated'",
    "locator": "where it is: section, table or figure, page if shown, plus a verbatim quote of 25 words or fewer that contains the number"
   }
 ],
 "narrative_summary": "for reviews with no pooled estimate (or as a supplement): what was found for the mapped condition and harm, with counts such as '9 of 13 studies found a positive association'. 60 words or fewer.",
 "narrative_locator": "section, table or page of that summary in the review, plus a verbatim quote of 25 words or fewer",
 "author_conclusion": "the authors' main conclusion, paraphrased, 40 words or fewer",
 "rob_tool_used": "the risk of bias or quality tool the review used on its primary studies, or 'none reported'",
 "amstar2": {
   "items": {"1": "Y", "2": "PY", "3": "N", "...": "...", "16": "Y"},
   "critical_flaws": ["item numbers rated N on a critical item, e.g. '7: no list of excluded studies'"],
   "noncritical_weaknesses": ["item numbers rated N or PY on non-critical items"],
   "overall": "High" | "Moderate" | "Low" | "Critically low" | "Not assessable (abstract only)",
   "notes": "short reasons for any judgment call"
 },
 "funding": "as reported, or 'not reported'",
 "conflicts": "as reported, or 'not reported'",
 "extraction_notes": "anything the second extractor or the lead reviewer should know: unclear numbers, errors found in the paper, results reported only in figures"
}
```

### Which findings to record

The conditions that count are the map's condition rows: ADHD; autism; depression; anxiety; PTSD and trauma; OCD; bipolar disorder; eating disorders; body dysmorphia and body image; substance use; gambling; intellectual disability; learning disabilities; brain injury; dementia and cognitive decline; psychosis and schizophrenia; suicidality and self-harm; blind and low vision; deaf and hard of hearing; physical disability; neurological conditions; speech, language, and communication; chronic illness and pain; disability in general. Symptom scales for these count (for example, depressive symptoms). Outcomes outside this list (stress, loneliness, boredom, wellbeing, life satisfaction, self-esteem, negative affect) are not recorded as findings; mention them in one line of extraction_notes.

The online side is any online exposure or online harm (problematic or addictive use, cyberbullying, harmful content, social comparison, gambling and loot boxes, online buying, dark patterns, AI chatbots, sexual exploitation and grooming, misinformation, night-time use, notifications, accessibility barriers, privacy and data, surveillance, online support, general social media or internet use).

Meta-analyses:
- Record the main pooled estimate for every pairing of a counted condition with an online exposure or harm, in either direction. Include null and contrary results the same way as positive ones. Each pairing is its own finding (depression with cyberbullying victimization, and anxiety with cyberbullying victimization, are two findings).
- If the review pools a pairing at more than one level of the exposure (for example overall use, problematic use, and routine use), record each level.
- Subgroups: record only age-group subgroups (for example children versus adults) and clinical versus community sample subgroups. Do not record other subgroups, moderator analyses, or meta-regression coefficients; note any striking one in extraction_notes.
- When a table row prints several numbers (for example a pooled r and a Fisher's z, or an estimate before and after trim-and-fill), record the column the table header labels as the pooled effect, and name that column in the locator.
- At most 12 findings per review; if there are more, keep the main estimates first and say in extraction_notes what was left out.

Systematic reviews without a meta-analysis:
- Record a finding only where the review itself states a result across studies: a pooled, median, or range figure, or a count of studies (record counts as metric "other: count of studies", estimate = the number of studies with the result, k = the number of studies examined, and say which way the result went in the label).
- Do not record single-study figures the review quotes. Put the review's main cross-study conclusion for the mapped condition and harm, with counts, in narrative_summary, and give its place in narrative_locator.
- Copy numbers exactly as printed, with the same decimals. Do not convert one metric into another. Do not compute anything. If a confidence interval is not reported, leave ci_low and ci_high null.
- If a number appears in two places and differs (abstract versus table, for example), record the table value and note the difference in extraction_notes.
- Prevalence reviews: metric "prevalence %", estimate is the pooled prevalence.
- Abstract only: extract whatever the abstract reports, set source_used to "abstract only", and set amstar2.overall to "Not assessable (abstract only)" with every item "NA".

## AMSTAR 2 (Shea et al., 2017, BMJ 358:j4008)

Rate each of the 16 items Y (yes), PY (partial yes), N (no), or NA (not applicable). These reviews mostly synthesize observational studies; apply the items to that design.

1. Research questions and inclusion criteria include the components of PECO (population, exposure, comparator, outcome).
2. (critical) A protocol was established before the review (registered, e.g. PROSPERO or OSF, or stated as written in advance), and the report justifies any significant deviations. PY if a protocol is stated but not registered or deviations are not addressed.
3. The authors explain their choice of study designs for inclusion.
4. (critical) Comprehensive literature search: at least two databases, keywords or search strategy given, and justification of publication restrictions. PY if two or more databases and a search strategy but missing grey literature, reference list searching, or expert contact.
5. Study selection performed in duplicate.
6. Data extraction performed in duplicate.
7. (critical) A list of excluded studies, with reasons, is provided (a flow diagram with reasons alone is PY at best only if exclusions are itemized per study somewhere; a PRISMA flow with counts only is N).
8. Included studies are described in adequate detail (population, exposure, comparator, outcome, design).
9. (critical) A satisfactory technique was used to assess risk of bias in the individual studies (a named tool suited to the designs, e.g. Newcastle-Ottawa, JBI checklists, AXIS). N if none.
10. Funding sources of the included studies are reported.
11. (critical, meta-analyses only; NA otherwise) Appropriate methods for statistical combination: justified model (random effects for heterogeneous observational data), suitable effect metric, heterogeneity assessed.
12. (meta-analyses only) The impact of risk of bias in individual studies on the pooled results was assessed (sensitivity or subgroup analysis by quality).
13. (critical) Risk of bias in individual studies was accounted for when interpreting or discussing the results.
14. Heterogeneity is explained or discussed satisfactorily.
15. (critical, meta-analyses only; NA otherwise) Publication bias was investigated (funnel plot, Egger's test, or similar) and its likely impact discussed.
16. The authors report potential conflicts of interest, including funding for the review.

Critical items: 2, 4, 7, 9, 11, 13, 15.

Overall confidence:
- High: no critical flaw and at most one non-critical weakness.
- Moderate: no critical flaw and more than one non-critical weakness.
- Low: one critical flaw, with or without non-critical weaknesses.
- Critically low: more than one critical flaw, with or without non-critical weaknesses.
A critical flaw is an N on a critical item. A PY on a critical item is not a flaw. A non-critical weakness is an N or PY on a non-critical item (NA does not count).

## Output

Write one JSON array of the review objects, in the order given, to the output path named in your task, using the Write tool. Valid JSON only: no comments, no trailing commas. Then reply with one line: the number of reviews written.
