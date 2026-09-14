# AI-Supported Software Refactoring

This repository contains the data-extraction artifacts for **AI-Supported Software Refactoring: A Tertiary Systematic Mapping Study**. The study synthesizes evidence from **25 secondary studies (P1–P25)** on how artificial intelligence has been used to support software refactoring.

The repository currently provides the frozen or cross-checked datasets used to answer RQ1–RQ4. Each workbook retains study identifiers and evidence text so that the coding decisions can be traced back to the included secondary studies.

## Research questions

- **RQ1. Which software refactoring activities have been supported by AI techniques?**
- **RQ2. Which AI techniques have been used to support software refactoring?**
- **RQ3. How have different AI techniques been applied across software refactoring activities?**
- **RQ4. Which areas of the refactoring process remain insufficiently supported by AI, and what challenges and future research opportunities have been identified?**

## Analytical framework

RQ1 uses the six refactoring activities described by Mens and Tourwé as its fixed high-level framework:

| ID | Refactoring activity |
| --- | --- |
| A1 | Opportunity Identification |
| A2 | Refactoring Selection |
| A3 | Behavior Preservation |
| A4 | Refactoring Application |
| A5 | Quality Impact Assessment |
| A6 | Artifact Consistency Maintenance |

The fine-grained tasks are evidence-derived categories obtained from the 25 included secondary studies. The frozen RQ1 taxonomy contains **16 fine-grained tasks**. A study may support more than one activity or task; all counts therefore use distinct Study IDs rather than the number of evidence rows.

Code-smell and code-clone studies are included under Opportunity Identification only when the secondary study explicitly connects detection to refactoring candidates, opportunities, or subsequent refactoring decisions. Detection-only evidence without this linkage is not treated as AI-supported refactoring evidence.

## Data files

All released workbooks are stored in [`data-extraction/`](data-extraction/).

### RQ1_Subtask_Dictionary_FROZEN_v2.xlsx

Frozen activity and subtask coding for RQ1.

- `Final_Subtask_Taxonomy`: the six high-level activities, 16 canonical subtasks, operational definitions, boundaries, supporting studies, and distinct-study counts.
- `Terminology_Decisions`: the audit trail for retaining, excluding, or normalizing earlier task labels.
- `RQ1_Frozen_Mapping`: the finalized Study × Activity × Subtask mapping.
- `Manual_Review`: records requiring or documenting manual adjudication.

### RQ2_AI_Techniques_RQ3_Aligned.xlsx

Evidence-level extraction and normalization of the AI techniques reported by the included studies.

- `RQ2_Techniques`: normalized technique, original terminology, technique family, evidence sentence, evidence location, and source-row provenance.
- `Broad_and_Auxiliary`: broad, underspecified, or supporting technique descriptions retained separately from the principal normalized entries.

Technique names are kept at the most specific level supported by the secondary-study evidence. Broad labels such as machine learning are retained only when the source does not report a more specific algorithm or model.

### RQ3_Technique_Relations_FROZEN.xlsx

Evidence-level links between AI techniques and refactoring activities or subtasks.

- `RQ3_Relations_Final`: the auditable relation table linking Study ID, activity, subtask, AI family, technique, reported terminology, and supporting evidence.
- `AI_Family_Activity`: distinct-study summary of AI-family × refactoring-activity relations.
- `AI_Technique_Subtask`: distinct-study summary of AI-technique × fine-grained-task relations.

The workbook answers how a reported technique is applied to a refactoring task. It does not infer technique–task relations that are absent from the secondary-study evidence.

### RQ4_Future_Directions.xlsx

Evidence-level extraction of future research directions reported in the Discussion, Future Work, or Conclusion sections of the included studies.

- `RQ4_Future_Directions`: Study ID, the original future-direction statement, its evidence-derived category, and the supporting evidence sentence.

Categories were derived by grouping semantically similar recommendations after extraction; they were not imposed in advance.

## Coding and counting rules

- The unit of synthesis is the **secondary study**, identified as P1–P25.
- A study can generate multiple evidence records and receive multiple activity, task, or technique labels.
- Summary counts use **distinct Study IDs**. Evidence-row counts must not be interpreted as study counts.
- High-level activity counts are calculated from the union of the Study IDs assigned to their fine-grained tasks.
- Classifications distinguish the wording explicitly reported by a secondary study from the normalized terms and mappings introduced by this tertiary study.
- Evidence that cannot be classified without inference is retained as broad, unresolved, or subject to manual review rather than being assigned from domain knowledge alone.

## Traceability

The workbooks preserve the following audit chain where applicable:

```text
Study ID
  → evidence sentence and source location
  → reported term
  → normalized AI technique or refactoring task
  → high-level activity or technique family
  → distinct-study summary
```

This structure allows the task taxonomy, technique inventory, cross-mapping, and future-direction synthesis to be checked against the underlying secondary-study evidence.

## Reference framework

Mens, T.; Tourwé, T. A Survey of Software Refactoring. *IEEE Transactions on Software Engineering* **2004**, *30*, 126–139. https://doi.org/10.1109/TSE.2004.1265817

## Citation

If you use these data, please cite the associated paper and this repository. Full bibliographic information for the tertiary study will be added after publication.
