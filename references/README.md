# Reference List

[Home](../README.md)

## Official Documentation

| ID | Resource | Content |
| --- | --- | --- |
| O01 | [GingerALE](https://brainmap.org/ale/) | Software, ALE documentation, and anatomical templates |
| O02 | [GingerALE User Manual](https://brainmap.org/ale/manual.pdf) | Foci format, single-dataset analysis, contrast analysis, and output types |
| O03 | [GingerALE Release Notes](https://brainmap.org/ale/readme.html) | Algorithm corrections, interface information, and output naming |
| O04 | [GingerALE Command-Line Documentation](https://brainmap.org/ale/cli.html) | Analysis steps and parameter definitions, including labels such as pID |
| O05 | [Official Foci Example](https://brainmap.org/ale/foci2.txt) | Reference, Subjects, three-column coordinates, and blank-line grouping |
| O06 | [icbm2tal](https://brainmap.org/icbm2tal/) | MNI/Talairach transformations and the Lancaster and Brett methods |
| O07 | [Mango User Guide](https://mangoviewer.com/usingmango.html) | Image display, coordinates, and left–right orientation |
| O08 | [Additional Mango Operations](https://mangoviewer.com/usingmango_add.html) | Update to Image Range and image information |
| O09 | [Mango Display Settings](https://mangoviewer.com/usingmango_display.html) | Color scales, views, and display ranges |
| O10 | [xjView](https://www.alivelearn.net/xjview/download/) | MATLAB/SPM dependencies and access |
| O11 | [BrainMap Workshop Materials](https://brainmap.org/workshop/materials.html) | Teaching materials for single-dataset analysis, contrast analysis, and Mango |

## Methodological Publications and Reporting Guidance

| ID | Resource | Topic |
| --- | --- | --- |
| M01 | Eickhoff SB et al. (2016). [Behavior, sensitivity, and power of activation likelihood estimation characterized by massive empirical simulation](https://pmc.ncbi.nlm.nih.gov/articles/PMC4981641/). NeuroImage, 137, 70–85. [DOI](https://doi.org/10.1016/j.neuroimage.2016.04.072) | Experiment counts, power, dominance by a few experiments, and thresholding strategies |
| M02 | Eickhoff SB et al. [Implementation Errors in the GingerALE Software: Description and Recommendations](https://brainmap.org/pubs/Eickhoff_HBM_16.pdf). [DOI](https://doi.org/10.1002/hbm.23342) | Implementation issues and recommendations concerning FDR and cluster-level correction |
| M03 | Müller VI et al. (2018). [Ten simple rules for neuroimaging meta-analysis](https://www.tnu.ethz.ch/fileadmin/user_upload/teaching/MuellerCieslik17-Ten_simple_rules.pdf). Neuroscience & Biobehavioral Reviews, 84, 151–161. [DOI](https://doi.org/10.1016/j.neubiorev.2017.11.012) | Question definition, coverage, multiple contrasts, verification, and reporting |
| M04 | Frahm L et al. (2022). [Evaluation of thresholding methods for activation likelihood estimation meta-analysis via large-scale simulations](https://pmc.ncbi.nlm.nih.gov/articles/PMC9374884/) | Simulation-based comparison of cFWE, vFWE, and TFCE |
| M05 | Page MJ et al. (2021). [The PRISMA 2020 statement](https://www.prisma-statement.org/prisma-2020-statement). BMJ, 372:n71. [DOI](https://doi.org/10.1136/bmj.n71) | Search, screening, and reporting; [official checklist](https://www.prisma-statement.org/prisma-2020-checklist) |
| M06 | Turkeltaub PE et al. (2012). [Minimizing within-experiment and within-group effects in activation likelihood estimation meta-analyses](https://doi.org/10.1002/hbm.21186) | Within-experiment and within-group effects, multiple peaks, and shared samples |

## BrainMap Forum

| ID | Topic and response | Respondent / date | Main issue |
| --- | --- | --- | --- |
| F01 | [Different N for different contrasts, p1975](https://brainmap.org/forum/viewtopic.php?p=1975#p1975) | Mick Fox / 2018-01-22 | Subjects values for between-group comparisons |
| F02 | [Study vs. experiment, thread t204](https://brainmap.org/forum/viewtopic.php?t=204); [2014 response p1286](https://brainmap.org/forum/viewtopic.php?p=1286#p1286), [p1291](https://brainmap.org/forum/viewtopic.php?p=1291#p1291), and [2019 response p2068](https://brainmap.org/forum/viewtopic.php?p=2068#p2068) | Mick Fox / 2014-02-11 and 2019-07-11 | Multiple contrasts from the same sample, independent grouping, and sample reuse across publications |
| F03 | [ANOVA results and combining tasks from different domains, p1486](https://brainmap.org/forum/viewtopic.php?p=1486#p1486) | SEickhoff, signed Simon / 2015-01-26 | Inclusion and interpretation of ANOVA results |
| F04 | [How to compute interaction effect?, p1017](https://brainmap.org/forum/viewtopic.php?p=1017#p1017) | SEickhoff, Simon / 2012-06-21 | Interaction testing at the meta-analytic level |
| F05 | [How to best choose threshold?, p2149](https://brainmap.org/forum/viewtopic.php?p=2149#p2149) | Mick Fox / 2021-03-03 | Cluster-forming thresholds, cluster-level FWE, and permutations |
| F06 | [Threshold for contrast analysis, p2160](https://brainmap.org/forum/viewtopic.php?p=2160#p2160) | Mick Fox / 2021-03-03 | Thresholded inputs for contrast analysis |
| F07 | [Subtraction in contrast analysis, p2159](https://brainmap.org/forum/viewtopic.php?p=2159#p2159) | Mick Fox / 2021-03-03 | Comparisons when one dataset has no significant results |
| F08 | [No FWE cluster threshold for contrast/conjunction analyses?, p1724](https://brainmap.org/forum/viewtopic.php?p=1724#p1724) | Mick Fox / 2016-06-02 | Conjunction algorithm and contrast inference options |
| F09 | [roi studies, p1998](https://brainmap.org/forum/viewtopic.php?p=1998#p1998) | Mick Fox / 2018-04-05 | Whole-brain ALE and ROI results |
| F10 | [controlling for different contrasts in multiple comparisons, p2150](https://brainmap.org/forum/viewtopic.php?p=2150#p2150) | Mick Fox / 2021-03-03 | Contrast redundancy, direction, and small datasets |
| F11 | [Does the difference between MNI (SPM) and MNI (FSL) matter?, p2136](https://brainmap.org/forum/viewtopic.php?p=2136#p2136) | Mick Fox / 2021-03-03 | Meaning of the SPM/FSL transformation options |

Browse by question in the [forum notes](../docs/07-forum-faq.md).

## Tutorials and Tools

| ID | Resource | Content |
| --- | --- | --- |
| T01 | [Andy’s Brain Book: Activation Likelihood Estimation with GingerALE](https://andysbrainbook.readthedocs.io/en/latest/MetaAnalysis/MetaAnalysis_ShortCourse/MetaAnalysis_01_GingerALE.html) | A teaching workflow covering input preparation, interface operations, and result viewing |
| T02 | [CBMAT](https://github.com/Jordi-Manuello/CBMAT) and its [methods paper](https://doi.org/10.3758/s13428-023-02185-3) | Data preparation, LOEO, subset analyses, and checks of dataset characteristics |
