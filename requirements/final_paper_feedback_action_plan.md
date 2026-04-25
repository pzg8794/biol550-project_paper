# BIOL550 final paper feedback action plan

This file consolidates the actionable feedback currently available from the course requirements, the paper draft comments, the requirements notes, and the meeting transcript. The repository is public, so private email content is not copied here. Add any email-only notes manually if they are safe to store in the repo.

## Sources checked

- Current Google Doc draft: `HTSA_Paper`
- `requirements/BIOL550_Piter_04-09_to_04-16_Additions_Draft.md`
- `biol550/transcripts/2006-03-16 Weekly Meeting_ Data Quality, Reference Genome, and Workflow-transcript.txt`
- `biol550/planning/BIOL550-Final-Project-Plan-CORRECTED.md`

---

# 1. Dr. Osier / course-level feedback and requirements

## 1.1 Meet final paper formatting and content requirements
**Priority:** High

### Action
Before final submission, verify:

- 30-50 pages
- minimum 15 primary sources
- no more than half the paper as figures/tables
- 8.5 x 11 inch page size
- double-spaced
- MS Word, LibreOffice, or OpenOffice final file, not Google Docs
- 10 or 12 point Calibri or Times New Roman
- exactly 1 inch margins
- no more than one page of direct quotes total
- standard sections: Introduction, Materials and Methods, Results, Discussion, References
- proper spelling, grammar, and scientific style
- individual contribution colors and opening comment identifying each author color

### Why it matters
These are grading requirements. The paper can lose points even if the science is strong if these are missed.

---

## 1.2 Include software versions and reproducible methods
**Priority:** High

### Action
Keep software versioning in the paper. Use versions at first mention in Methods and keep the compact version table only if it does not crowd out prose.

### Suggested Methods wording
- `FastQC v0.12.1 was used to evaluate raw and trimmed read quality.`
- `MultiQC v1.33 was used to summarize cohort-level QC reports.`
- `fastp v0.23.2 was used for paired-end trimming.`
- `STAR v2.7.11b was used for genome indexing, alignment, and GeneCounts output.`
- `DESeq2 v1.38.3 was used for count-based differential-expression analysis.`
- `g:Profiler API e109_eg56_p17_7d9b9 was queried on 2026-04-16.`

### Why it matters
The project is computational. Reproducibility depends on software names, versions, parameters, reference releases, and query dates.

---

## 1.3 QC/adapters must justify moving to alignment
**Priority:** High

### Feedback captured
In the meeting transcript, Dr. Osier indicated that if adapter removal resolved the QC issue and MultiQC no longer showed the large gap after trimming, the group could proceed to alignment.

### Action
The Results and Methods should show a clear before/after QC handoff:

- raw adapter-content issue
- trimming with fastp
- post-trim FastQC/MultiQC improvement
- justification for using cleaned reads for alignment

### Suggested wording
`The pre-trim QC review identified adapter-related signal in the raw reads. After fastp trimming, the adapter signal was reduced substantially in the post-trim FastQC/MultiQC summaries, supporting the decision to use the cleaned reads for alignment.`

---

## 1.4 Reference genome choice must be justified
**Priority:** High

### Feedback captured
Dr. Osier warned not to blindly assume the source paper's reference choice was correct. The group needed to think through the reference choice and avoid inappropriate mouse references such as strain-specific references that do not match the dataset.

### Action
In Data Preparation, explain why the GRCm39 primary assembly and Ensembl release 115 annotation were appropriate.

### Suggested sentence
`The GRCm39 primary assembly and matching Ensembl release 115 annotation were selected to keep the genome FASTA and gene model coordinate system consistent while avoiding strain-specific references that were not appropriate for the retained mouse DRG subset.`

---

## 1.5 Use one official workflow path for final claims
**Priority:** High

### Feedback captured
The transcript discussion clarified that final paper claims should come from the shared retained outputs, not from separate exploratory local runs.

### Action
Make sure the paper reports one retained 20-sample workflow path.

### Suggested sentence
`All reported QC, alignment, differential-expression, and enrichment results refer to the retained 20-sample family_drg_novaseqx workflow outputs rather than exploratory local test runs.`

---

# 2. Faculty comments currently in the Google Doc

## 2.1 Tighten the Introduction transition
**Priority:** High

### Feedback captured
The paper starts broadly with neurological injury and shifts abruptly into the Ahr mouse DRG study.

### Action
Add a bridge from neurological injury to the specific dataset.

### Suggested replacement bridge
`To study this question in a defined injury model, this project reanalyzed a published mouse dorsal root ganglion RNA-seq dataset collected one day after sciatic nerve injury, with particular focus on how AhR loss changes the balance between stress-response and regeneration-associated transcriptional programs.`

---

## 2.2 Reduce repeated side-specific / WT-clearest claims
**Priority:** High

### Feedback captured
The draft repeats that side-specific injury contrasts carried the strongest signal and that the WT branch was the clearest pathway-level result.

### Action
Keep this interpretation once in Discussion. In Results, use technical language and avoid repeating the same claim.

### Suggested Results wording
`Bend-point narrowing was applied to the two side-specific branches to convert large differential-expression outputs into smaller follow-up sets suitable for pathway-level interpretation.`

### Suggested Discussion wording
`The PCA and sample-distance structure supported prioritizing side-specific contrasts, while genotype remained a secondary but biologically relevant layer.`

---

## 2.3 Keep Methods descriptive, not interpretive
**Priority:** High

### Feedback captured
The phrase `which remained the clearest pathway-level follow-up` should not be in Methods.

### Action
Use neutral Methods wording.

### Preferred sentence
`For the side-specific follow-up, retained GO outputs were re-analyzed with term-gene membership preserved and summarized using ranked-chart, clustering-tree, and shared-gene network views to reduce redundancy among overlapping GO labels.`

---

# 3. Team feedback and cleanup items

## 3.1 Software version table vs versions at first mention
**Priority:** Medium

### Team concern
Software versions are often given at first mention in Methods rather than as a standalone table.

### Resolution
Use versions at first mention and keep the table only if it stays compact. If space or figure/table ratio becomes an issue, move the full table to supporting material.

---

## 3.2 Use WT in prose instead of FF
**Priority:** Medium

### Action
Use `WT` in narrative prose and captions. Keep `ff` only in code labels and saved contrast names.

### Replace in prose
- `FF branch` -> `WT branch`
- `FF-only genes` -> `WT-only genes`
- `FF GO follow-up` -> `WT GO follow-up`
- `seen in FF` -> `seen in WT`

### Do not replace
- `ipsi_vs_contra_in_ff`
- file names
- saved contrast labels
- genotype-code definitions

---

## 3.3 Clarify vague `main` wording
**Priority:** Medium

### Action
Replace vague phrases such as `main side-specific branches`.

### Suggested replacement
`the two side-specific branches carried forward for GO follow-up`

---

## 3.4 Make Figure 14 clearly WT-only
**Priority:** Medium

### Action
Revise the caption so it does not imply the figure covers both WT and cKO.

### Suggested caption
`Figure 14. WT upregulated GO Biological Process follow-up for the ipsilateral-versus-contralateral branch. The ranked chart and shared-gene network summarize enriched GO Biological Process terms supported by the 709-gene WT bend-point follow-up set.`

---

## 3.5 Define the shared injury-response backbone
**Priority:** Medium

### Action
Replace vague `core injury-response program` wording with counts.

### Suggested replacement
`The two narrowed side-specific branches shared 620 genes, meaning that most of the WT follow-up set also appeared in the cKO follow-up set. This shared gene set was treated as the common injury-response backbone, while the WT-only and cKO-only genes were used to evaluate branch-specific differences.`

---

## 3.6 Use Venn diagrams without duplicating tables
**Priority:** Medium

### Action
Use the Venn diagram in the source-dataset validation or published-analysis comparison section, not immediately beside a table that already gives the same counts.

---

## 3.7 Delete or explain the `Main cKO-specific divergence` table row
**Priority:** Medium

### Action
Delete the row unless a paragraph explains exactly how the phosphorylation/phosphate metabolism divergence was derived.

---

## 3.8 Move anchor-gene interpretation into Discussion
**Priority:** Medium

### Action
Keep only a short Results statement and move interpretation to Discussion.

### Results version
`Recurring anchor genes in the WT GO follow-up included Atf3, Gadd45a, Jun, Sox11, and Flrt3.`

### Discussion version
`These recurring genes provide a bridge between the broad GO labels and biologically recognizable injury-response and remodeling markers, helping connect the global reanalysis back to the original paper's candidate-gene logic.`

---

## 3.9 Fix missing citations
**Priority:** High

### Required citation fixes
- DRG motor-response sentence should cite Link et al. (2023).
- `Zuo et al.` should be corrected to `Zou et al. (2009)` if the reference list uses Zou et al.
- Demyelinating pathology / neuron-intrinsic interpretation should cite Halawani et al. (2023).
- Original-paper claims about stress response and axon regeneration should cite Halawani et al. (2023).

---

## 3.10 Remove unfinished placeholders
**Priority:** High

### Search for and resolve
- `LINK`
- `[Future Directions]`
- `[Limitations]`
- `Figure X`
- `Table X`
- empty bracket placeholders
- unfinished headings such as `Alternative Splicing Analysis` if no content is added

---

# 4. Recommended final revision order

1. Add any safe-to-share email-only feedback from Dr. Osier.
2. Verify formatting and final `.docx` requirements.
3. Fix Introduction transition and citations.
4. Remove repeated side-specific / WT-clearest claims.
5. Finalize Methods reproducibility and software versions.
6. Justify GRCm39 / Ensembl release 115 reference choice.
7. Resolve figure and table numbering.
8. Decide where the Venn diagram belongs.
9. Move anchor-gene interpretation into Discussion or shorten it in Results.
10. Finish Future Directions and Limitations.
11. Do a final citation-reference cross-check.
12. Export from Word/LibreOffice/OpenOffice for submission.
