# CA-Manuscript Checklist and Issue-Register Schema

Scientific reporting rigour only (not style, not AI-likeness). Each item: pass, or issue with severity and remedy.

## Checklist
1. **STROBE  -  Title/Abstract**  -  design in the title; informative structured abstract.
2. **STROBE  -  Introduction**  -  background/rationale; specific objectives and the pre-specified hypothesis.
3. **STROBE  -  Methods**  -  design, setting, participants, variables, data sources, bias, study size,
   statistical methods, missing-data handling  -  all present and matching `protocol_lock.json`.
4. **STROBE  -  Results**  -  participant flow, descriptive data, outcome data, main results with CIs, subgroup
   analyses  -  all matching `results_lock.json` (spot-check each reported value).
5. **STROBE  -  Discussion**  -  key results, limitations, interpretation, generalisability.
6. **Methods fidelity**  -  no methods detail contradicts the Protocol Lock.
7. **Results fidelity (exhaustive)**  -  perform a **complete number-by-number reconciliation**, not a
   spot-check: every figure in the abstract, text, tables, and figures traces to exactly one value in the
   Results Lock; no new or altered statistic. Build a reconciliation table (manuscript value <-> lock value <->
   match?) and attach it; any unmatched or mismatched value is a Critical break.
8. **Claim-data support**  -  every assertion is supported; nothing overstated.
9. **No causal overreach**  -  cross-sectional results are associations, never causes.
10. **Limitations adequacy**  -  design, self-report/common-method bias, single-country generalisability, and
    each material deviation are acknowledged.
11. **Citation verification**  -  references verified against Consensus; comparators current; none fabricated.
12. **Title-sample match**  -  the title reflects the achieved sample.
13. **Exploratory separation**  -  exploratory findings are labelled and not used to support primary conclusions.

## Severity rule
Critical (fidelity break; fabricated citation; causal overreach in conclusions) and Major issues are resolved
in emp-10 before peer review proceeds to a clean draft; Minor issues may be carried with justification.

## CA_manuscript_register.json
```json
{
  "project_id": "D03-P01",
  "appraised_step": "Yassin_EMP_07_Manuscript_V1",
  "summary": {"critical": 0, "major": 0, "minor": 0},
  "issues": [
    {"id": 1, "checklist_item": 9, "severity": "Critical",
     "finding": "Discussion s