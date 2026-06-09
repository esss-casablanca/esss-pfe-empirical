# ESSS PFE — Empirical Research Pipeline (Claude Cowork plugin)

By **Dr Khaled Yassin (ESSS)**. A guided, thirteen-skill pipeline that takes a student from a locked
Component-1 literature review and a *note de cadrage* through a pre-registered protocol, a protocol-faithful
analysis, and a peer-review-ready, submission-ready empirical manuscript. It speaks as Dr Yassin, uses
Consensus as an enforced deep-research knowledge base, and enforces two hard locks (Protocol Lock, Results
Lock) with a deliberate fieldwork pause.

> Runs only in **Claude Cowork**.

---

## For students — how to install

### Method A — download the plugin file (recommended for Cowork)

1. Open **`yassin-pfe-empirical-research.plugin`** in this repository and click **Download**
   (or download it from the repo's **Releases** page).
2. In **Claude Cowork**, open the downloaded `.plugin` file and click **Save plugin**.
3. The 13 `yassin-emp-*` skills now appear under **Customize → Skills → Personal plugins**.

### Method B — add as a marketplace (Claude Code / marketplace-aware clients)

```
/plugin marketplace add esss-casablanca/esss-pfe-empirical
/plugin install yassin-pfe-empirical-research@yassin-pfe-empirical
```


---

## How to use it

Start a new chat in Cowork and trigger the first skill (e.g. *"build my empirical protocol"* or run
`yassin-emp-01-protocol-v1`). Dr Yassin will greet you, ask your working language, and ask you to upload:

1. your **locked Component-1 review article**, and
2. the **note de cadrage** for your project.

Then move through the steps in order:

- **Pipeline 1 — Protocol:** `emp-01` (build) → `emp-02` (appraise) → `emp-03` (lock).
  Out come a French *protocole court*, a field-language questionnaire, and an Excel data-entry workbook.
- *Collect your data and fill the workbook.*
- **Pipeline 2 — Data & Analysis:** `emp-04` (audit + clean) → `emp-05` (analyse + appraise) → `emp-06` (lock).
- **Pipeline 3 — Manuscript:** `emp-07` (draft) → `emp-08` (appraise) → `emp-09` (mock peer review) →
  `emp-10` (revise) → `emp-11`/`emp-12` (authorship loop, two passes) → `emp-13` (journals + submission packs).

Each skill tells you which skill to launch next.

## Requirements

- **Claude Cowork** (the pipeline stores your profile and every lock across sessions).
- The **Consensus** research connector (evidence knowledge base).
- The bundled **docx** and **xlsx** skills (available in Cowork) for the deliverables.

## Repository layout

```
.claude-plugin/marketplace.json              # marketplace manifest (Method B)
plugins/yassin-pfe-empirical-research/        # the plugin (skills + shared spine)
yassin-pfe-empirical-research.plugin          # downloadable plugin file (Method A)
```

## License

Proprietary. © Dr Khaled Yassin, ESSS.
