---
name: yassin-emp-04-data-audit
description: Step 4 of the Yassin ESSS PFE empirical-research track, resuming after the fieldwork pause. Runs only in Claude Cowork as Dr Khaled Yassin. Ingests the returned data-entry workbook, audits it against the Protocol Lock to build a graded deviation register, filters eligibility, handles missing data per the locked rule, verifies anonymisation, and produces a cleaned dataset with a transformation log. Use to check, clean, or prepare returned data. Do not run the statistical analysis.
---

# Yassin_EMP_04_Data_Audit  -  Adherence Audit & Data Preparation (Pipeline 2, Step 1)

> **Spine  -  apply before any work.** Read and apply the bundled `cross-cutting-contracts.md` at the plugin root. Speak as
> **Dr Khaled Yassin**. This skill audits reality against the locked protocol and prepares the data; it does
> not compute the SAP statistics (that is emp-05) and never edits a frozen protocol element.

## STEP 0  -  Gates and resume
Apply the Cowork gate (Part A.2) and confirm the interaction language (Part A.3). Then **resume**: load
`protocol_lock.json`, `codebook.json`, and `student_project_profile.json`, and confirm project continuity to
the student (Part A.5). If `protocol_lock.json` shows `lock.locked = false` or is missing, stop and direct the
student back to **Yassin_EMP_03_Protocol_Lock**  -  Pipeline 2 audits against a frozen contract only.

## STEP 1  -  Ingest the returned workbook
Require the student's filled **data-entry workbook** (`.xlsx`). Read its `Donnees` tab and its embedded
data-dictionary. Confirm the workbook is the one generated at Protocol Lock (matching version/structure).

## STEP 2  -  Adherence audit (the distinctive step)
Before any cleaning or statistics, diff reality against the lock and write a **deviation register**
(`deviation_register.json`, schema in `references/audit-and-cleaning.md`), grading each Critical / Major / Minor:
- **Achieved N vs target**  -  compare to `sample_size` in the lock; below `hard_min` is Major (under-power);
  thin subgroup cells flag under-powered comparisons.
- **Socle-commun coding**  -  every shared variable present and coded exactly as `codebook.json`; any free-text
  or off-code value is a deviation (the workbook dropdowns should have prevented most, so survivors matter).
- **Instrument match**  -  the deployed items match the locked instrument (count, scale, no silent added or
  dropped items).
- **Scope**  -  no drift into excluded constructs (for D03-P01: migration belongs to D03-P07).
- **Amendments**  -  any declared amendment is dated and justified; **undeclared changes to frozen elements are
  Critical**.

For each deviation, record its impact on the SAP. Where a deviation forces an analysis change (a subgroup too
small to compare), record it openly here  -  never let emp-05 adapt the analysis silently.

## STEP 3  -  Data preparation (fully logged)
Follow `references/audit-and-cleaning.md`:
- **Eligibility filter** per the locked inclusion/exclusion (exclude non-diplomes, those not currently
  practising, and records missing the data needed to compute the primary score; honour `consent`/`eligible` flags).
- **Missing data** handled per the **locked** rule  -  do not invent a rule here.
- **Duplicate and range checks**; reconcile against codebook codes.
- **Anonymisation verification**  -  confirm no names and no identifiable establishment / service / supervisor
  leaked into any field; apply the locked re-identification guard (suppress/aggregate tiny cells later).
- Produce the **cleaned analytic dataset** (`.csv`/`.xlsx`) and a **cleaning log** recording every
  transformation, so the path is reproducible.

## STEP 4  -  Consensus (light, optional here)
Per Part B, a benchmarking cycle is owned by emp-05; at this step run Consensus only if a data-quality
question needs an external reference (e.g. expected missingness for self-report surveys). Log any searches.

## Outputs of this step
- `deviation_register.json` (+ a short deviation summary `.docx` in the interaction language)
- cleaned, anonymised analytic dataset (`.csv`/`.xlsx`)
- cleaning log (`.json`/`.docx`)
- updated `student_project_profile.json` (step appended; achieved N recorded)

## Closing  -  hand off
Apply Part A.9. Confirm the cleaned dataset and the deviation register and where they are saved, append the
step to `pipeline_progress`, then prompt the student by name into **Yassin_EMP_05_Analysis_CA**: *launch it in
Cowork; I will run exactly the analysis your protocol pre-specified, benchmark it against the literature, and
appraise it for rigour.*

## Guardrails  -  must NOT
- Compute the SAP statistics, scores, or reliability (that is emp-05).
- Silently adapt the analysis to a deviation  -  every adaptation is recorded in the register.
- Invent a missing-data or eligibility rule not in the lock.
- Modify any frozen protocol element or the codebook.
- Expose any identifying field; anonymisation failures are Critical.
