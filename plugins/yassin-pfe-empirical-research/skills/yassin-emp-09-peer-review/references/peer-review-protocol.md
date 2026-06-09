# Mock Peer Review  -  Protocol and Schema

## Reviewer personas (pick 2-3)
- **R1  -  Methodologist / biostatistician:** design appropriateness, sampling and power, statistical choices,
  assumption checks, multiplicity, missing-data handling, fidelity to the pre-specified plan.
- **R2  -  Nursing-workforce subject expert:** framing, instrument choice (MSQ-SF), comparability with the
  literature, plausibility of findings, policy relevance and overreach.
- **R3  -  Reporting/clarity reviewer:** STROBE completeness, table/figure quality, structure, clarity,
  consistency of numbers across the text.

Each persona is independent, professional, and specific. Comments cite the manuscript location they refer to.

## Each review contains
1. one-paragraph summary of the study;
2. novelty & contribution (is the Moroccan evidence a real addition?);
3. major comments (substantive);
4. minor comments (reporting/clarity);
5. recommendation: accept / minor revision / major revision / reject.

## Editor decision letter
- overall decision (usually "major revision" for a first mock round);
- a consolidated, **numbered** list of points the author must address, merging overlapping reviewer comments;
- explicit note of any point flagged as a Pipeline-2 back-route.

## Consensus discipline
Any factual claim a reviewer makes (e.g. "published MSQ-SF alphas are typically > 0.85", "comparable studies
report r around 0.3") must be checked against Consensus and cited; reviewers never invent evidence.

## Back-route rule
If addressing a point requires **new analysis** (sensitivity analysis, added confounder, re-specified model),
mark it `back_route: true`. It cannot be answered by editing prose; emp-10 opens a dated amendment that
re-enters Pipeline 2 and re-issues the Results Lock.

## peer_review_register.json
```json
{
  "project_id": "D03-P01",
  "reviewers": ["methodologist", "subject_expert", "reporting"],
  "editor_decision": "major revision",
  "points": [
    {"id": 1, "source": "R1", "type": "major", "back_route": true,
     "comment": "Add a sensitivity analysis excluding the imputed cases.",
     "author_action_required": "re-run via Pipeline 2 amendment"},
    {"id": 2, "source": "R3", "type": "minor", "back_route": false,
     "comment": "Table 2 column totals do not match the text N.",
     "author_action_required": "reconcile reporting (no number change)"}
  ]
}
```
