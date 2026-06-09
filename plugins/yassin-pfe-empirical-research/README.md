# ESSS PFE  -  Empirical Research Pipeline

The empirical-research track (Component 2) of the ESSS Projet de Fin d'Etudes, and the counterpart
to the `yassin-pfe-review-pipeline`. It carries a student from a **locked Component-1 review article**
and the **note de cadrage** through a pre-registered protocol, a protocol-faithful analysis, and a
peer-review-ready empirical manuscript with submission support.

The full track is thirteen skills across three chained pipelines, with a deliberate real-world
fieldwork pause after the protocol is locked:

```
LOCKED REVIEW ARTICLE
   
Pipeline 1  -  Protocol      -> protocole court (FR) + questionnaire + data-entry workbook -> PROTOCOL LOCK
      [ fieldwork pause: recruitment + data collection ]
Pipeline 2  -  Data & Analysis -> adherence audit + pre-specified analysis -> RESULTS LOCK
   
Pipeline 3  -  Manuscript    -> critical appraisal + simulated peer review + authorship loop -> submission packs
```

## This release  -  Pipelines 1, 2 & 3 (complete track)

### Pipeline 1  -  Protocol
| Skill | Role |
|-------|------|
| `yassin-emp-01-protocol-v1` | Onboard, ingest the locked review + note de cadrage, detect the design, build the draft protocol, questionnaire, and validated data-entry workbook from one shared codebook; enforce the socle commun. |
| `yassin-emp-02-protocol-ca` | Critically appraise the draft protocol for scientific rigour; emit a graded issue register. |
| `yassin-emp-03-protocol-lock` | Close every issue, regenerate the questionnaire/workbook from the corrected codebook, and issue the **Protocol Lock**. |

### Pipeline 2  -  Data & Analysis (resumes after the fieldwork pause)
| Skill | Role |
|-------|------|
| `yassin-emp-04-data-audit` | Ingest the returned workbook, audit it against the Protocol Lock (deviation register), clean and anonymise, and produce the cleaned analytic dataset. |
| `yassin-emp-05-analysis-ca` | Run only the pre-specified analysis (the pipeline computes it), benchmark against the literature, and critically appraise it. |
| `yassin-emp-06-results-lock` | Close every issue, finalise tables/figures, take the student's sign-off, and issue the **Results Lock**. |

### Pipeline 3  -  Manuscript & Publishing
| Skill | Role |
|-------|------|
| `yassin-emp-07-manuscript-v1` | Draft the IMRaD/STROBE article from the locks (+ rapport final + slides); reconcile the title to the achieved sample. |
| `yassin-emp-08-manuscript-ca` | Critically appraise the manuscript's reporting rigour and fidelity to the locks. |
| `yassin-emp-09-peer-review` | Convene a mock peer review (2-3 reviewers + editor) with a decision letter and back-route flags. |
| `yassin-emp-10-manuscript-v2` | Coach a point-by-point response and produce V2; route true analytic gaps back to Pipeline 2. |
| `yassin-emp-11-ai-ara` | Audit AI-likeness / weak authorship (ARA-1, 