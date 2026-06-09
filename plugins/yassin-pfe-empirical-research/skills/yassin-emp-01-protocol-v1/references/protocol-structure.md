# Protocol, Questionnaire, and Workbook  -  Build Reference

The codebook is the single source of truth. Build it first, then generate the protocol, questionnaire, and
workbook from it so all three stay consistent.

## 1. Codebook (build first)
One row per variable. Formal fields: `var` (machine name), `label`, `type` (categorical / ordinal / Likert /
numeric / text), `codes` (allowed values), `role` (exposure / outcome / confounder / descriptive / admin),
`instrument` (socle_commun / MSQ-SF / intention / levers / admin), `reverse_coded` (Likert only),
`subscale` (e.g. MSQ intrinsic / extrinsic / general; null when not applicable), `notes`.

`subscale` and `reverse_coded` are first-class fields, **not** free text in `notes`, because Pipeline 2 reads
them directly to compute the MSQ subscale scores and to recode reverse-keyed items. Every workbook column
derives from exactly one codebook row.

## 2. protocole court (French, .docx)  -  mandatory sections
Short in prose but complete enough to be a binding contract.

1. **Titre, auteurs, type d'etude.**
2. **Contexte et justification**  -  condensed from the locked review and Consensus comparators.
3. **Objectifs et hypotheses**  -  primary vs secondary explicitly designated. For D03-P01 the primary
   hypothesis is satisfaction <-> intention de rester; secondary are subgroup differences and levers ranking.
4. **Type d'etude, cadre, population, eligibilite**  -  operational inclusion/exclusion.
5. **Echantillonnage et justification de la taille**  -  upgrade the brief's descriptive target (e.g.
   150-250; min 100) to an **analytic power justification** for the primary association, citing the
   Consensus-anchored effect size. **Pre-specify a numeric thin-cell threshold** for subgroup comparisons
   (default: each compared group n >= 10, and for chi2 expected cell counts >= 5); below it, a comparison is
   declared infeasible/under-powered. This exact number is what emp-04 audits against  -  do not leave it vague.
6. **Variables et codebook**  -  socle commun (exact coding), instrument scoring (MSQ-SF intrinsic /
   extrinsic / general algorithm and scale), the intention block with the primary intention outcome defined,
   the levers MCQ with its ranking rule; each variable tagged exposure / outcome / confounder.
7. **Instrument et plan de traduction**  -  version and **licensing**: the MSQ-SF is copyrighted (University of
   Minnesota / Vocational Psychology Research); confirm authorized use, record the licensing status and exact
   version, and do not reproduce or freely re-translate items without permission. If adaptation is needed:
   forward/back translation, expert review, a pretest with a stated n, no free change of item meaning, a
   Cronbach-alpha plan.
8. **Collecte, gestion et anonymisation des donnees**  -  mode, field authorization, period; anonymised-DB
   structure (no nominative data, no institutional identification).
9. **Plan d'analyse statistique (SAP)**  -  fully pre-specified: descriptives; instrument scoring; Cronbach-alpha;
   the specific primary-association test (e.g. correlation then multivariable regression adjusting named
   confounders); the named subgroup comparisons and their tests; levers ranking; a multiplicity stance; named
   software. The **missing-data rule must be numeric, not generic**: state the item-level threshold (e.g.
   score a subscale only if >= 70 % of its items are answered) *and* the case-level rule (e.g. listwise for the
   regression). emp-05 applies exactly these numbers, so do not leave them implicit.
10. **Considerations ethiques**  -  consent text, voluntariness, anonymity, confidentiality, non-judgmental
    phrasing, no disciplinary use, field authorization, low-risk assessment. **Re-identification guard:**
    fine-grained socle-commun cross-tabs (region x establishment type x service x seniority) can identify
    individuals in small services; commit in the protocol to suppressing or aggregating any reported cell
    below a small-count threshold and to never identifying an individual service, supervisor, or
    establishment in public results.
11. **Calendrier / faisabilite.**
12. **Annexe lisible par machine**  -  the locked parameters as JSON (see schemas.md).

## 3. Questionnaire (field language, .docx)  -  survey best practice
Students have little background here; do the work and apply best practice.
- **Flow:** title + anonymity/voluntariness statement + estimated completion time -> informed-consent gate ->
  eligibility screen -> socle-commun background -> instrument block (MSQ-SF) -> intention-to-stay block ->
  retention-levers MCQ -> thank-you and return instructions.
- **Instrument fidelity:** keep the MSQ-SF intact on its native 5-point Likert; do not change item meaning;
  handle reverse-coded items correctly; present scales consistently.