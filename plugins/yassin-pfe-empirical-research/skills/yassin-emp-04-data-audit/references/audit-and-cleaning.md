# Adherence Audit & Data Cleaning  -  Reference

## Adherence audit dimensions (-> deviation_register.json)
| Dimension | Check | Typical severity |
|-----------|-------|------------------|
| Achieved N | vs `sample_size.target_min/hard_min` in lock | < hard_min -> Major; any subgroup cell below the **locked thin-cell threshold** (default n >= 10; expected chi2 counts >= 5) -> Major for that comparison |
| Socle commun | every shared var present, coded per codebook | off-code / free text -> Major; missing var -> Critical |
| Instrument | item count, scale, wording match locked instrument | added/dropped/reworded item -> Major; undeclared -> Critical |
| Scope | no excluded constructs collected | drift -> Minor-Major |
| Amendments | each declared, dated, justified | undeclared change to frozen element -> Critical |
| Data integrity | duplicates, impossible values, ID uniqueness | case-by-case |

## deviation_register.json
```json
{
  "project_id": "D03-P01",
  "protocol_lock_ref": "<id>",
  "achieved_n": 0,
  "summary": {"critical": 0, "major": 0, "minor": 0},
  "deviations": [
    {"id": 1, "dimension": "achieved_n", "severity": "Major",
     "finding": "N=92 below hard_min=100.",
     "sap_impact": "Primary association under-powered for r<=0.25; subgroup comparisons by region not feasible.",
     "declared": false, "resolution": "report as limitation; drop region subgroup; flag in manuscript"}
  ]
}
```
Each deviation carries `id`, `dimension`, `severity`, `finding`, `sap_impact`, `declared`, `resolution`.

## Eligibility filtering (per locked criteria)
- Keep rows with `consent = oui` and `eligible = oui`.
- Apply locked inclusion (diplomes currently practising in Morocco) and exclusion (non-diplomes; not currently
  practising; records missing data needed for the primary score).
- Record counts at each step for the STROBE participant-flow diagram (retrieved -> consented -> eligible ->
  analysed), so emp-05/emp-07 can report it.

## Missing data
Apply the **locked** rule only. Common locked patterns: item-level rule for MSQ subscale computability (e.g.
score a subscale only if >= X of its items are present); listwise for the primary association model. Do not
introduce imputation unless the lock specifies it. Record the rule applied and the resulting Ns.

## Anonymisation verification
- No names, no national IDs, no free-text that identifies a person.
- No identification of a specific establishment, service, or supervisor in any retained field.
- Apply the re-identification guard from the protocol: plan to suppress or aggregate any reported cell below a
  small-count threshold (this is enforced at reporting in emp-05/emp-07, recorded here).

## Cleaning log
Record every transformation in order: source rows, rows removed by each filter (with reason), recodes,
duplicate resolutions, and the final analytic N. The log must let a third party reproduce the cleaned dataset
from the raw workbook.

## Outputs
- `deviati