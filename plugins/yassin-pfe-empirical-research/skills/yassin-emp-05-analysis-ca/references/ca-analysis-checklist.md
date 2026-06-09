# CA-Analysis Checklist and Issue-Register Schema

Scientific rigour only. Each item: pass, or issue with severity (Critical / Major / Minor) and a required remedy.

## Checklist
1. **Test correctness**  -  each test matches the variable types and the question (continuous vs ordinal vs
   categorical; paired vs unpaired).
2. **Assumptions checked**  -  normality where assumed, homoscedasticity, multicollinearity (VIF) in regression,
   expected cell counts for chi2 (use exact tests when sparse).
3. **Missing data**  -  handled exactly as the lock specifies; Ns reported at each step; no ad-hoc imputation.
4. **Multiplicity**  -  the locked stance applied across the subgroup-test family; no silent multiple testing.
5. **Fidelity to the SAP**  -  every primary/secondary result corresponds to a pre-specified analysis;
   exploratory results are cleanly separated and labelled.
6. **Scoring correctness**  -  reverse-coding applied; subscales computed per algorithm; item-missing rule applied.
7. **Reliability**  -  alpha (and omega where used) reported with interpretation; low values discussed, not hidden.
8. **Internal consistency**  -  Ns reconcile across tables; percentages sum; table values match the script output.
9. **Anonymisation / small cells**  -  re-identification guard honoured; cells below the threshold suppressed or
   aggregated in any reported table.
10. **Deviation handling**  -  each deviation in the register is reflected (dropped comparison, widened CI,
    limitation), not silently ignored.
11. **STROBE results readiness**  -  participant flow available; descriptive results precede analytic; effect
    estimates carry CIs; p-values reported exactly with a `p < 0.001` floor (never a literal `p = 0`).
12. **Consensus benchmarking**  -  obtained values compared to comparable studies; implausible results
    investigated; `consensus_search_log.json` present and proportionate.

## Severity rule
Critical and Major issues block the Results Lock; Minor issues may be carried with a recorded justification.

## CA_analysis_register.json
```json
{
  "project_id": "D03-P01",
  "appraised_step": "Yassin_EMP_05_Analysis_CA",
  "summary": {"critical": 0, "major": 0, "minor": 0},
  "issues": [
    {"id": 1, "checklist_item": 2, "severity": "Major",
     "finding": "Regression reported without multicollinearity check among MSQ subscales.",
     "remedy": "Report VIF; if high, use the general score or justify the specification.",
     "status": "open"}
  ]
}
```
Every issue carries `id