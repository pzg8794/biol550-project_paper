# BIOL550 paper add-in draft — Piter findings from 04/02, 04/09, and 04/16

This draft is designed to be pasted into the Google Doc **without rewriting the rest of the paper**. It focuses on the latest Piter-owned findings and keeps the additions anchored to the existing DE -> GO story.

---

## Recommended placement in the paper

### 1) Results — add a new subsection
**Insert after:** the current **Gene Ontology Analysis** section  
**Insert before:** **Discussion**

**New subsection title:**  
**GO Follow-up of the Main Side-Specific Branches**

This is the best place for the 04/09 and 04/16 material because it extends the existing GO result instead of starting a new story.

---

## Priority order for additions

### Must add
1. **FF upregulated GO follow-up paragraph**
2. **Figure: FF chart view + FF network view**
3. **FF vs cKO overlap table**
4. **Anchor-gene paragraph**

### Strong add
5. **Anchor-gene companion table**
6. **Short branch-comparison paragraph**

### Optional add
7. **Direction-split table (upregulated vs downregulated)**
8. **FF tree view**
9. **Downregulated heatmap as contrast-only figure**

---

# READY-TO-PASTE RESULTS TEXT

## A. New subsection heading
### GO Follow-up of the Main Side-Specific Branches

After the initial GO enrichment analysis identified the side-specific branches as the strongest follow-up path, the `ipsi_vs_contra_in_ff` Biological Process result was re-analyzed with retained term-gene membership to reduce redundancy among overlapping labels. Rather than treating the enriched output as a long list of independent pathway findings, the follow-up used ranked-chart, clustering-tree, and shared-gene network views to determine which terms were repeatedly supported by the same underlying gene neighborhood. This refinement showed that the strongest FF upregulated signal did not represent many unrelated pathway stories. Instead, the top GO terms repeatedly collapsed into a smaller set of recurring biological neighborhoods centered on signaling and regulation, cell migration or morphogenesis, stress and injury response, and neurogenesis or developmental remodeling.

The same follow-up also clarified that the GO result was structurally asymmetric. The upregulated branch carried the main interpretable pathway-level signal, whereas the downregulated branch remained much thinner and was driven mainly by synaptic-modulation and nervous-system-development terms. This asymmetry supports using the FF upregulated branch as the main pathway-level result in the paper, with the downregulated branch retained only as secondary context rather than as a parallel biological narrative.

Comparison of the narrowed side-specific branches showed that the FF and cKO follow-up sets were largely built on the same core injury-response program. The two bend-point-selected branches shared 620 genes, leaving 89 FF-only genes and 250 cKO-only genes, and they also shared 14 of the top 20 retained GO terms. This indicates that the cKO branch preserves most of the same core pathway structure seen in FF, while extending that shared background with additional pathway emphasis, most notably phosphorylation and phosphate-containing compound metabolic process terms.

To keep the pathway interpretation gene-supported rather than purely label-based, the strongest FF GO neighborhoods were traced back to recurring anchor genes. Across the signaling, stress-response, and neurogenesis-related themes, repeated support came from genes such as **Atf3, Gadd45a, Jun, Sox11,** and **Flrt3**. These genes help connect the pathway-level interpretation back to a smaller set of biologically recognizable injury-response and regeneration-related markers.

---

## B. Figure insertion instructions

### Figure R1 (must add)
**Insert after:** the first paragraph of the new subsection  
**Insert before:** the paragraph beginning “The same follow-up also clarified…”

**Use these two images side by side:**
- `mouse_new/differential_expression_all20/derived_analysis/ipsi_vs_contra_in_ff/shinygo_style/ff_up_chart_view.png`
- `mouse_new/differential_expression_all20/derived_analysis/ipsi_vs_contra_in_ff/shinygo_style/ff_up_network_view.png`

**Caption:**
**Figure R1.** FF upregulated GO Biological Process follow-up shown as a ranked chart and shared-gene network. The strongest enriched terms cluster around signaling and regulation, migration or morphogenesis, stress response, and neurogenesis or developmental remodeling. Shared-gene overlap indicates that many top labels are supported by the same underlying injury-response neighborhood rather than by many independent pathway signals.

---

### Figure R2 (optional but good)
**Insert after:** the paragraph beginning “The same follow-up also clarified…”  
**Insert before:** the FF vs cKO comparison paragraph

**Use this image:**
- `mouse_new/differential_expression_all20/derived_analysis/ipsi_vs_contra_in_ff/shinygo_style/ff_up_tree_view.png`

**Caption:**
**Figure R2.** Hierarchical clustering of FF upregulated GO terms based on shared-gene overlap. The retained terms group into a smaller number of recurring neighborhoods, supporting interpretation of the FF branch as a compact injury-response program rather than a long list of separate pathway findings.

---

### Figure R3 (optional contrast-only figure)
**Insert after:** Figure R2 or near the sentence describing the thinner downregulated branch

**Use this image:**
- `mouse_new/differential_expression_all20/derived_analysis/ipsi_vs_contra_in_ff/shinygo_style/ff_down_distance_heatmap.png`

**Caption:**
**Figure R3.** Distance-heatmap view of the FF downregulated GO branch. Compared with the upregulated branch, the downregulated signal is much thinner and is driven mainly by synaptic-modulation and nervous-system-development terms, supporting its use as secondary context rather than as the main pathway-level result.

---

## C. Table insertion instructions

### Table R1 (must add)
**Insert after:** the FF vs cKO comparison paragraph  
**Insert before:** the anchor-gene paragraph

**Title:**
**Table R1.** Overlap summary for the two narrowed side-specific branches.

| Metric | Value |
|---|---:|
| FF bend-point genes | 709 |
| cKO bend-point genes | 870 |
| Shared genes | 620 |
| FF-only genes | 89 |
| cKO-only genes | 250 |
| Shared top GO terms | 14 of 20 |
| Main cKO-specific divergence | phosphorylation / phosphate-containing compound metabolic process |

---

### Table R2 (strong add)
**Insert after:** the anchor-gene paragraph  
**Insert before:** Discussion

**Title:**
**Table R2.** Anchor-gene companion summary for the FF GO follow-up.

| Theme | Example retained terms | Recurring anchor genes |
|---|---|---|
| Injury / stress response | response to stress; regulation of apoptotic process; response to wounding | **Atf3, Gadd45a, Jun** |
| Signaling / regulation | intracellular signal transduction; cell surface receptor signaling; MAPK-related regulation | **Atf3, Jun, Gadd45a** |
| Neurogenesis / remodeling | neurogenesis; nervous system development; neuron projection morphogenesis | **Sox11, Flrt3** |
| Migration / morphogenesis | cell migration; regulation of cell shape; positive regulation of locomotion | **Flrt3, Sox11** |

---

## D. Optional extra Results block from the 04/16 final wrap-up

If you want to use more of the late-stage material because the paper still has room, add this as a **second small subsection** before Discussion.

### New optional subsection title
### Direction Split and Anchor-Gene Interpretation

The final GO wrap-up showed that the FF branch was not only the clearest pathway-level result, but also the only direction that carried substantial pathway-level signal. In the upregulated query, 567 genes produced 388 enriched GO Biological Process terms, with the strongest term reaching approximately -log10(p) = 32. By contrast, the downregulated query contained 90 genes and yielded only 4 enriched GO terms, with much weaker statistical support. This imbalance justifies centering the main biological interpretation on the FF upregulated branch rather than presenting the two directions as equally informative.

The same follow-up also strengthened the interpretation at the gene level. Within the bend-point core, the most prominent upregulated genes included **Atf3, Flrt3, Gadd45a, Sox11,** and **Jun**, which together support an injury-response and regeneration-centered transcriptional program. In contrast, the strongest downregulated genes were more weakly interpretable and were more consistent with reduced homeostatic or synaptic-state signaling than with a parallel regenerative program. Taken together, the anchor-gene and GO results support the interpretation that ipsilateral FF neurons are engaged in a coherent transcriptional injury-response state rather than displaying many disconnected expression changes.

### Table R3 (optional)
**Insert after:** the first paragraph of the optional subsection

**Title:**
**Table R3.** Direction split summary for the FF GO follow-up.

| Branch | Query genes | Enriched GO terms | Best -log10(p) | Median gene coverage |
|---|---:|---:|---:|---:|
| Upregulated | 567 | 388 | 32.0 | 0.089 |
| Downregulated | 90 | 4 | 2.45 | 0.259 |

---

# SHORT METHODS ADDITION (recommended)

If you add the new Results material, add this short Methods paragraph too.

**Insert after:** the existing paragraph that introduces GO enrichment in **Materials and Methods**  
**Insert before:** the paragraph that moves fully into interpretation or downstream summaries

**Ready-to-paste text:**

For the main side-specific follow-up, the GO Biological Process enrichment output was re-run with retained term-gene membership so that redundancy among enriched labels could be evaluated directly. Terms were then summarized using ranked-chart, clustering-tree, and shared-gene network views, and overlapping terms were interpreted as recurring neighborhoods when they were supported by the same underlying gene set. In the final FF branch wrap-up, additional scoring and reduction steps were used to prioritize terms supported by both strong statistical significance and meaningful gene-set coverage, and recurring anchor genes were traced back from the strongest retained GO neighborhoods to connect the pathway summary to named genes.

---

# DISCUSSION ADDITION (optional but strong)

If you want the late findings to show up more clearly in Discussion, add this short paragraph.

**Insert after:** the paragraph that currently says the FF branch is the clearest pathway-level result  
**Insert before:** the paragraph that begins caution/limitations

**Ready-to-paste text:**

The later GO follow-up sharpened this interpretation by showing that the apparent abundance of enriched FF terms was driven largely by overlapping gene membership rather than by many unrelated pathway stories. Once the output was reduced with chart, tree, and network views, the main upregulated branch consistently converged on a smaller set of recurring themes: signaling and regulation, migration or morphogenesis, stress and injury response, and neurogenic remodeling. Comparison with the cKO branch further showed that most of this pathway-level signal was shared, while the cKO branch extended the same core with a smaller number of additional pathway features, especially phosphorylation-related terms. This makes the FF branch the clearest biological centerpiece, while still leaving room to discuss how genotype background modifies the shared injury-response program.

---

# BEST FIGURES TO PULL FROM THE REPOS

## Highest-value figures
1. `mouse_new/differential_expression_all20/derived_analysis/ipsi_vs_contra_in_ff/shinygo_style/ff_up_chart_view.png`
2. `mouse_new/differential_expression_all20/derived_analysis/ipsi_vs_contra_in_ff/shinygo_style/ff_up_network_view.png`
3. `mouse_new/differential_expression_all20/derived_analysis/ipsi_vs_contra_in_ff/shinygo_style/ff_up_tree_view.png`
4. `mouse_new/differential_expression_all20/derived_analysis/ipsi_vs_contra_in_ff/shinygo_style/ff_down_distance_heatmap.png` (contrast only)

## If you want one more DE-side image already aligned with this story
5. the ordered adjusted-p-value / cumulative bend-point diagnostic for the main FF branch
6. the sample-to-sample distance heatmap if it is not already cleanly placed in the paper

---

# WHAT TO LEAVE OUT

Do **not** add:
- notebook screenshots
- code blocks
- every GO panel
- too many downregulated figures
- a second full GO section that repeats the existing one

The paper should gain **one compact follow-up block**, not a second weekly report.

---

# CITATION SUPPORT YOU CAN TIE TO THESE ADDITIONS

These additions are supported by the weekly report sequence:
- 04/02: branch-priority logic, PCA-first interpretation, bend-point narrowing, and contrast ranking
- 04/09: retained term-gene membership and FF chart/tree/network follow-up
- 04/16: FF vs cKO overlap summary, anchor genes, direction asymmetry, and four-theme biological reduction

---

# SIMPLE INSERT PLAN

If you are tired and need the fastest path, do only this:

1. Add subsection **GO Follow-up of the Main Side-Specific Branches**
2. Paste the first four Results paragraphs from section A
3. Add **Figure R1** (chart + network)
4. Add **Table R1** (overlap summary)
5. Add **Table R2** (anchor-gene companion summary)
6. Add the short Methods paragraph

That will materially improve the paper without blowing up the structure.
