# Empirical Manuscript (IMRaD / STROBE)  -  Build Reference

Write English-primary; offer a French companion. Every number, table, and citation is fixed by the locks  - 
write around them.

## Title & abstract
- Title names the design and the **achieved** population (reconcile to the real sample, not the brief's
  aspiration).
- Structured abstract: Background, Methods, Results (key numbers from `results_lock.json`), Conclusions.

## Introduction (from the locked review + Consensus)
Three moves: why the topic matters (workforce/retention), what is known (the locked review's synthesis +
current Consensus comparators), the gap and the Moroccan rationale. End with the pre-specified objectives and
the primary hypothesis (satisfaction -> intention-to-stay).

## Methods (from protocol_lock.json  -  STROBE items 4-12)
- Study design named; setting and dates; eligibility criteria.
- Variables: exposures, outcomes, confounders, effect modifiers; the MSQ-SF and intention block with scoring.
- Data sources/measurement; bias; study size (the analytic power justification); quantitative variable
  handling.
- Statistical methods exactly as locked, including the missing-data rule and multiplicity stance.
- **Deviations disclosed**: summarise `deviation_register.json` honestly (achieved N, dropped comparisons).
- Ethics statement: approval/authorization, consent, anonymity.

## Results (from results_lock.json only)
- Participant flow (STROBE item 13) from the lock.
- Descriptives (item 14): socle commun, scores, intention, levers.
- Reliability (alpha).
- Main result (items 15-16): the primary association with estimate, 95 % CI, and p (p-value floor `p < 0.001`).
- Named subgroup results.
- **Exploratory findings in their own subsection**, labelled non-confirmatory.
- Do not interpret here.

## Discussion (STROBE items 18-21)
Key results vs the locked review and Consensus comparators; limitations (cross-sectional -> association not
causation; self-report/common-method bias; single-country generalisability; deviations; any under-powered
comparison); implications for nurse retention; a conclusion proportionate to certainty.

## Companion deliverables
- **rapport final** (FR): the same evidence in a fuller institutional report for the defense.
- **presentation orale** (pptx): background, methods, key results, implications  -  locked numbers only.

## Integrity invariants (self-check before handing off)
- Every Results number traces to `results_lock.json`; every Methods detail to `protocol_lock.json`.
- No causal language for a cross-sectional design.
- Title matches the achieved sample.
- Exploratory clearly separated from confirmatory.
