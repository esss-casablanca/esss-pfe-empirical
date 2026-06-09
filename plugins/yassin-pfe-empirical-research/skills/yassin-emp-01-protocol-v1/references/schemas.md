# Machine-Readable Schemas  -  Pipeline 1

Indicative shapes. Field names may be finalised in implementation but must stay stable across emp-01/02/03.

## student_project_profile.json
```json
{
  "first_name": "", "family_name": "", "filiere": "", "promotion": "",
  "project_code": "D03-P01", "project_title": "",
  "academic_supervisor": "", "field_supervisor": "", "email": null,
  "interaction_language": "fr|en|ar",
  "questionnaire_field_language": "fr|ar",
  "design": "cross-sectional analytic",
  "reporting_standard": "STROBE",
  "review_article_ref": "<locked review doc id>",
  "socle_commun_conformant": false,
  "created_at_step": "Yassin_EMP_01_Protocol_V1",
  "pipeline_progress": ["Yassin_EMP_01_Protocol_V1"]
}
```

## protocol_lock.json (produced by emp-03, scaffolded conceptually here)
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
  "_roles_note": "For the primary association, job satisfaction (MSQ scores) is the EXPOSURE and intention-to-stay is the OUTCOME. Reporting the satisfaction levels themselves is a descriptive secondary objective. Tag each codebook variable accordingly.",
  "population": {"include": [], "exclude": []},
  "sample_size": {"target_min": 150, "target_max": 250, "hard_min": 100,
                  "power_basis": "<effect size + Consensus source>"},
  "socle_commun": {"conformant": true, "variables": []},
  "instrument": {"name": "MSQ-SF", "version": "", "language": "fr",
                 "translation_status": "authorized|adapted", "cronbach_planned": true},
  "codebook": [
    {"var": "secteur", "label": "Secteur", "type": "categorical",
     "codes": ["public"