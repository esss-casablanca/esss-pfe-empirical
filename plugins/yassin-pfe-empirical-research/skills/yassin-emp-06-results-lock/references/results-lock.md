# Results Lock  -  Procedure and Schema

## Frozen vs editable
**Frozen (the content lock for Pipeline 3):**
- the cleaned analytic dataset and final N
- every results table and figure
- every reported statistic, the primary estimate and 95% CI, p-values
- the named subgroup results and the levers ranking
- the reliability results (alpha/omega)
- the deviation register and the exploratory/confirmatory labelling
- every citation used to support a reported number

**Editable afterward (manuscript phase only):**
- interpretation, discussion framing, prose, and structure  -  never a frozen value

The **only** way to change a frozen number after the lock is a dated amendment that re-enters Pipeline 2
(re-run from the analysis script) and re-issues the Results Lock. The manuscript phase can never edit a value.

## Preconditions (all must hold)
1. No Critical or Major issue open in `CA_analysis_register.json`.
2. Tables/figures regenerated from the corrected script and matching it exactly.
3. Small-cell suppression / re-identification guard applied to every reported table.
4. The student has given explicit sign-off (Interaction Contract A.6).

## results_lock.json
```json
{
  "project_id": "D03-P01",
  "protocol_lock_ref": "<protocol_lock id>",
  "final_n": 0,
  "participant_flow": {"retrieved": 0, "consented": 0, "eligible": 0, "analysed": 0},
  "deviation_register_ref": "<id>",
  "reliability": {"msq_intrinsic_alpha": 0.0, "msq_extrinsic_alpha": 0.0, "intention_alpha": 0.0},
  "primary_result": {"test": "", "estimate": 0.0, "ci": [0.0, 0.0], "p": 0.0, "adjusted": true},
  "subgroup_results": [],
  "levers_ranking": [],
  "tables": ["<table ids>"],
  "figures": ["<figure ids>"],
  "exploratory": [{"label": "", "not_prespecified": true}],
  "lock": {"locked": true, "version": 1, "date": "", "signed_off_by_student": true,
           "frozen_scope": ["numbers", "tables", "figures", "citations"],
           "amendments": []}
}
```

## Re-issuing the lock (back-route from Pipeline 3)
If a peer-review or appraisal point in Pipeline 3 forces new analysis (a back-rou