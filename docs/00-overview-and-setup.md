# 00 Introduction, Terminology, and Software Setup

[Home](../README.md) · [Start coordinate extraction](01-foci-extraction.md)

## Define the Question ALE Will Address

Activation likelihood estimation (ALE) assesses whether peak coordinates reported across experiments show greater spatial convergence than expected by chance. It does not directly average the t statistics, activation magnitudes, or Cohen’s d values reported in individual papers. An ALE map does not represent the probability of a psychological function occurring.

Conventional whole-brain ALE uses peak coordinates as input. The contrasts in the original studies must match the research question. For example, task > baseline and patients > controls cannot be treated as the same type of effect without justification. See the [official GingerALE documentation](https://brainmap.org/ale/) for background and [Müller et al.](https://doi.org/10.1016/j.neubiorev.2017.11.012) for guidance on defining the research question.

## Key Terms

| Term | Meaning | Common source of confusion |
| --- | --- | --- |
| Paper / publication | An article or report | One publication may include multiple samples |
| Sample / subject group | A group of participants | Two publications may use the same participants |
| Contrast | A comparison between conditions or groups in an original study | Multiple contrasts do not necessarily represent independent samples |
| Experiment / foci group | A group of coordinates entered into the software; the grouping rule must be stated | Report the final number of independent groups. Counting text blocks alone does not establish independence |
| Focus; plural: foci | A peak coordinate in standard space | One focus is not one experiment |
| Subjects | The sample size assigned to an input group | This differs from the number of experiments included in the meta-analysis |
| MA map | A modeled activation map constructed from one input group | Combining peaks within an experiment differs from combining information across experiments |
| ALE map | A map of spatial convergence across input groups | Raw ALE values are neither significance levels nor effect sizes |
| Mask | The spatial extent of the analysis | It is not the anatomical underlay used in a figure |
| Underlay / overlay | The background image / superimposed image used for display | Displaying an overlay does not perform a statistical test |
| Pooled | A dataset created by combining inputs and analyzing them again | It is not a conjunction |
| Conjunction | A representation of regions shared by two sets of results | It is not obtained simply by combining coordinates and rerunning ALE |
| Contrast analysis | A directional comparison between meta-analytic results | It differs from a task contrast in an original study |

For the basis of the grouping rules, see [forum thread F02](https://brainmap.org/forum/viewtopic.php?t=204). Practical procedures are described in Chapters 01 and 04.

## Software Setup

1. Obtain GingerALE from the [official BrainMap website](https://brainmap.org/ale/).
2. If using the JAR distribution, prepare the required Java runtime environment.
3. Prepare [Mango](https://mangoviewer.com/usingmango.html).
4. Obtain an anatomical template that matches the selected analysis space. Record its filename, source, and resolution.
5. If using xjView, prepare MATLAB and SPM according to the [official dependency information](https://www.alivelearn.net/xjview/download/). This is optional and is not required to run GingerALE.
6. Store the original extractions, transformed input files, and analysis outputs separately.

## Reading Tutorials Critically

When reading another author’s notes, consider three questions:

1. Is the example demonstrating that the software can load a file, or does it provide a statistical plan for an actual study?
2. Are the parameters intended to reproduce an earlier publication, or are they recommendations for a new study?
3. Are the input space, display template, filename suffixes, and reported parameters consistent?

For example, [Andy’s Brain Book](https://andysbrainbook.readthedocs.io/en/latest/MetaAnalysis/MetaAnalysis_ShortCourse/MetaAnalysis_01_GingerALE.html) provides a clear sequence of interface operations. A demonstration with a small dataset, however, does not establish adequate statistical power. The inputs and parameters still require individual checks before an actual analysis.

## Records Required at Each Stage

| Stage | Minimum required record | Starting point |
| --- | --- | --- |
| Question definition | Population, task, effect direction, primary and secondary analyses, and reasons for eligibility criteria | [Protocol template](../templates/research-protocol.md) |
| Search and screening | Complete search strategies, dates, deduplication procedures, and exclusion records | [Chapter 01](01-foci-extraction.md) |
| Extraction and grouping | Coordinate sources, sample sizes, standard spaces, and handling of shared samples | [Extraction template](../templates/extraction-and-grouping.md) |
| Space harmonization | Original space, target space, transformation method, and correspondence between original and transformed data | [Chapter 02](02-coordinate-conversion.md) |
| Analysis | Complete parameters, inputs, outputs, and logs | [Chapter 03](03-ale-analysis.md), [Chapter 04](04-conjunction-contrast.md) |
| Display | Underlay, final statistical image, color scale, left–right convention, and figure legend | [Chapter 05](05-visualization.md) |
| Verification and reporting | Records of independent or repeated checks, sensitivity analyses, limitations, and traceable materials | [Chapter 06](06-quality-and-reporting.md) |
