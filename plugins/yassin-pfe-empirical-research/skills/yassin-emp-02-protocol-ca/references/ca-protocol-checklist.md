# CA-Protocol Checklist and Issue-Register Schema

Scientific rigour only. Each item: pass, or issue with severity (Critical / Major / Minor) and a required remedy.

## Checklist
1. **Design & standard**  -  design appropriate for the question; the correct reporting standard is bound
   (cross-sectional / cohort / case-control -> STROBE).
2. **Objectives & hypotheses**  -  unambiguous; primary vs secondary explicitly designated; the primary
   outcome is operationally defined.
3. **Population & eligibility**  -  operational and unambiguous inclusion/exclusion.
4. **Sample size**  -  justified **analytically** for the primary association (effect size + source), not only
   as a descriptive target; a **numeric thin-cell threshold** for subgroup comparisons is pre-specified
   (e.g. n >= 10 per group; expected chi2 counts >= 5).
5. **Socle commun**  -  every shared variable present and coded exactly (hard fail otherwise).
6. **Instrument validity**  -  licensing/version; an authorized translation exists or a translation/back-
   translation/pretest plan is specified; a Cronbach-alpha plan; a coherent intention block.
7. **Variable operationalisation**  -  codebook complete; exposure/outcome/confounder tags assigned;
   scoring algorithm and scales specified.
8. **Statistical analysis plan**  -  fully pre-specified; tests match variable types; the missing-data rule is
   **numeric** (named item-level threshold, e.g. >= 70 % items, plus a case-level rule); multiplicity stance
   stated; software named.
9. **Ethics**  -  consent text, voluntariness, anonymity, confidentiality, non-judgmental phrasing, no
   disciplinary use, field authorization; risk assessment present and proportionate.
10. **Review alignment**  -  the protocol measures the indicators the locked review recommended.
11. **Scope discipline**  -  no drift into other components' constructs (migration, burnout, motivation) as the
    primary object.
12. **Consensus depth**  -  `consensus_search_log.json` present, non-empty, documented, and proportionate;
    instrument and effect-size claims traceable to verifiable sources (no fabrication).
13. **Codebook consistency**  -  questionnaire item <-> workbook column <-> codebook variable one-to-one.

## Severity rule
Critical and Major issues block the Protocol Lock; Minor issues may be carried with a recorded justification.

## CA_protocol_register.json
```json
{
  "project_id": "D03-P01",
  "appraised_step": "Yassin_EMP_01_Protocol_V1",
  "appraisal_date": "",
  "summary": {"critical": 0, "major": 0, "minor": 0},
  "issues": [
    {"id": 1, "checklist_item": 4, "severity": "Major",
     "finding": "Sample size justified only as a descriptive target (150-250).",
     "remedy": "Compute power for the satisfaction-intention association using the Consensus-anchored effect size; flag under-powered