# 03 Single-Dataset ALE Analysis

[Home](../README.md) · [Previous chapter](02-coordinate-conversion.md) · [Next chapter](04-conjunction-contrast.md)

## Purpose

Run ALE on a dataset that has passed screening, grouping, and coordinate space checks. Preserve the results together with the corresponding inputs and threshold settings.

## Inputs

- A plain-text foci file in a common coordinate space, with extraction and grouping records.
- The analysis space, mask, and output directory.
- Prespecified primary-analysis settings and a secondary-analysis plan.
- The [analysis run record template](../templates/run-record.md).

Resolve input and design issues before analyzing an actual research dataset. The [synthetic format example](../examples/synthetic-foci-MNI.txt) is suitable only for practicing file import and does not support statistical conclusions.

## Procedure

### 1. Set the Analysis Space and Output Location

In Preferences, record:

- The full names of Coordinate Space and the selected mask.
- Actual settings such as Additional FWHM. Do not add smoothing merely to reproduce a screenshot if it was not specified in the analysis plan.
- Output Directory, the output prefix, and the images, tables, and history files to retain.
- Any departures from the original study being reproduced or from default settings, together with their reasons.

### 2. Open the Foci File and Check How It Was Read

Load the input through `File → Open Foci`. Compare the recognized numbers of groups and foci and the standard space against the extraction records. Address messages about missing sample sizes, empty groups, duplicate groups, unreadable coordinates, and foci outside the mask individually.

If the counts do not match, return to the text file and extraction table. Continuing to Compute does not replace these checks. Do not delete out-of-mask foci simply to improve the appearance of a figure. First verify their values, coordinate space, original study coverage, and relationship to the selected mask.

### 3. Distinguish the Two Threshold Levels

| Setting | Question addressed | What it does not mean |
| --- | --- | --- |
| Cluster-forming threshold: voxel-level uncorrected p | Which voxels initially form candidate clusters? | It is not the final cluster-level corrected p value |
| Cluster-level FWE threshold: cluster-level corrected p | Which clusters survive whole-brain cluster-level error control? | It does not provide the same localization guarantee for every voxel within a surviving cluster |
| Number of permutations | How many random realizations are used to estimate the threshold? | More permutations do not resolve dependence in the input or selection bias |
| Final cluster extent threshold | What cluster-size criterion was obtained or applied in this analysis? | It does not mean that a fixed 200 mm³ cutoff should always be added manually |

Cluster-level family-wise error correction (cFWE) first forms candidate clusters using an uncorrected voxel-level threshold and then applies cluster-level correction. The [technical report](https://brainmap.org/pubs/Eickhoff_HBM_16.pdf) explains the relationship between candidate clusters and the maximum-cluster distribution.

### 4. Use Documented Starting Points and Record the Study Decisions

The following settings can serve as starting points for a conventional whole-brain, single-dataset ALE analysis. Determine the actual parameters before running the analysis.

| Item | Starting point | Explanation and basis |
| --- | --- | --- |
| Correction | Cluster-level FWE | A commonly used approach supported by methodological simulations; [M01](https://doi.org/10.1016/j.neuroimage.2016.04.072) |
| Cluster formation | Uncorrected p < 0.001 | A commonly used setting; [M02](https://brainmap.org/pubs/Eickhoff_HBM_16.pdf) |
| Cluster level | FWE-corrected p < 0.05 | A commonly used setting; report it separately from the cluster-forming threshold |
| Permutations | Consider 5,000 when planning a full analysis | A planning reference; determine the actual number in the research protocol |
| Mask / space | Match the input and document both fully | Do not switch spaces or analysis coverage without recording the change |
| Additional extent restriction | Do not assume a universal value | Distinguish the threshold obtained through cFWE from an additional user-defined restriction |

Why not simply use FDR, or an uncorrected p threshold with an arbitrary extent cutoff, for the primary analysis? The [simulations in M01](https://doi.org/10.1016/j.neuroimage.2016.04.072) support prioritizing FWE-based inference and describe limitations of other approaches. Voxel-level FWE is a separate inference method and is generally more conservative. It should not be treated as equivalent to cFWE.

The basis of permutation recommendations also requires care. [Mick Fox’s 2021 response](https://brainmap.org/forum/viewtopic.php?p=2149#p2149) warns that too few permutations may produce unstable thresholds and recommends at least 1,000. A [later simulation study](https://pmc.ncbi.nlm.nih.gov/articles/PMC9374884/) used larger numbers. A value of 5,000 can guide planning, but record the actual number and its justification. If the software provides a random-seed field, record it; otherwise, note that no such field was available.

### 5. Separate Tutorial Demonstrations from the Primary Analysis

[Andy’s Brain Book](https://andysbrainbook.readthedocs.io/en/latest/MetaAnalysis/MetaAnalysis_ShortCourse/MetaAnalysis_01_GingerALE.html) uses a small number of experiments and relatively few permutations to introduce the procedure. This can help check interface operations, but it does not demonstrate adequate power for an actual research question.

Forum response F05 also discusses trying several p thresholds to inspect cluster sizes. That is exploratory advice. Prespecify the primary analysis. If thresholds are changed after examining the results, explain why and label the revised analysis as exploratory.

### 6. Run the Analysis and Check Its Completion Status

After checking the parameter record, start the computation. Record the start and end times, messages, and actual outputs. Distinguish three outcomes:

1. The analysis completed successfully, and some clusters survived the prespecified thresholds.
2. The analysis completed successfully, but no clusters survived the prespecified thresholds.
3. The analysis produced warnings or errors, has missing outputs, or has not finished.

The second outcome is not a software failure. It also does not establish the absence of a true effect. If sensitivity analyses are needed, follow [Chapter 06](06-quality-and-reporting.md) and retain the primary analysis.

### 7. Identify Output Types Rather Than Inferring the Statistical Procedure from an Old Suffix

| Output type | Meaning | Subsequent use |
| --- | --- | --- |
| Unthresholded ALE map | Spatial convergence statistics | Retain for inspection; color alone does not establish significance |
| P or Z map | Another statistical representation; check whether it has been thresholded | The extension alone does not establish that correction has been applied |
| Final thresholded ALE map | The statistical image retained under the specified analysis procedure | Commonly used for visualization and as input to subsequent comparisons |
| Cluster-label map, such as a `clust` file | An identifier for each cluster | Cluster numbers are not ALE values; label the color scale accordingly |
| Cluster/peak tables and history files | Records of peaks, volumes, labels, parameters, contributions, and related information | Check them against the final image from the same run |

Do not assume that `*_ALE_pID05.nii` is a cFWE output. The official [command-line documentation](https://brainmap.org/ale/cli.html) lists `pID` as an FDR parameter. The [release notes](https://brainmap.org/ale/readme.html) also document changes in cluster-inference suffixes and `peaks.xls` filenames. **Identify results using the actual run history, complete parameters, and output type rather than applying the interpretation of an old example filename.**

## Outputs

For each traceable analysis run, retain the frozen input, complete parameters, all relevant outputs, logs or history files, and a list identifying the final images.

For A/B comparisons, proceed to [Chapter 04](04-conjunction-contrast.md). To display a single-dataset result, proceed directly to [Chapter 05](05-visualization.md).

## References

[Publications and official documentation](../references/README.md) · [BrainMap forum notes](07-forum-faq.md)
