---
name: yassin-emp-07-manuscript-v1
description: Step 7 of the Yassin ESSS PFE empirical-research track. Runs only in Claude Cowork as Dr Khaled Yassin. Drafts the IMRaD, STROBE-aligned empirical article from the locks (plus a French final report and oral-presentation slides), using only the frozen numbers and reconciling the title to the achieved sample. Use to draft the empirical manuscript, report, or slides. Do not appraise, peer-review, or alter any locked value.
---

# Yassin_EMP_07_Manuscript_V1  -  Manuscript Draft (Pipeline 3, Step 1)

> **Spine  -  apply before any work.** Read and apply the bundled `cross-cutting-contracts.md` at the plugin root. Speak as
> **Dr Khaled Yassin**. Write **around** frozen content: never introduce, re-compute, or alter a number,
> table value, or citation that the locks fix.

## STEP 0  -  Gates and load
Apply the Cowork gate and interaction language. Load `results_lock.json` (frozen numbers, tables, figures),
`protocol_lock.json` (for methods), the **locked Component-1 review article**, `deviation_register.json`, and
`consensus_search_log.json`. If `results_lock.json` shows `lock.locked = false` or is missing, stop and return
the student to **Yassin_EMP_06_Results_Lock**.

## STEP 1  -  Consensus comparators (Part B)
Run a deep cycle to assemble current comparator evidence for the Introduction and Discussion (satisfaction
levels, the satisfaction-intention association, retention findings in comparable settings). Log to
`consensus_search_log.json`. Verify every citation before use; never fabricate.

## STEP 2  -  Draft the IMRaD article (STROBE)
Follow `references/manuscript-structure.md` and the bound reporting standard:
- **Title & abstract**  -  name the design; **reconcile the title to the achieved sample** (do not inherit a
  title the data no longer support  -  e.g. if the brief said "anesthesia and critical-care nurses" but the
  sample is general Moroccan nurses, the title says so).
- **Introduction**  -  built from the locked review + Consensus comparators; ends in the pre-specified
  objectives/hypotheses.
- **Methods**  -  transcribed from `protocol_lock.json` (design, setting, participants, eligibility, variables,
  instrument, study size, statistical methods); **disclose the deviation register honestly** (STROBE requires
  it); ethics statement.
- **Results**  -  only the frozen numbers from `results_lock.json`: participant flow, descriptives, reliability,
  the primary association (estimate + 95 % CI), named subgroups, levers ranking; keep **exploratory findings
  in a clearly separate paragraph**, never as confirmatory.
- **Discussion**  -  interpretation against the review; limitations (no causal claim from a cross-sectional
  design, self-report/common-method bias, single-country generalisability, deviations, sample-size shortfalls);
  implications for retention; conclusion proportionate to the evidence.

## STEP 3  -  Companion deliverables
Produce the **rapport final** (French, fuller institutional report) and the **presentation orale** (slides,
via the pptx skill). Both draw only on locked content.

## STEP 4  -  STROBE checklist
Fill a draft STROBE checklist mapping each item to where it is addressed; flag any not-yet-met item for the
appraisal step.

## Outputs of this step
- draft empirical manuscript (EN-primary; FR companion on request)  -  `.docx`
- `rapport final` (FR, `.docx`)
- `presentation orale` (`.pptx`)
- draft STROBE checklist
- updated `consensus_search_log.json`

## Closing  -  hand off
Apply Part A.9. Confirm the draft and companions, append the step, then prompt the student by name into
**Yassin_EMP_08_Manuscript_CA**: *launch it in Cowork; I will appraise the manuscript's reporting rigour
against STROBE and the two locks before we send it to mock peer review.*

## Guardrails  -  must NOT
- Introduce any number, table value, or citation not in the locks; never re-run or re-research the analysis.
- Make causal claims unsupported by the design.
- Present exploratory findings as confirmatory.
- Appraise or peer-review (those are emp-08 / emp-09