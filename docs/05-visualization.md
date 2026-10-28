# 05 Visualization and Result Interpretation

[Home](../README.md) · [Previous chapter](04-conjunction-contrast.md) · [Next chapter](06-quality-and-reporting.md)

## Purpose

Display results on an appropriate anatomical template and describe the image layers, color scale, direction, and statistical meaning. Record display adjustments separately from statistical thresholds.

## Inputs

- Final images from a single-dataset, conjunction, or contrast analysis, with their corresponding run records.
- An anatomical template in the corresponding space.
- Peak/cluster tables, sources of anatomical labels, and the analysis direction.
- Mango or another image viewer.

## Procedure

### 1. Identify the Image Type First

| Image type | What it can show | Interpretation to avoid |
| --- | --- | --- |
| ALE-value map | The distribution of convergence statistics | BOLD magnitude, effect size, or the probability of a psychological function |
| Z map | Z values from the statistical output | Raw ALE values |
| P-value map | P values for the corresponding test | Assuming multiple-comparison correction from the colors alone |
| Cluster-label map | Cluster identifiers and locations | A continuous measure of statistical significance |
| Conjunction map | Shared regions under the specified input conditions | A pooled result or a newly averaged effect size |

Distinguish unthresholded value maps from final thresholded maps. Select images using the output list for the relevant analysis rather than choosing an arbitrary `.nii` file.

### 2. Select an Underlay and Check Alignment

Choose an anatomical underlay that matches the analysis space through the [official template resources](https://brainmap.org/ale/). Record its name, source, and resolution. Use the documented correspondence among MNI space, Talairach space, and the specific templates.

After loading the images, check left–right orientation, coordinate units, spatial geometry, and obvious misalignment. Images may have different resolutions and still align correctly, but their spatial geometry must correspond. Their shared appearance as brain images is not evidence of alignment. If a problem appears, inspect the image headers and processing records. Do not change origins or flip images solely to obtain visual overlap without documenting the change.

### 3. Add an Overlay in Mango

In Mango:

1. Start Mango and open the anatomical template as the underlay.
2. In the same viewer, select `File → Add Overlay`.
3. Load the verified final statistical image.
4. Check the layer filename, comparison direction, and image type.
5. Select axial, coronal, or sagittal views and the required slice positions. Record the coordinates.

See the [official Mango guide](https://mangoviewer.com/usingmango.html) for basic display operations and concepts.

### 4. Adjust the Color Scale and Display Range

According to the [official documentation](https://mangoviewer.com/usingmango_add.html), `Edit → Update to Image Range` sets the display range to the range of image values. **It does not perform a new significance test or FWE correction.**

Record the color map, lower and upper limits, opacity, handling of positive and negative values, left–right display convention, slice coordinates, interpolation, and other settings actually used. If a contrast map contains both directions, explain them clearly in the legend. When comparing several figures, state whether their display settings are identical. Different color scales should not create a misleading impression of stronger or weaker results.

Obtain the statistical thresholds from the analysis run record and document the lower display limit separately. Changing the display range of an already thresholded image does not change the statistical model.

### 5. Treat Anatomical Names as Labels with Identifiable Sources

Check the software’s peak and cluster tables. Distinguish the peak location, the spatial extent of a cluster, and its anatomical labels. State the atlas and labeling procedure. If atlases provide different names, retain the differences and their spatial context.

Do not transform correctly prepared input coordinates again merely to obtain an expected label. An automatic table label, a visual impression from a screenshot, and the final anatomical interpretation in a paper should not be treated as a single unchecked piece of evidence.

### 6. Use the Optional xjView Tool Appropriately

[xjView](https://www.alivelearn.net/xjview/download/) is an image-viewing tool that depends on MATLAB and SPM. It must be obtained and configured separately.

If it is used for supplementary inspection, identify the underlay and atlas. Its p-value slider does not replace the inference already performed in GingerALE. Do not treat an ALE-value map as an SPM t or F map and apply another p threshold without understanding the statistic and image-header information. Base interpretation on the final statistical image and GingerALE result tables.

### 7. Save Figures with Reusable Legends

A figure legend should answer:

- Which dataset, direction, and analysis run does the figure represent?
- Does the color scale show ALE values, Z values, p values, or cluster identifiers?
- Which coordinate space and template were used?
- What were the statistical thresholds, correction method, and number of permutations?
- What were the display range, left–right convention, and slice coordinates?

The [run record template](../templates/run-record.md) includes a display-settings table, and the [reporting outline](../templates/reporting-outline.md) includes figure-legend fields.

## Outputs

Retain the figures, legends, display-settings table, corresponding original statistical images, and run IDs. A screenshot alone is insufficient if its relationship to the input and parameters has been lost.

Use the [interpretation exercises](../examples/interpretation-practice.md) to practice distinguishing display operations from statistical inference. Then complete the checks in [Quality Checks, Sensitivity Analysis, and Reporting](06-quality-and-reporting.md).

## References

[Publications and official documentation](../references/README.md) · [BrainMap forum notes](07-forum-faq.md)
