# BIOL550 Final Paper Feedback Inventory

This file is the source-first feedback inventory for wrapping up the BIOL550 final paper. It separates confirmed Dr. Osier/course-level feedback from non-Osier team and draft feedback so the group can address instructor-facing requirements first.

## Sources checked

### Gmail search status
I searched the connected Gmail account for Dr. Osier / BIOL550 paper feedback using these queries:

- `from:(mvoscl@rit.edu) BIOL550 paper OR draft OR final OR requirements OR feedback after:2026/01/01`
- `from:(mvoscl@rit.edu)`
- `mvoscl`
- `Osier BIOL550`
- `Michael Osier`
- `Osier`
- `BIOL550`
- `BIOL 550`, `High Throughput`, and `final paper`

No relevant Dr. Osier email messages were found in the connected Gmail account. If there are email-only comments in another inbox, they still need to be added manually.

### Repository / document sources checked
- Current Google Doc draft: `HTSA_Paper`
- `requirements/BIOL550_Piter_04-09_to_04-16_Additions_Draft.md`
- `requirements/final_paper_feedback_action_plan.md`
- `biol550/transcripts/2006-03-16 Weekly Meeting_ Data Quality, Reference Genome, and Workflow-transcript.txt`
- `biol550/planning/BIOL550-Final-Project-Plan-CORRECTED.md`

---

# 1. Confirmed Dr. Osier / course-level feedback

## 1.1 Final paper format and submission requirements
**Priority:** High  
**Source:** Paper requirements in Google Doc and BIOL550 project plan.

### Feedback / requirement
The final paper must meet the formal course requirements:

- 30-50 pages
- minimum of 15 primary sources
- no more than half figures/tables; the rest must be prose
- 8.5 x 11 inch paper size
- double-spaced
- citations do not count for or against the page requirement
- final file must be MS Word, LibreOffice, or OpenOffice; do not rely on Google Docs for the final submitted version
- 10 or 12 point Calibri or Times New Roman
- exactly 1 inch margins
- no more than one page of direct quotes total
- proper spelling, grammar, and scientific style
- standard scientific sections: Introduction, Materials and Methods, Results, Discussion, References
- individual text must be color-coded using a unique color for each contributor
- include an opening comment identifying each contributor and their revision color

### Required action
Before submission, export the paper to `.docx` and verify every formatting requirement manually in Word, LibreOffice, or OpenOffice.

### Why this matters
These are grading requirements, not optional preferences. A strong analysis can still lose points if the submitted document fails these formatting rules.

---

## 1.2 Publication-quality scientific paper, not a stitched weekly report
**Priority:** High  
**Source:** BIOL550 project plan.

### Feedback / requirement
The final product should read like a publication-quality research paper, not a sequence of weekly reports.

### Required action
Remove or rewrite:

- placeholders
- informal process language
- unfinished headings
- repeated weekly-report framing
- unsupported treatment claims
- notebook/code discussion that does not belong in main prose

### Why this matters
The final paper is being evaluated as a scientific manuscript with standard sections and polished argument flow.

---

## 1.3 Methods must include software names, versions, parameters, and reproducible analysis details
**Priority:** High  
**Source:** BIOL550 project plan and professor-facing software-version requirement discussed by the group.

### Feedback / requirement
The computational Methods section should include the major software tools, versions, parameters, and reference resources used in the workflow.

### Required action
Keep software versioning in the paper. Best implementation:

1. Add versions at first mention in Methods where practical.
2. Keep a compact version/resource table only if it remains clean and does not crowd out prose.
3. Include reference genome and annotation releases, not just software tools.

### Current version entries to preserve or verify
- SRA Toolkit: 3.3.0
- FastQC: 0.12.1
- MultiQC: 1.33
- fastp: 0.23.2
- STAR: 2.7.11b
- Ensembl mouse reference genome: *Mus musculus* GRCm39 primary assembly
- Ensembl gene annotation: release 115
- R: 4.3.3
- Python: 3.13.5
- DESeq2: 1.38.3
- g:Profiler: API version e109_eg56_p17_7d9b9, queried 2026-04-16

### Suggested Methods wording
Use first-mention wording like:

> Raw and trimmed read quality was evaluated with FastQC v0.12.1 and summarized with MultiQC v1.33. Read trimming used fastp v0.23.2 with paired-end adapter detection, poly-G trimming, a mean-quality cutoff of 20, and a minimum retained length of 30 bases.

> Alignment and count generation were performed with STAR v2.7.11b using the *Mus musculus* GRCm39 primary assembly and Ensembl release 115 annotation.

> Count-based differential expression was performed with DESeq2 v1.38.3 in R v4.3.3, and enrichment analysis used g:Profiler API e109_eg56_p17_7d9b9 queried on 2026-04-16.

### Why this matters
The professor asked for software versions, and reproducibility is central to a computational RNA-seq paper.

---

## 1.4 QC/adapters: show before/after evidence and justify moving to alignment
**Priority:** High  
**Source:** March 16 meeting transcript with Dr. Osier.

### Feedback captured
Dr. Osier asked whether adapter cleanup removed the major QC discrepancy. His guidance was that if MultiQC no longer showed the big gap after adapter removal and GC patterns looked similar enough, the group could stop chasing that issue and proceed to alignment.

### Required action
The paper should clearly show the QC handoff:

- raw adapter-content issue
- trimming/cleanup performed
- post-trim FastQC/MultiQC improvement
- cleaned reads used for alignment

### Suggested Results wording
> The pre-trim QC review identified adapter-related signal in the raw reads. After fastp trimming, adapter content was reduced substantially in the post-trim FastQC/MultiQC summaries, supporting the decision to use the cleaned reads for alignment.

### Why this matters
This directly addresses the faculty guidance and makes the alignment handoff defensible.

---

## 1.5 Reference genome choice must be justified
**Priority:** High  
**Source:** March 16 meeting transcript with Dr. Osier.

### Feedback captured
Dr. Osier warned not to assume the source paper's reference choice was automatically correct. He told the group to think through which mouse reference matched the data and to avoid inappropriate strain-specific references such as SCID-related references if they did not fit the dataset.

### Required action
The Data Preparation section should justify the reference choice:

- the dataset is mouse DRG RNA-seq
- the selected genome was *Mus musculus* GRCm39 primary assembly
- the annotation was Ensembl release 115
- the genome FASTA and GTF were matched
- strain-specific or mismatched references were avoided

### Suggested Methods sentence
> The GRCm39 primary assembly and matching Ensembl release 115 annotation were selected to keep the genome FASTA and gene-model coordinate system consistent while avoiding strain-specific references that were not appropriate for the retained mouse DRG subset.

### Why this matters
This turns Dr. Osier's reference-selection warning into a visible Methods justification.

---

## 1.6 Final claims should use one official shared workflow path
**Priority:** High  
**Source:** March 16 meeting transcript and project workflow discussion.

### Feedback captured
The group discussion clarified that final reported results should come from the shared/official workflow outputs, not separate exploratory local runs.

### Required action
The paper should make clear that reported QC, alignment, DE, and GO results come from the retained 20-sample workflow path.

### Suggested sentence
> All reported QC, alignment, differential-expression, and enrichment results refer to the retained 20-sample `family_drg_novaseqx` workflow outputs rather than exploratory local test runs.

### Why this matters
This prevents inconsistency between individual exploratory analyses and the official paper results.

---

# 2. Confirmed faculty-style comments already present in the Google Doc

These comments are marked as faculty or appear in the current Google Doc feedback block. If the group later confirms authorship as Dr. Osier, move them into Section 1.

## 2.1 Tighten the Introduction transition
**Priority:** High

### Feedback captured
The Introduction starts broadly with neurological injury, then shifts abruptly into the AhR mouse DRG dataset.

### Required action
Add a stronger bridge from general neurological injury to the specific mouse DRG sciatic nerve injury dataset.

### Suggested bridge
> To study this question in a defined injury model, this project reanalyzed a published mouse dorsal root ganglion RNA-seq dataset collected one day after sciatic nerve injury, with particular focus on how AhR loss changes the balance between stress-response and regeneration-associated transcriptional programs.

---

## 2.2 Remove repeated statements about side-specific injury being strongest or WT being clearest
**Priority:** High

### Feedback captured
The draft repeats that side-specific injury contrasts carried the strongest signal and that the WT/FF branch remained the clearest pathway-level result.

### Required action
Keep the side-specific-strongest idea once, preferably in Discussion. Remove or soften repeated versions in Results and Methods.

### Suggested Results replacement
> Bend-point narrowing was applied to the two side-specific branches to convert large differential-expression outputs into smaller follow-up sets suitable for pathway-level interpretation.

### Suggested Discussion replacement
> The PCA and sample-distance structure supported prioritizing side-specific contrasts, while genotype remained a secondary but biologically relevant layer.

### Why this matters
Repetition weakens the narrative and makes the paper sound like it is over-arguing one point.

---

## 2.3 Methods should not include interpretive branch-ranking language
**Priority:** High

### Feedback captured
The phrase `which remained the clearest pathway-level follow-up` does not belong in Methods.

### Required action
Keep Methods descriptive and move interpretive branch ranking to Results or Discussion.

### Preferred Methods sentence
> For the side-specific follow-up, retained GO outputs were re-analyzed with term-gene membership preserved and summarized using ranked-chart, clustering-tree, and shared-gene network views to reduce redundancy among overlapping GO labels.

---

# 3. Non-Osier team feedback and draft cleanup items

## 3.1 Software version table vs versions at first mention
**Priority:** Medium

### Feedback captured
Nikhi questioned whether a standalone software-version table is normal.

### Resolution
Keep the information because software versions are required, but make the format clean:

- versions at first mention in prose
- compact table if retained
- no extra/non-final tools unless clearly marked as exploratory

### Why this matters
This satisfies the professor's versioning requirement while addressing the team's formatting concern.

---

## 3.2 Use WT in prose instead of FF
**Priority:** Medium

### Feedback captured
Team feedback: terming FF as WT, as done in the Introduction, is more informative than saying FF.

### Required action
Use `WT` in narrative prose, headings, captions, and tables. Keep `ff` only in code labels and filenames.

### Replace in prose
- `FF branch` -> `WT branch`
- `FF-only genes` -> `WT-only genes`
- `FF GO follow-up` -> `WT GO follow-up`
- `seen in FF` -> `seen in WT`

### Do not replace
- `ipsi_vs_contra_in_ff`
- file names
- saved contrast labels
- genotype-code explanations where `ff` is being defined

---

## 3.3 Clarify vague `main` wording
**Priority:** Medium

### Feedback captured
Comments asked: `what does main mean here?`

### Required action
Replace vague phrases like `main side-specific branches`.

### Suggested replacement
> the two side-specific branches carried forward for GO follow-up

### Why this matters
`Main` is vague. The paper should say whether the branches were selected because of PCA structure, follow-up priority, or GO analysis scope.

---

## 3.4 Make Figure 14 explicitly WT-only
**Priority:** Medium

### Feedback captured
Team asked whether Figure 14 only looked at FF/WT.

### Required action
Caption should clearly say the figure is WT-only.

### Suggested caption
> Figure 14. WT upregulated GO Biological Process follow-up for the ipsilateral-versus-contralateral branch. The ranked chart and shared-gene network summarize enriched GO Biological Process terms supported by the 709-gene WT bend-point follow-up set.

---

## 3.5 Define `core injury-response program` using counts
**Priority:** Medium

### Feedback captured
Team comment: `what does this mean?`

### Required action
Replace vague wording with the measurable overlap result.

### Suggested replacement
> The two narrowed side-specific branches shared 620 genes, meaning that most of the WT follow-up set also appeared in the cKO follow-up set. This shared gene set was treated as the common injury-response backbone, while the WT-only and cKO-only genes were used to evaluate branch-specific differences.

---

## 3.6 Use Venn diagrams carefully
**Priority:** Medium

### Feedback captured
Team asked why Sam's Venn diagrams were not used.

### Required action
Use a Venn diagram only if it adds clarity beyond the overlap table. Do not place a Venn diagram immediately beside a table that repeats the exact same numbers unless the visual is doing explanatory work.

### Suggested placement
Use the best Venn diagram in `Data Validation of Source Dataset` or in the comparison section linking project findings to the source study.

---

## 3.7 Delete or justify the cKO-specific divergence row
**Priority:** Medium

### Feedback captured
Team comment says `DELETE` near:

> Main cKO-specific divergence: phosphorylation / phosphate-containing compound metabolic process

### Required action
Delete the row unless a short paragraph explains exactly how that divergence was derived and why it matters.

---

## 3.8 Move anchor-gene interpretation into Discussion
**Priority:** Medium

### Feedback captured
Team comment says `Move to discussion` near the anchor-gene paragraph.

### Required action
Keep Results factual; move biological interpretation to Discussion.

### Results version
> Recurring anchor genes in the WT GO follow-up included Atf3, Gadd45a, Jun, Sox11, and Flrt3.

### Discussion version
> These recurring genes provide a bridge between broad GO labels and biologically recognizable injury-response and remodeling markers, helping connect the global reanalysis back to the original paper's candidate-gene logic.

---

## 3.9 Fix missing citations and citation placeholders
**Priority:** High

### Required citation fixes
- DRG motor-response sentence should cite Link et al. (2023).
- `Zuo et al.` should be corrected to `Zou et al. (2009)` if the reference list uses Zou et al.
- Demyelinating pathology / neuron-intrinsic interpretation should cite Halawani et al. (2023).
- Source-paper claims about stress response and axon regeneration should cite Halawani et al. (2023).
- Placeholder `(LINK)` must be replaced or deleted.

---

## 3.10 Remove unfinished placeholders before final submission
**Priority:** High

### Search for and resolve
- `LINK`
- `Figure X`
- `Table X`
- `[Future Directions]`
- `[Limitations]`
- empty bracket placeholders
- unfinished section headings

### Why this matters
Placeholders are finalization blockers and make the paper look unfinished.

---

# 4. Recommended revision order

1. Add any missing Dr. Osier email-only feedback if found in another inbox.
2. Confirm final `.docx` formatting requirements.
3. Fix Introduction transition and source citations.
4. Make Methods descriptive and reproducible.
5. Add software versions at first mention and keep/clean the compact version table.
6. Justify GRCm39 / Ensembl release 115 reference choice.
7. Remove repeated side-specific strongest / WT-clearest statements.
8. Standardize WT terminology in prose while preserving `ff` code labels.
9. Resolve Figure 14, Venn diagram, and table-row comments.
10. Move anchor-gene interpretation into Discussion or shorten it in Results.
11. Fill Future Directions and Limitations.
12. Do a final citation-reference cross-check.
13. Export from Word/LibreOffice/OpenOffice and submit the `.docx`.

---

# 5. Fast action checklist

## Must fix before submission
- [ ] No unresolved `LINK`, `Figure X`, `Table X`, `[Future Directions]`, or `[Limitations]` placeholders.
- [ ] All source-paper biological claims have citations.
- [ ] Paper has at least 15 primary sources.
- [ ] Final paper is 30-50 pages.
- [ ] Figures/tables are not more than half of paper length.
- [ ] Final file is `.docx` from Word/LibreOffice/OpenOffice.
- [ ] All individual contribution colors are identifiable.

## Piter-owned priority fixes
- [ ] Add/verify software versions.
- [ ] Keep Methods descriptive.
- [ ] Justify reference genome choice.
- [ ] Standardize WT/ff terminology.
- [ ] Remove repeated side-specific / WT-clearest language.
- [ ] Clarify GO follow-up figure/table wording.
- [ ] Move anchor-gene interpretation if the group agrees.

## Team-owned priority fixes
- [ ] Tighten Introduction transition.
- [ ] Fix missing citations in Introduction.
- [ ] Finish Discussion limitations and future directions.
- [ ] Decide whether to keep or move the Venn diagram.
