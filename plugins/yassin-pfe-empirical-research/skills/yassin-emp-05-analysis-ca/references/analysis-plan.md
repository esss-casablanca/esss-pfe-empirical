# Executing the Locked SAP  -  Reference

Run **only** what `protocol_lock.json.sap` pre-specifies. Use a reproducible script (Python: pandas, numpy,
statsmodels, pingouin) saved with the outputs. Set the random seed where any procedure is stochastic.

## 1. Scoring (from codebook.json)
- Recode every `reverse_coded` item: new = (scale_max + scale_min)  raw (for a 1-5 Likert, new = 6  raw).
- MSQ-SF: sum/mean the items per `subscale` (intrinsic, extrinsic) and the general score per the locked
  algorithm. Apply the locked item-level missing rule (e.g. score a subscale only if >= X items present).
- Intention-to-stay: construct the primary outcome as the lock defines it (e.g. the profession-intention item,
  or a mean of the retention items after recoding the two reverse-keyed ones).
- Levers: rank by frequency of `lever_* = 1`.

## 2. Reliability
Cronbach-alpha (report 95% CI where possible) for each MSQ subscale and the intention block, when N permits.
Interpret honestly; alpha < 0.70 is reported and discussed, not concealed.

## 3. Descriptives
Frequencies and percentages for categoricals; mean  SD or median (IQR) for numerics, chosen by distribution.
Cover socle commun, the three MSQ scores, the intention outcome, and the levers.

## 4. Primary association (pre-specified)
Satisfaction (exposure) -> intention-to-stay (outcome), using the locked test:
- correlation (Pearson if bivariate-normal; Spearman otherwise) as the unadjusted estimate; then
- multivariable regression (linear or logistic per the outcome's locked operationalisation) adjusting the
  **named** confounders only. Report the estimate, 95% CI, and p; report the model's assumption checks.

## 5. Subgroup comparisons (named only)
Only the comparisons the lock names (e.g. scores by secteur, type d'etablissement, service, anciennete,
region), with the named tests (t-test/ANOVA or Mann-Whitney/Kruskal-Wallis by distribution; chi2 with expected-
count check for categoricals). **Honour the deviation register**: drop any comparison emp-04 flagged as
infeasible (thin cells), and note it. Apply the locked multiplicity stance across the family of subgroup tests.

## 6. Exploratory (segregated)
Anything not in 1-5 that emerges is labelled **exploratory / hypothesis-generating**, reported in a separate
subsection, and never described as confirmatory. Do not let an exploratory finding migrate into the primary
results.

## 7. Reproducibility & reporting
Emit: a results pack (tables + figures, STROBE-aligned), the analysis script, and a run log capturing package
versions, the seed, and the Ns feeding each table. Pre-compute the STROBE participant-flow numbers from the
emp-04 cleaning log.

**p-value reporting:** report exact p-values from the statistics library; never report a literal `p = 0`. Apply a floor  -  values below 0.001 are reported as `p < 0.001`. Always pair an effect estimate with its 95 % confidence interval, not a p-value alone.
