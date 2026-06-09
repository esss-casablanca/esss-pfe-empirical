# Protocol Lock  -  Procedure and Schema

## Frozen vs editable
**Frozen (the auditable contract for Pipeline 2):**
- study design and bound reporting standard
- primary and secondary outcomes and hypotheses
- population and eligibility criteria
- the instrument and its exact item wording
- the codebook (variables, codes, roles, scoring)
- the statistical analysis plan (SAP)
- the sample-size plan
- the ethics protocol and consent text

**Editable afterward (no amendment needed):**
- recruitment logistics
- timeline
- background prose

**Any change to a frozen element after the lock** is a dated, justified **amendment** appended to
`protocol_lock.json.lock.amendments`. Pipeline 2 surfaces every amendment as a deviation to evaluate.

## Preconditions (all must hold)
1. No Critical or Major issue open in `CA_protocol_register.json`.
2. Socle-commun conformance confirmed.
3. Consistency invariant holds (questionnaire <-> workbook <-> codebook).
4. The student has given explicit sign-off (Interaction Contract A.6).

## protocol_lock.json
```json
{
  "project_id": "D03-P01",
  "design": "cross-sectional analytic",
  "reporting_standard": "STROBE",
  "review_article_ref": "<locked review doc id>",
  "objectives": {
    "primary": "association between job satisfaction and intention to stay",
    "secondary": ["subgroup differences", "retention levers ranking"]
  },
  "outcomes": {
    "primary": "intention_to_stay_profession",
    "secondary": ["subgroup_differences", "levers_ranking"]
  },
  "exposures": {
    "primary": "msq_general",
    "components": ["msq_intrinsic", "msq_extrinsic"]
  },
  "_roles_note": "Primary association: satisfaction (MSQ) is the EXPOSURE, intention-to-stay the OUTCOME. Satisfaction levels are a descriptive secondary objective.",
  "population": {"include": [], "exclude": []},
  "sample_size": {"target_min": 150, "target_max": 250, "hard_min": 100,
                  "power_basis": "<effect size + Consensus source>"},
  "socle_commun": {"conformant": true, "variables": []},
  "instrument": {"name": "MSQ-SF", "version": "", "language": "fr",
                 "translation_status": "authorized|adapted", "cronbach_planned": true},
  "codebook": [{"var": "secteur", "type": "categorical",
                "codes": ["public", "prive", "associatif"], "role": "confounder"}],
  "sap": {"descriptives": [], "primary_test": "", "subgroup_tests": [],
          "missing_rule": "", "multiplicity": ""},
  "ethics": {"consent_text_ref": "", "risk": "low"},
  "lock": {"locked": true, "date": "",