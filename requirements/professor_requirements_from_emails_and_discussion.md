# Professor Requirements from Emails and Course Discussion

This document converts Dr. Osier's email feedback and course discussion posts into an actionable final-paper requirements checklist for the BIOL550 project paper. It summarizes requirements and revision expectations without copying the full email threads.

## Source set used

- Dr. Osier email feedback dated 2026-04-09: `HTS: Feedback for Zebrafish`
- Dr. Osier general course discussion dated 2026-04-09: `Draft feedback process` and `General feedback on drafts`
- Dr. Osier email feedback dated 2026-04-16: `HTS: Zebrafish feedback`
- Dr. Osier email feedback dated 2026-04-23: `HTS: Zebrafish feedback`
- Course discussion screenshot: `Data set requirements`
- Zoom meeting assets / summary dated 2026-03-31

---

# 1. Dataset requirements

## 1.1 Dataset must meet the course project dataset rules
**Priority:** Required

The dataset used for the project should meet these criteria:

- Must be RNA-seq.
- Should have at least 20 samples in the project.
- Must have at least 150 bp per fragment.
- Should have at least 40 million fragments per sample.

## 1.2 Dataset quality must be defensible before downstream analysis
**Priority:** Required

Before making biological claims, the paper should show that the retained dataset passed key QC checks:

- post-trim MultiQC/FastQC should support moving forward;
- adapter-content issues should be reduced after trimming;
- alignment and sample-structure outputs should support the retained subset;
- PCA, sample-distance heatmap, and dispersion plots should be interpreted clearly if included.

## 1.3 Use the new dataset consistently once it is accepted
**Priority:** Required

The March 31 meeting summary indicates that the group had received positive feedback on the post-trim MultiQC for the new dataset and should proceed with that dataset. The final paper should not mix claims from older abandoned datasets with claims from the retained mouse DRG dataset.

---

# 2. Submission and draft-process requirements

## 2.1 Submit in an editable format, not PDF
**Priority:** Required

For drafts and final submission, use a format that allows inline feedback and meets course requirements:

- MS Word, LibreOffice, or OpenOffice format.
- Do not submit a PDF if feedback is expected.
- Do not rely on Google Docs as the submitted final format.

## 2.2 One person can submit the group draft
**Priority:** Process

For future drafts, designate one person from the group to submit the draft. Not every group member needs to submit separate copies.

## 2.3 No abstract unless specifically requested later
**Priority:** Required

Dr. Osier's general draft feedback says no abstracts. Remove the abstract from the draft unless he later changes this instruction.

---

# 3. Introduction requirements

## 3.1 Do not open with generic HTS background
**Priority:** Required

The Introduction should not begin with a broad, generic high-throughput sequencing overview. It should start with the biological problem and source-paper context.

### Replace this kind of opening
- broad statements about HTS in general;
- generic statements about sequencing technology;
- course-goal language.

### Use this kind of opening instead
- why neurological injury matters;
- why the source paper is biologically interesting;
- what specific aspect of the source paper this reanalysis focuses on;
- why the AhR / DRG / sciatic nerve injury system matters.

## 3.2 Sell the importance of neurological injury with concrete evidence
**Priority:** Required

The Introduction must explain why neurological injuries matter. Add specific statistics where possible:

- number of injuries per year;
- impact on lives or disability burden;
- economic cost per year;
- relevance to recovery, motor function, or nerve regeneration.

## 3.3 Use more primary research citations
**Priority:** Required

The draft needs many more primary research article citations, especially in the Introduction and Discussion.

### Citation targets
Add citations for:

- neurological injury burden and relevance;
- DRG biology / regeneration relevance;
- AhR role in stress response, proteostasis, or regeneration context;
- sciatic nerve injury / axon regeneration model;
- RNA-seq reanalysis methods and pathway/enrichment interpretation where needed.

## 3.4 Explain the source paper clearly
**Priority:** Required

The Introduction should explain:

- why the source paper is interesting;
- what biological question the source paper asked;
- how the source paper performed the study;
- what part of the source paper/data this project focuses on;
- how this project uses the source data.

## 3.5 State this project's biological contribution, not only course workflow completion
**Priority:** Required

Do not end the Introduction by saying the group completed basic RNA-seq steps. That is the course objective, not the study objective.

### Better framing
The final Introduction should answer:

> What did this reanalysis contribute to understanding the biology of injury response, AhR genotype context, or pathway-level interpretation?

## 3.6 Intro figures are allowed only if they clarify a concept
**Priority:** Optional / Use carefully

Figures can be added to the Introduction if they help explain a concept, but they should not be filler. Any Intro figure should clarify the system, pathway, injury model, or experimental design.

---

# 4. Materials and Methods requirements

## 4.1 Use many clear subheadings
**Priority:** Required

The Materials and Methods section should be organized with explicit subheadings. Recommended order:

1. Dataset and sample metadata
2. Data acquisition
3. Quality control and trimming
4. Reference genome and annotation
5. Alignment and count generation
6. Differential-expression modeling
7. Bend-point / follow-up gene-set selection
8. Functional enrichment / GO analysis
9. Software versions and reproducibility

## 4.2 Keep M&M factual and limited to methods used
**Priority:** Required

Materials and Methods should describe what was done. It should avoid:

- speculation;
- interpretation of biological meaning;
- ranking branches as biologically strongest;
- discussion-style claims;
- tools or analyses that were not actually used in the retained workflow.

## 4.3 Include a sample/subject table early in M&M
**Priority:** Required

Include a table of samples/subjects early in the Methods section with what is known about each group.

### Minimum table content
- sample group;
- side/class or injury condition;
- genotype;
- number of samples;
- tissue/source;
- time point;
- sequencing platform;
- accession/source dataset.

## 4.4 Cite every tool used
**Priority:** Required

Every tool/resource used in the workflow needs a citation or source reference.

### Tools/resources that need citations or formal references
- SRA Toolkit / NCBI accessions
- FastQC
- MultiQC
- fastp
- STAR
- Ensembl reference genome and annotation
- DESeq2
- g:Profiler/gprofiler2
- Gene Ontology
- KEGG
- Reactome
- any plotting/statistical package if emphasized as methodological

## 4.5 Do not use one standalone table as the only place where tools appear
**Priority:** Required

Instead of relying on a single table of tools, introduce and cite each tool in the Methods subsection where that tool was used.

### Correct pattern
- Dataset subsection: cite SRA/GEO/BioProject.
- QC subsection: cite FastQC, MultiQC, fastp.
- Alignment subsection: cite STAR and Ensembl/GRCm39.
- DE subsection: cite DESeq2.
- Enrichment subsection: cite g:Profiler, GO, KEGG, Reactome.

A compact software/version table can remain for reproducibility, but it should supplement the Methods prose, not replace it.

## 4.6 Give sample commands for every tool used
**Priority:** Required for this class paper

Dr. Osier noted that this is not always done in published papers, but should be done here to make the paper more reproducible.

### Include sample commands/code for
- prefetch / fasterq-dump
- FastQC
- MultiQC
- fastp
- STAR index/alignment
- count matrix assembly or GeneCounts handoff
- DESeq2 model setup
- bend-point/follow-up script if used
- g:Profiler query

## 4.7 Report specific non-default parameters and explain why each was changed
**Priority:** Required

For parameters different from defaults:

- give the exact parameter name;
- give the exact value;
- explain why it was changed;
- avoid vague descriptions when similar parameters exist.

### Example requirement
Do not write only:

> quality trimming was applied.

Write something like:

> fastp was run with `--cut_mean_quality 20` to remove lower-quality sequence regions and `--length_required 30` to discard reads too short for reliable alignment after trimming.

---

# 5. Results requirements

## 5.1 Cite every figure and table in the prose
**Priority:** Required

Each figure/table must be explicitly referenced in the Results text before or near where it appears.

### Fix pattern
Use: `Figure 5 shows...` or `As shown in Figure 5,...`

Do not drop a figure into the section without prose explanation.

## 5.2 For every figure/table, say what is interesting about it
**Priority:** Required

The Results text must tell the reader what to notice.

### For each figure/table, include
- the main pattern;
- hard numbers where possible;
- any outliers;
- unusual columns, groups, or aggregate patterns;
- whether the result supports moving to the next analysis step.

## 5.3 Results should report factual findings; interpretation belongs mostly in Discussion
**Priority:** Required

Use Results for observed patterns and quantitative outputs. Move speculation, opinion, and broader biological interpretation to Discussion.

### Results language
> PC1 separated ipsilateral and contralateral samples and explained 46.2% of variance.

### Discussion language
> This separation suggests that injury side dominated the transcriptomic response in the retained dataset.

## 5.4 Avoid very short two-sentence paragraphs
**Priority:** Required

Dr. Osier repeatedly flagged two-sentence paragraphs. Expand or merge them.

### Fix strategy
For a short paragraph about a figure, add:

- a second quantitative observation;
- an outlier/pattern note;
- a transition to the next result;
- a statement explaining why the result matters for the next step.

## 5.5 Use hard numbers wherever possible
**Priority:** Required

When describing figures and tables, add exact values:

- sample counts;
- percent variance explained;
- mapped-read percentages;
- number of genes retained;
- p-value or adjusted-p-value thresholds;
- overlap counts;
- number of enriched terms;
- top fold enrichment or FDR values.

## 5.6 Curate and explain key figures before presenting or submitting
**Priority:** Required

From the March 31 meeting summary, the group needed to curate graph interpretations for Osier/class. The final paper should do the same for the retained figures.

### Minimum expected explanation for core figures
- PCA: what clusters, by which variable, and how much variance is explained.
- Sample-distance heatmap: whether replicates group consistently and whether groups separate.
- Dispersion plot: whether technical variance appears controlled enough for DESeq2 modeling.
- Volcano/MA plots: what thresholds were used and what the up/down structure shows.
- GO/network figures: what biological-process neighborhoods are supported and what overlaps mean.

---

# 6. Discussion requirements

## 6.1 Discussion needs more depth
**Priority:** Required

The Discussion should not merely restate results. It should explain what the findings mean in the context of the biological problem and source paper.

## 6.2 Include limitations
**Priority:** Required

The Discussion must include limitations of the work.

### Strong limitations to include
- reanalysis depends on the original experimental design;
- bulk RNA-seq cannot identify cell-type-specific effects;
- GO terms are redundant and can overstate breadth of biological interpretation;
- bend-point narrowing is a follow-up heuristic, not an independent biological threshold;
- transcriptomic differences do not prove functional regeneration outcomes;
- the group did not replicate wet-lab validation from the source study.

## 6.3 Include future directions
**Priority:** Required

The Discussion should explain what future research could do next.

### Strong future directions
- qPCR validation for selected anchor genes;
- comparison with the source paper's RSS-selected genes;
- pathway validation focused on AhR/stress/proteostasis and regeneration markers;
- cell-type-specific or single-cell follow-up if available;
- alternative splicing analysis only if it is justified and not left as a placeholder;
- targeted analysis of cKO-specific follow-up genes.

## 6.4 Keep interpretation/speculation mainly in Discussion
**Priority:** Required

Interpretive claims such as which branch is biologically clearest, what the pathway shifts mean, or what AhR knockout may imply should be placed in Discussion, not Methods and not overdone in Results.

## 6.5 Compare this reanalysis to the source paper
**Priority:** Required / Strong

The Discussion should explain how the group's results agree with, extend, or differ from the source paper.

### Questions to answer
- Does the reanalysis support the source paper's claim that injury is the dominant axis of variance?
- What does the genotype/cKO signal add?
- How does the global DE approach differ from the source paper's response-shift / RSS-style approach?
- Which findings are consistent with AhR/stress/growth balance?
- Which findings are weaker, unexpected, or require caution?

---

# 7. Writing, grammar, and style requirements

## 7.1 Run spelling, grammar, and style checks
**Priority:** Required

Dr. Osier explicitly said to examine anything flagged by spelling/grammar/style checking.

## 7.2 Write like a scientific article, not a lab report
**Priority:** Required

Avoid course-process language such as:

- `we completed basic RNA-seq steps`;
- `we ran the tools`;
- `this was done for class`;
- `the next step was...` without scientific framing.

Use scientific-article framing:

- biological question;
- reproducible methods;
- results as evidence;
- discussion of biological meaning and limitations.

## 7.3 Avoid filler
**Priority:** Required

Remove broad, vague, or decorative text that does not advance the paper.

### Common filler to remove
- generic high-throughput sequencing background not tied to the study;
- overly broad injury statements without evidence;
- treatment-oriented claims not supported by the reanalysis;
- unnecessary intro figures or long tool descriptions.

---

# 8. Final paper checklist from these professor requirements

## Must do
- [ ] Dataset meets RNA-seq, sample count, read length, and depth expectations or limitations are explained.
- [ ] Draft/final file is submitted in editable Word/LibreOffice/OpenOffice format, not PDF.
- [ ] Abstract removed unless later requested.
- [ ] Introduction starts with the biological problem, not generic HTS background.
- [ ] Neurological injury importance is supported with statistics and citations.
- [ ] Introduction explains source paper, focus, data use, and biological contribution.
- [ ] More primary research citations added.
- [ ] M&M uses subheadings and factual workflow structure.
- [ ] Sample/subject table appears early in M&M.
- [ ] Every tool/resource is cited in the relevant Methods subsection.
- [ ] Sample commands are included for every major tool used.
- [ ] Non-default parameters include exact values and justification.
- [ ] Every figure/table is cited in prose.
- [ ] Every figure/table has explanation of pattern, outliers, hard numbers, or unexpected features.
- [ ] Results avoid speculation and keep most interpretation for Discussion.
- [ ] Two-sentence paragraphs are expanded or merged.
- [ ] Discussion includes limitations.
- [ ] Discussion includes future directions.
- [ ] Writing reads like a scientific article, not a lab report.
- [ ] Spelling/grammar/style flags are checked.

## Strongly recommended
- [ ] Keep a compact software/version table only as a reproducibility supplement.
- [ ] Add one Intro figure only if it clarifies the study system or pathway.
- [ ] Use hard numbers throughout Results.
- [ ] Explicitly compare this reanalysis to the source paper's approach and conclusions.
- [ ] Keep cKO/AhR biology central so the paper does not become only an injury-side comparison.
