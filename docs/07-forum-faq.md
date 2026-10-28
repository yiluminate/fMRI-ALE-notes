# 07 Notes from the BrainMap Developer Forum

[Home](../README.md) · [References](../references/README.md)

Common methodological questions and responses from BrainMap developers.

## 1. If Two Groups Have Different Sample Sizes, Should Subjects Be Their Sum?

**Original post:** [Different N for different contrasts, Mick Fox, 2018-01-22](https://brainmap.org/forum/viewtopic.php?p=1975#p1975).

**Main point:** For the two-group contrast discussed in the post, the smaller group size was recommended as a conservative representation of spatial uncertainty around the peaks.

**Considerations:** Retain both original sample sizes and the basis of the entered value. Do not add them by default. Different effective samples, partial overlap, and complex repeated-measures designs require further assessment. This response does not resolve every sample-size definition.

## 2. How Many Experiments Should Be Created from Multiple Contrasts in One Publication?

**Original post:** [Study vs. experiment, with follow-up responses by Mick Fox on 2014-02-11 and 2019-07-11](https://brainmap.org/forum/viewtopic.php?t=204).

**Main point:** Related contrasts from the same sample can be combined into one group, whereas genuinely different samples can form separate groups. Participants may also be reused across publications. The 2019 response describes automatic grouping in Sleuth and notes that reuse across publications may still be missed.

**Considerations:** Use sample IDs to assess independence. Do not treat publication counts, contrast counts, and independent-group counts as interchangeable. For related contrasts based on exactly the same sample, follow the protocol to select or combine them. Record separate decisions for partial overlap. Blank lines determine parsing, not independence.

## 3. Can Only Main Effects Be Extracted from ANOVA Results?

**Original post:** [ANOVA results and combining tasks from different domains, SEickhoff, 2015-01-26](https://brainmap.org/forum/viewtopic.php?p=1486#p1486).

**Main point:** Simon’s response states that ANOVA results may be included. Their suitability depends on the question and interpretation, with particular care required for interaction effects.

**Considerations:** If directional findings are needed, check the actual comparison and its direction. Do not interpret a nondirectional F-test peak as an increase or decrease.

## 4. How Does ANOVA in an Original Study Differ from a Meta-analytic Interaction Test?

**Original post:** [How to compute interaction effect?, SEickhoff, 2012-06-21](https://brainmap.org/forum/viewtopic.php?p=1017#p1017).

**Main point:** The post discusses meta-analytic interaction testing and implementation limits in the software available at that time.

**Considerations:** Separate this question from whether peaks obtained using ANOVA in an original study are eligible. Simply subtracting previously generated contrast maps does not establish a valid interaction. An interaction test requires an appropriate statistical design and implementation.

## 5. How Should Thresholds Be Selected? Can They Be Adjusted According to Cluster Size?

**Original post:** [How to best choose threshold?, Mick Fox, 2021-03-03](https://brainmap.org/forum/viewtopic.php?p=2149#p2149).

**Main point:** The response distinguishes the cluster-forming threshold from cluster-level correction and warns that too few permutations may produce an unstable extent threshold. It mentions a cluster-level threshold of 0.01 or 0.05, at least 1,000 permutations, and exploratory attempts with several p thresholds. These refer to different parts of the procedure and should not be combined into an uncorrected final analysis plan.

**Considerations:** Prespecify the primary analysis. Document exploratory adjustments and report them separately rather than retaining only a favorable parameter set. See [Chapter 03](03-ale-analysis.md) for common starting points and permutation considerations. The forum suggestions should not be assembled into a universal parameter set.

## 6. Should Contrast Analysis Use Unthresholded or Thresholded Images?

**Original post:** [Threshold for contrast analysis, Mick Fox, 2021-03-03](https://brainmap.org/forum/viewtopic.php?p=2160#p2160).

**Main point:** The implementation discussed requires images that have already been thresholded.

**Considerations:** Record the three A, B, and pooled input images and their respective thresholds. Do not substitute raw coordinate text or unthresholded images in the earlier three-image procedure. Select the input type required by the software.

## 7. Can a Dataset with No Significant Clusters Be Compared Directly with Another Dataset?

**Original post:** [Subtraction in contrast analysis, Mick Fox, 2021-03-03](https://brainmap.org/forum/viewtopic.php?p=2159#p2159).

**Main point:** The procedure available at that time did not support a direct contrast against this type of null result. The author did not provide a confirmed alternative interpretation.

**Considerations:** Report the absence of significant clusters and check the comparison method’s input requirements. Do not present the other dataset’s significant map as a test of the difference. Significance in A and nonsignificance in B do not establish that A is significantly greater than B.

## 8. Does cFWE in the Single-Dataset Analyses Automatically Apply to the Contrast?

**Original post:** [No FWE cluster threshold for contrast/conjunction analyses?, Mick Fox, 2016-06-02](https://brainmap.org/forum/viewtopic.php?p=1724#p1724).

**Main point:** The permutation calculation in the earlier contrast procedure was distinct from adding another FWE correction step. The conjunction used the voxelwise minimum of the two input images.

**Considerations:** Report input-image thresholds separately from the contrast’s own threshold. Do not describe a simple p threshold combined with an extent restriction as cFWE. Explain the scope of correction according to the method actually used.

## 9. Can ROI-Only Studies Be Included in Whole-Brain ALE?

**Original post:** [roi studies, Mick Fox, 2018-04-05](https://brainmap.org/forum/viewtopic.php?p=1998#p1998).

**Main point:** Results obtained within a restricted search region do not share the same inferential coverage as whole-brain results and may artificially increase convergence within that region.

**Considerations:** Conventional whole-brain ALE uses coordinates from whole-brain analyses. If a publication includes both whole-brain and ROI tables, distinguish them. The exploratory local display discussed in the post does not replace formal whole-brain inference.

## 10. Does “Combining Contrasts” Mean That A > B and B > A Can Be Mixed?

**Original post:** [controlling for different contrasts in multiple comparisons, Mick Fox, 2021-03-03](https://brainmap.org/forum/viewtopic.php?p=2150#p2150).

**Main point:** The original question includes drug/placebo contrasts in both directions. The response addresses redundancy from treating the same sample as multiple independent data points and discusses the preliminary nature of small datasets.

**Considerations:** First distinguish a directional question from a question about differences in either direction. Then address sample dependence within each analysis. A result combining both directions cannot still be described as a single directional effect. Do not add opposite or unrelated results simply to reach a target count.

## 11. Must MNI Coordinates from SPM and FSL Be Transformed into Each Other?

**Original post:** [Does the difference between MNI (SPM) and MNI (FSL) matter?, Mick Fox, 2021-03-03](https://brainmap.org/forum/viewtopic.php?p=2136#p2136).

**Main point:** The options reflect the software-specific and combined fits used to derive the transformation. The response does not recommend forcing another such transformation on coordinates already in MNI space.

**Considerations:** Record the actual template, software, and previous transformations. Do not choose a transformation solely from the software name. Differences among templates and periods may still require explanation. Evaluate entries individually using [Chapter 02](02-coordinate-conversion.md).

## Three Checks When Using These Responses

1. Have the original question and subsequent corrections been read, rather than only a screenshot or an isolated reply?
2. Does the response describe software behavior, recommend a study design, or merely suggest an unconfirmed possibility?
3. Are the study design and software functions discussed in the post applicable to the present analysis?

Case-specific decisions should state the research question, applicable conditions, and methodological basis.
