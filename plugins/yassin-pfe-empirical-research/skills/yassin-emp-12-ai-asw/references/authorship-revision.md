# Authorship Revision  -  Reference

## Editable scope (content lock)
Editable: wording, sentence and paragraph structure, voice, signposting, clarity, and evidence traceability.
**Frozen:** every result, number, table value, statistic, CI, citation, and methodological claim. Never move a
frozen value; never edit to defeat a detector.

## Coaching method (not ghost-writing)
For each finding in the `AI_ARA_register.json`:
1. show the weak passage and name the AI-likeness signal (generic register, hedging chain, templatey rhythm);
2. model **one** revision in the student's own register;
3. have the student rewrite the remaining passages themselves;
4. give specific feedback until the passage carries a genuine authorial stance.

Strengthen: precision (replace vague claims with specific, data-tied statements), traceability (tie each claim
to a result or a cited comparator), and voice (the student's own framing of why findings matter for Moroccan
nursing).

## Lock-compliance diff (before emitting)
Compare every number and citation in the new version against `results_lock.json` and `protocol_lock.json`. Any
difference without a logged amendment is a violation  -  revert it.

## ASW_attestation.json
```json
{
  "project_id": "D03-P01",
  "pass": "ASW-1",
  "output_version": "V3",
  "frozen_values_unchanged": true,
  "diff_summary": "0 numbers changed; 0 citations changed; prose only",
  "revision_log_ref": "ASW_1_revision_log.docx"
}
```
`frozen_values_unchanged` must be `true` to hand off; if it cannot be, fix the violation first.
