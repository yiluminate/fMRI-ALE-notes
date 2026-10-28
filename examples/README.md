# Examples and Exercises

[Home](../README.md) · [Coordinate extraction](../docs/01-foci-extraction.md)

## Synthetic Foci File

[synthetic-foci-MNI.txt](synthetic-foci-MNI.txt) is a plain-text formatting exercise. Its group names, sample sizes, and coordinates are all synthetic.

The file contains **an MNI declaration, three input groups, eight rows of peak coordinates, and tab-separated columns**.

| Input group | Synthetic example represented | Subjects | Number of foci |
| --- | --- | --- | --- |
| SYNTHETIC_S01 | Two related contrasts from exactly the same sample, combined into one group; the sample size is recorded once | 20 | 4 |
| SYNTHETIC_S02 | An independent synthetic sample distinct from the first group | 24 | 2 |
| SYNTHETIC_S03 | A third independent synthetic sample | 18 | 2 |

After opening the file in GingerALE, check that the recognized numbers of groups and foci match these values.

This example is intended for practicing formatting and grouping. See [Chapter 01](../docs/01-foci-extraction.md) for experiment-count and power considerations in actual research.

## Result Interpretation Exercises

The [interpretation exercises](interpretation-practice.md) provide eight scenarios and answers. They distinguish display operations from statistical tests, unthresholded from final images, shared samples from independent experiments, and significance within one dataset from a difference between datasets.

## Adding an Empirical Example

At minimum, retain the data source, research question, extraction table, sample-grouping and overlap records, coordinate transformations, frozen inputs, analysis parameters, run logs, and corresponding results. Use the [working templates](../templates/README.md) to record these details.

If using an official workshop example or another author’s dataset, cite the original source and explain the dataset’s purpose. See [reference O11](../references/README.md) for the official resources.
