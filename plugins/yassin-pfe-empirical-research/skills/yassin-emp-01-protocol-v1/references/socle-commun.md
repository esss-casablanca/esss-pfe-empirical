# Socle Commun  -  Domaine 3 Shared Variable Core

All seven Domaine-3 projects must collect this shared background block, coded identically, so the datasets
can be pooled across the nursing workforce. The protocol is **not** free to rename or re-bucket these.
Every variable below must appear in the instrument and the workbook, coded as specified.

| Variable (var) | Label (FR) | Type | Allowed codes / format |
|----------------|------------|------|------------------------|
| `age` | Age | numeric | years (integer) |
| `sexe` | Sexe | categorical | homme / femme |
| `region` | Region | categorical | the 12 Moroccan regions (controlled list) |
| `secteur` | Secteur | categorical | public / prive / associatif |
| `type_etablissement` | Type d'etablissement | categorical | CHU / hopital regional ou provincial / clinique privee / centre de sante / autre |
| `service` | Service d'exercice | categorical | urgences / medico-chirurgical / reanimation-soins critiques / maternite / pediatrie / soins primaires / autre |
| `anciennete_prof` | Anciennete professionnelle | numeric | years |
| `anciennete_poste` | Anciennete dans le poste actuel | numeric | years |
| `niveau_formation` | Niveau de formation | categorical | diplome d'Etat / licence / master / autre |
| `statut_prof` | Statut professionnel | categorical | titulaire / contractuel / vacataire / autre |
| `gardes_nuits` | Nombre moyen de gardes ou nuits / mois | numeric | count |
| `charge_horaire` | Charge horaire hebdomadaire approximative | numeric | hours/week |
| `formation_continue` | Participation recente a une formation continue | categorical | oui / non |

## Enforcement
- A missing variable, a renamed `var`, or an altered code list is a **hard failure** at STEP 6: report it to
  the student and fix it before proceeding.
- The project-specific instruments (MSQ-SF, the intention block, the levers MCQ) are **added to** this core,
  never **instead of** it.
- If the note de cadrage's controlled lists differ from this table, surface the discrepancy to the student
  and align to the programme-level core unless the student's supervisor has formally revised it.

> Note: the controlled lists above reflect the D03 programme as described in the note de cadrage. If the
> programme office issues an updated socle commun, replace this table and re-run the conformance check.
