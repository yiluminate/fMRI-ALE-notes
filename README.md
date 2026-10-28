# fMRI ALE Meta-analysis Notes

MYL

## Analysis Workflow

Research question and protocol → Literature search and screening → Coordinate extraction and sample grouping → Coordinate space harmonization → Single-dataset ALE → Conjunction or contrast analysis → Visualization → Quality checks and reporting.

To compare datasets A and B: run separate ALE analyses for A and B → Merge the coordinates into a pooled dataset → Run an ALE analysis on the pooled dataset → Load the corresponding images for comparison.

Pooled ALE, conjunction analysis, and contrast analysis are separate procedures. Their differences are explained in [Conjunction and Contrast Analyses](docs/04-conjunction-contrast.md).

## Contents

| Chapter | Content |
| --- | --- |
| [00 Introduction, Terminology, and Software Setup](docs/00-overview-and-setup.md) | Research questions addressed by ALE, key terms, and software setup |
| [01 Literature Screening and Coordinate Extraction](docs/01-foci-extraction.md) | Eligibility criteria, effect direction, ANOVA, Subjects, shared samples, and foci file format |
| [02 Coordinate Space Harmonization](docs/02-coordinate-conversion.md) | MNI and Talairach spaces, transformation methods, transformation history, and checks |
| [03 Single-Dataset ALE Analysis](docs/03-ale-analysis.md) | Cluster-level FWE correction, cluster-forming thresholds, permutations, and output files |
| [04 Conjunction and Contrast Analyses](docs/04-conjunction-contrast.md) | A, B, and pooled datasets; shared regions; directional differences; and limits of inference |
| [05 Visualization and Result Interpretation](docs/05-visualization.md) | Mango, anatomical templates, color scales, anatomical labels, and xjView |
| [06 Quality Checks, Sensitivity Analysis, and Reporting](docs/06-quality-and-reporting.md) | Data verification, LOEO analysis, statistical power, bias, and reporting |
| [07 BrainMap Forum Questions and Answers](docs/07-forum-faq.md) | Common methodological questions and developer responses |

For an introduction, read Chapters 00–06 in order. Use the [forum notes](docs/07-forum-faq.md) to look up specific questions.

## Working Forms

| Form | Purpose |
| --- | --- |
| [Research protocol](templates/research-protocol.md) | Define the population, task, effect direction, eligibility criteria, and analysis plan |
| [Extraction, grouping, and coordinate space records](templates/extraction-and-grouping.md) | Extract individual peaks, handle shared samples, document coordinate transformations, and verify the data |
| [Analysis run record](templates/run-record.md) | Document inputs, parameters, A/B/pooled relationships, outputs, and display settings |
| [Methods, results, and figure legend outline](templates/reporting-outline.md) | Organize the methods, statistical results, figure legends, and limitations |

## Examples and Exercises

- [Foci file example](examples/README.md): a synthetic file containing three groups and eight foci for practicing file formatting and grouping.
- [Result interpretation exercises](examples/interpretation-practice.md): display settings versus statistical thresholds, sample independence, effect direction, and tests of differences.
- [Organizing analysis results](results/README.md): links among analysis outputs, figures, tables, and parameters.

## References

- [Publications, official documentation, and the BrainMap forum](references/README.md)
- [PDF notes](docs/original-note.pdf)
