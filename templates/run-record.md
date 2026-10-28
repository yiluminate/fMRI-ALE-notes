# Analysis Run Record

[Templates](README.md) · [Single-dataset analysis](../docs/03-ale-analysis.md) · [Contrast analysis](../docs/04-conjunction-contrast.md)

## Basic Information

- Run ID, date, and analyst: to be completed.
- Analysis type: single dataset / pooled / conjunction / contrast / sensitivity analysis; select as appropriate.
- Primary protocol, replication, or exploratory analysis: to be completed.
- Research protocol: to be completed.
- Relevant software documentation or methodological basis: to be completed.

## Inputs and Checks

| Item | Actual record |
| --- | --- |
| Frozen input file, source, and checksum information, if available | To be completed |
| Reference, analysis space, and mask | To be completed |
| Numbers of publications, independent samples, contrasts, foci groups, and foci | To be completed |
| Agreement between expected and software-recognized group and focus counts | To be completed |
| Sample overlap and basis of the final Subjects values | To be completed |
| Formatting, duplicate-group, and out-of-mask coordinate messages | To be completed, including how they were handled |
| Location of coordinate transformation records | To be completed or not applicable |

## Actual Parameters for Single-Dataset or Pooled Analysis

| Field | Actual value | Rationale or protocol location |
| --- | --- | --- |
| Full name of the correction method | To be completed | To be completed |
| Cluster-forming threshold and whether it is uncorrected | To be completed | To be completed |
| Cluster-level FWE threshold | To be completed or not applicable | To be completed |
| Number of permutations | To be completed | To be completed |
| Availability and recording of a random seed | To be completed | State if no seed option is available |
| Final cluster extent threshold and its source | To be completed | Specify whether calculated by the software or additionally imposed, with units |
| Additional FWHM and other settings | To be completed | To be completed |
| Output path and prefix | To be completed | To be completed |

See Chapter 03 for common starting points. This table records the values actually used, rather than values inferred from screenshots.

## Contrast-Specific Record

| Field | Actual input image | Corresponding source coordinates/run ID | Space, mask, and thresholds |
| --- | --- | --- | --- |
| A | To be completed | To be completed | To be completed |
| B | To be completed | To be completed | To be completed |
| Pooled | To be completed | To be completed | To be completed |

- Pooled merging and handling of duplicates/overlap: to be completed.
- A/B comparison question and direction: to be completed.
- The contrast’s own threshold, correction capability, permutation count, and extent restriction: to be completed. Do not copy the single-dataset cFWE label.
- Conjunction algorithm and input conditions: to be completed.
- Comparison method and handling when one dataset has no significant clusters: to be completed or not applicable.

## Completion Status and Output Inventory

- Start and end times: to be completed.
- Status: not started / incomplete / error / completed with no surviving clusters / completed with surviving clusters; select as appropriate.
- All warnings and their resolution: to be completed, or explicitly state “none.”

| Actual filename | Content type/comparison direction | Thresholding status and statistical procedure | Subsequent analysis step |
| --- | --- | --- | --- |
| To be completed | To be completed | To be completed | To be completed |

- Logs or Data History: to be completed.
- Basis for identifying the final image: to be completed.
- Departures from the primary protocol, timing of changes, and whether results had already been examined: to be completed or none.

## Display Record

| Item | Actual setting |
| --- | --- |
| Image viewer | To be completed |
| Underlay file, space, resolution, and source | To be completed |
| Overlay file, image type, and direction | To be completed |
| Left–right convention, slice coordinates, and views | To be completed |
| Color map, range, opacity, and interpolation | To be completed |
| Atlas and anatomical-label sources | To be completed |
| Exported files, date, and figure-legend location | To be completed |

## Results and Limitations

Result summary, relationship to the prespecified plan, limitations, reviewer, and date: to be completed.
