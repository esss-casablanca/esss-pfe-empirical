# Authorship Audit  -  Reference

## Principle
The goal is **authentic student authorship**, never a lower detector score by trickery. We never coach
evasion. We diagnose AI-likeness so the student can re-author in their own voice within the editable scope.
The science is locked and untouched.

## Four levels
- **Document:** generic-academic register; an even, voiceless tone; repetitive structural scaffolding; absence
  of a specific authorial stance.
- **Section:** formulaic openings ("In recent years..."), list-like prose, clustered hedging, mechanical
  signposting.
- **Paragraph:** uniform length and rhythm; templatey topic-sentence-then-three-supports patterns; transitions
  that add no content.
- **Sentence:** tell-tale connective phrases, empty intensifiers, over-smooth parallelism, vagueness where a
  specific is expected.

## What is in scope vs out of scope
- **In scope (editable):** wording, sentence structure, paragraph organisation, voice, signposting, clarity.
- **Out of scope (frozen):** every result, number, table value, citation, and methodological claim.

## ARA-2 attestation check
On the second pass, before auditing, open `ASW_attestation.json` and confirm the writing pass changed no
frozen value. If it did, return to emp-12. On a clean attestation, audit V3 and **track progress** against
`AI_ARA_register.json` from ARA-1 (which findings closed, which persist, any new ones).

## AI_ARA_register.json
```json
{
  "project_id": "D03-P01",
  "pass": "ARA-1",
  "detector_report_interpreted": false,
  "summary": {"document": 0, "section": 0, "paragraph": 0, "sentence": 0},
  "findings": [
    {"id": 1, "level": "sentence", "location": "Discussion 2",
     "issue": "Generic hedging chain with no specific claim.",
     "coaching": "Replace with a concrete statement tied to your own data and one comparator."}
  ],
  "progress_vs_prev": null
}
```
