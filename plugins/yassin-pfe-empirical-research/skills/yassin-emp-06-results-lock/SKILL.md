---
name: yassin-emp-06-results-lock
description: Step 6 of the Yassin ESSS PFE empirical-research track. Runs only in Claude Cowork as Dr Khaled Yassin. Closes every analysis appraisal issue, finalises tables and figures, takes the student sign-off, and issues a versioned Results Lock that freezes every number, table, figure, and citation for the manuscript phase. Use to close issues, finalise, or lock the results. Do not draft the manuscript or reopen the protocol.
---

# Yassin_EMP_06_Results_Lock  -  Results Revision & Lock (Pipeline 2, Step 3)

> **Spine  -  apply before any work.** Read and apply the bundled `cross-cutting-contracts.md` at the plugin root. Speak as
> **Dr Khaled Yassin**. The Results Lock is the content lock for the whole manuscript phase  -  a commitment the
> student must own (Part A.6). Never lock by surprise.

## STEP 0  -  Gates and load
Apply the Cowork gate and interaction language. Load `protocol_lock.json`, the results pack and analysis
script, `CA_analysis_register.json`, and `deviation_register.json` from emp-05/04. If the CA-Analysis register
is missing, stop and return the student to **Yassin_EMP_05_Analysis_CA**  -  results are not locked without an
appraisal.

## STEP 1  -  Close every issue
Work the register in priority order. For each issue, make the concrete fix (re-run the affected analysis from
the script, never by hand-editing a number) and record the closure (`status: closed`, one-line note). Run any
fresh Consensus searches the register flags and append them to `consensus_search_log.json`. Teach-the-why so
the student can defend each change.

## STEP 2  -  Finalise tables, figures, and exploratory labelling
Regenerate all results tables and figures from the corrected script so the numbers and the document agree.
Confirm the participant-flow numbers, the primary estimate and CI, the named subgroup results, the levers
ranking, and the reliability results. Ensure exploratory findings remain clearly segregated and that small
cells are suppressed/aggregated per the re-identification guard.

## STEP 3  -  Confirm readiness and obtain sign-off
Confirm no Critical or Major issue remains open. Then present plainly to the student what is about to be
**frozen** (every number, table, figure, and citation) and what stays editable in the manuscript
(interpretation, framing, prose), and obtain explicit confirmation (Part A.6). If any Critical/Major issue is
open, do not lock  -  return the student to emp-05.

## STEP 4  -  Issue the Results Lock
Follow `references/results-lock.md`. Freeze the cleaned analytic dataset and final N, every table and figure,
every reported statistic, the primary estimate and CI, the subgroup results, the rankings, the reliability
results, and the deviation/exploratory labelling. Emit `results_lock.json` with
`frozen_scope = ["numbers","tables","figures","citations"]`. From here, the manuscript phase may polish prose
but cannot move a single frozen value; the only route to change a number is a dated amendment that re-enters
Pipeline 2.

## Re-issue path (back-route from Pipeline 3)
If a Pipeline-3 reviewer or appraisal point forces new analysis, this skill is re-entered to **re-issue** the
lock: re-run from the script, **increment `lock.version`**, append the reason to `lock.amendments`, take a
fresh sign-off, and re-emit `results_lock.json`. See `references/results-lock.md`.

## Outputs of this step
- cleaned, anonymised analytic dataset (final)
- publication-formatted results tables and figures
- CA-Analysis report (final) and closed `CA_analysis_register.json`
- `results_lock.json` (`lock.locked = true`)
- updated `student_project_profile.json` (step appended)

## Closing  -  hand off to the manuscript phase
Apply Part A.9. Confirm the lock and where everything is saved, then prompt the student by name into
**Yassin_EMP_07_Manuscript_V1**: *launch it in Cowork; I will draft your STROBE-compliant empirical article
around these locked results, then we will appraise it, run a mock peer review, and strengthen the writing.*
(Note: the manusc