# 04 Conjunction and Contrast Analyses

[Home](../README.md) · [Previous chapter](03-ale-analysis.md) · [Next chapter](05-visualization.md)

## Purpose

Distinguish pooled ALE, conjunction analysis, and contrast analysis, and compare datasets A and B using the appropriate inputs and threshold conditions.

## Inputs

- Definitions of the questions addressed by A and B, original contrast directions, foci files, and sample-grouping records.
- Completed ALE analyses for A and B, their parameters, and their final thresholded maps.
- Pooled coordinates and a separately completed pooled analysis, where required by the implementation.
- Records of coordinate space, masks, thresholds, and sample overlap between A and B.
- The comparison-input table in the [analysis run record template](../templates/run-record.md).

## Procedure

### 1. Distinguish the Three Questions

| Analysis | Procedure | Interpretation |
| --- | --- | --- |
| Pooled ALE | Organize the eligible A/B inputs according to the merging rules and run a new ALE analysis | Convergence in the combined dataset; it does not establish significance in both groups |
| Conjunction | Identify shared regions from the thresholded A/B results by taking the voxelwise minimum | Shared convergence under the specified input conditions; it is not a newly averaged effect size |
| Contrast | Compare directional differences using the two sets of inputs and a permutation model | Differences in convergence patterns; it is not a direct comparison of raw BOLD signal magnitude |

The described conjunction procedure follows Section 2.3 of the [earlier official manual](https://brainmap.org/ale/manual.pdf) and [Mick Fox’s 2016 response](https://brainmap.org/forum/viewtopic.php?p=1724#p1724).

Also distinguish between directly synthesizing original between-group contrasts, such as patients > controls, and separately synthesizing task activation in patients and controls before comparing the two meta-analytic maps. These approaches address questions at different levels. State the intended interpretation in the research protocol.

### 2. Complete the A and B Analyses Separately

Complete both single-dataset analyses using the records described in [Chapter 03](03-ale-analysis.md). Their spaces and analysis coverage must be compatible, and the threshold conditions must be explicit. Explain the rationale and implications of any differences in settings.

Count the independent groups in A and B separately. The combined A+B total cannot be presented as the number available in each group. Multiple contrasts from the same sample do not add independent experiments.

### 3. Prepare the Pooled Coordinates

1. Retain the frozen input files for A and B.
2. Use a merging function such as `Save & Merge Foci` or `Merge & Save Foci` to save a separate pooled file. Check the input requirements of that function.
3. Check duplicate experiments, sample overlap, Subjects values, and grouping. Retain the merging decisions.
4. Duplicate experiments recognized by the software do not capture every instance of actual sample overlap. Manually examine participant sources across publications.
5. Run a new single-dataset ALE analysis on the pooled input. Retain its own parameters, logs, and final thresholded map.

Merging the pooled coordinates must be followed by an ALE analysis. The coordinate text file cannot be loaded as the pooled ALE image. See [Sections 2.3 and 3.4 of the manual](https://brainmap.org/ale/manual.pdf).

If A and B share participants or contain partially overlapping samples, also address grouping and exchangeability in the comparison. Removing duplicates within each dataset does not resolve the design of the comparison as a whole.

### 4. Enter Contrast Mode and Check All Three Inputs

Enter `Contrast Studies` or `Contrast Datasets` mode and match the inputs as follows:

| Interface field or menu item | Required input |
| --- | --- |
| Data Set 1 / Open ALE Image 1 | Final thresholded ALE map for A |
| Data Set 2 / Open ALE Image 2 | Final thresholded ALE map for B |
| Pooled Data Sets / Open Pooled ALE Image | Final thresholded ALE map for the pooled dataset |

The [developer’s direct response in 2021](https://brainmap.org/forum/viewtopic.php?p=2160#p2160) confirms that the input images must already be thresholded. Do not substitute coordinate text files, unthresholded images, or Z maps from a previous contrast analysis for these three inputs.

### 5. Record Contrast Significance Settings Separately

**Using cFWE for the single-dataset analyses does not automatically provide cFWE correction for the final contrast.**

[Mick Fox’s 2016 explanation](https://brainmap.org/forum/viewtopic.php?p=1724#p1724) states that the contrast procedure at that time used permutations to calculate p values without an additional FWE permutation step. Conjunction results did not receive a new threshold and depended on the input images. The simple p threshold discussed in that response should not be interpreted as a general whole-brain correction procedure.

When setting up a contrast analysis:

- Record A/B/pooled input thresholds separately from the contrast’s own p threshold, permutation count, and extent restriction.
- Describe the inference method and its basis according to the correction options actually available in the software.
- If only a simple p threshold and an extent restriction were applied, report exactly that. Do not describe the result as cFWE- or FDR-corrected.
- If confirmatory whole-brain control of multiple comparisons is required, establish that the selected inference method provides it.

The contrast threshold and permutation count are study decisions. State the basis for each rather than combining parameters from different analysis stages into a single set.

### 6. Identify Shared Regions and Both Difference Directions Separately

Preserve the correspondence among files, tables, and logs for the conjunction, `A > B`, and `B > A` results. Do not infer direction solely from file order or the sign of image values.

`A_conj_B_ALE.xls` is a table, whereas `A_conj_B_ALE.nii` is an image. They are not interchangeable. Record `clust` or `cluster` files and ALE or Z maps according to their actual output types.

### 7. Handle Datasets with No Significant Clusters

If one dataset has no clusters surviving the prespecified thresholds, the [developer’s 2021 response](https://brainmap.org/forum/viewtopic.php?p=2159#p2159) states that the procedure then available could not contrast against that null result. Check whether the chosen comparison method supports an input with no significant clusters. Do not construct an artificial “empty control.”

In particular, “A is significant and B is not significant” does not establish that A is significantly greater than B. In the same response, the developer expressed uncertainty about interpreting A’s result as a difference. That suggestion should not be treated as an established procedure. This limitation concerns the software workflow and its inference, rather than all statistical approaches to such comparisons.

### 8. Do Not Treat Repeated Image Subtraction as an Interaction Test

Coordinates from original between-group contrasts can be organized according to the research question. However, subtracting two ALE contrast maps does not automatically yield a valid interaction test. The [author discussion](https://brainmap.org/forum/viewtopic.php?p=1017#p1017) concerns meta-analytic interaction testing and its implementation. A conventional two-group subtraction should not simply be interpreted as an interaction.

If the target question concerns a group × task interaction, develop a separate analysis plan and establish the relevant data dependencies and software implementation. Do not leave these decisions implicit within a standard two-dataset contrast.

## Outputs

Retain a table linking A/B/pooled inputs and outputs, merging decisions, complete contrast parameters, images and tables for the shared regions and both difference directions, logs, and a description of the limitations.

When proceeding to [Chapter 05](05-visualization.md), identify the selected image type and its statistical meaning.

## References

[Publications and official documentation](../references/README.md) · [BrainMap forum notes](07-forum-faq.md)
