# 01 Literature Screening and Coordinate Extraction

[Home](../README.md) · [Introduction and setup](00-overview-and-setup.md) · [Next chapter](02-coordinate-conversion.md)

## Purpose

Create coordinate extraction records that can be traced to the original publications, while distinguishing publications, samples, contrasts, and input groups.

## Inputs

- The research question, target population, task, contrast direction, and eligibility criteria.
- Search records, full texts, supplementary materials, and whole-brain peak coordinate tables.
- Information on the sample sizes actually included in the original analyses, coordinate spaces, and analysis coverage.
- Information needed to identify shared cohorts, duplicate publications, and partially overlapping samples.

Use the [research protocol template](../templates/research-protocol.md) and the [extraction and grouping template](../templates/extraction-and-grouping.md) to begin recording these details.

## Procedure

### 1. Define the Question Before Examining the Analysis Results

State the research question in a form that makes it possible to decide whether a contrast is eligible. Examples include spatial convergence of task-related activation relative to baseline in adults, or abnormally increased responses in a patient group relative to healthy controls. Specify:

- The population, age range, task, and baseline.
- Whether the direction is `A > B`, `B > A`, or a prespecified difference in either direction.
- The primary analysis, secondary analyses by task or population, and intended comparisons.
- Whether PET, resting-state, structural imaging, or other study types are eligible. If they are, explain how they address the same question.

These decisions belong in the research protocol. Do not revise them simply because few coordinates are available or the results are not significant. See [Müller et al.](https://doi.org/10.1016/j.neubiorev.2017.11.012) for guidance on research questions, paradigms, and the scope of study selection.

### 2. Maintain a Search and Screening Record

Record the databases, complete search strategies, search dates, date limits, number of reviewers, deduplication procedures, and reasons for exclusion. Document supplementary methods, such as citation tracking, alongside database searches. Studies found through these methods should not be treated as undocumented additions. Use [PRISMA 2020](https://www.prisma-statement.org/prisma-2020-statement) to check the reporting of the search and screening process.

For conventional whole-brain ALE, extract coordinates identified through whole-brain searches. Do not combine them with peaks identified only through region-of-interest (ROI) analyses or small-volume correction (SVC). If a publication reports both whole-brain and ROI results, extract the eligible whole-brain results and record the source of each row. The presence of the term ROI does not by itself justify excluding the entire publication. See the [developer’s explanation of ROI studies](https://brainmap.org/forum/viewtopic.php?p=1998#p1998).

Studies that address the topic but provide no usable coordinates should remain in the screening record. State the actual reason, such as “no extractable coordinates.” Do not invent coordinates or interpret the absence of significant peaks as evidence that the analysis was not performed.

### 3. Interpret the Recommendation of 17–20 Experiments Correctly

This recommendation concerns the number of experimental units included in the meta-analysis. It does not refer to the number of participants recruited in each original study or the number of reported foci. Report the numbers of publications, independent participant samples, original contrasts, final foci groups, and coordinates separately.

Simulation research recommends aiming for approximately 20 or more experiments to reduce the risk that individual experiments dominate the results and to improve statistical power. The frequently cited range of 17–20 is an approximate recommendation. The required number still depends on factors such as effect size. It is not a software requirement that determines whether an analysis can run. Report the number of units in each subgroup separately rather than substituting the total from the primary analysis. See [Eickhoff et al., 2016](https://doi.org/10.1016/j.neuroimage.2016.04.072).

If fewer experiments are available, describe the findings as preliminary or exploratory and explain the limitations. Do not count multiple contrasts from the same sample as additional independent experiments. [Mick Fox’s response concerning small datasets](https://brainmap.org/forum/viewtopic.php?p=2150#p2150) also emphasizes the need to justify decisions about redundancy, dataset size, and homogeneity.

### 4. Select ANOVA Results According to the Research Question

First establish what the result actually tests: a main effect, an interaction, a directional post hoc comparison, or a nondirectional omnibus F test. If the research question is directional, an F-test peak alone does not establish the direction. Check the original contrast or the accompanying explanation.

[Simon Eickhoff’s 2015 response](https://brainmap.org/forum/viewtopic.php?p=1486#p1486) states that ANOVA results can generally be included. Their interpretation depends on the research question, and interaction effects require particular care. Assess eligibility according to the effect being tested and the target question.

Also distinguish coordinate extraction from an original ANOVA from interaction testing at the meta-analytic level. The [2012 discussion](https://brainmap.org/forum/viewtopic.php?p=1017#p1017) primarily concerns the latter. It does not establish that coordinates from ANOVA results are categorically ineligible.

### 5. Group Related Contrasts According to Sample Independence

Assign a paper ID to each publication, a sample ID to each participant sample, and a contrast ID to each original contrast. Also record the final ALE group ID to which each contrast contributes.

| Situation | Handling principle |
| --- | --- |
| Completely different samples analyzed separately within one publication | They may form independent groups. Retain the evidence supporting the separate sample IDs |
| Multiple eligible, related contrasts from the same sample entering one analysis | Prespecify one contrast or combine the related coordinates into one group. Explain the decision and do not repeatedly add the same participants |
| The same sample reused across publications | Address the dependence. Different authorship or publication years do not establish independence |
| Partial overlap, different scanning subsets, or different effective sample sizes | Document the overlap and develop a case-specific plan. Deleting blank lines or assigning a single sample size does not resolve the issue |
| Contrasts in opposite directions | Organize them separately for directional analyses. Combining them may be considered for a question about differences in either direction, but the interpretation must remain consistent with that question |

See the [2014 and 2019 follow-up responses in F02](https://brainmap.org/forum/viewtopic.php?t=204) for the basis of these grouping principles. Sleuth’s automatic grouping can assist with organization, but the developer notes that it does not identify all instances of sample reuse across publications.

**Contrasts in both directions:** The original question in [F10](https://brainmap.org/forum/viewtopic.php?p=2150#p2150) includes both drug > placebo and the reverse contrast. The recommendation to combine contrasts or select one addresses redundancy arising from shared samples. First establish whether the research question is directional, then handle sample dependence within each analysis. Do not include reverse-direction peaks in an `A > B` analysis.

### 6. Determine the Subjects Value and Record Its Basis

- For a task contrast within one participant sample, use the number of participants actually included in that contrast, rather than the number initially recruited.
- For an original between-group contrast with unequal group sizes, [Mick Fox’s response](https://brainmap.org/forum/viewtopic.php?p=1975#p1975) recommends the smaller group size as a conservative representation of spatial uncertainty. Retain both original group sizes and document this convention. Do not replace it with their sum.
- Repeated-measures designs, partially overlapping samples, varying sample sizes across contrasts, and other complex designs require a separate justification. The recommendation for two groups is not a universal formula.
- If the sample size cannot be confirmed, flag it for clarification. A default value accepted by the software is not evidence of the actual sample size.

Subjects contributes to the modeling of spatial uncertainty. It is therefore an essential extraction field rather than an optional comment.

### 7. Prepare a Plain-Text Foci File

See the [official example](https://brainmap.org/ale/foci2.txt) for the foci file format:

1. Begin with `// Reference=MNI` or the declaration for the actual target space.
2. Identify each group using a `//` comment. Before its coordinates, include `// Subjects=N`, where N is the assigned sample size.
3. Place one focus on each line, with only three numeric columns: x, y, and z, in millimeters.
4. Separate input groups with a blank line. Do not insert blank lines between peaks within the same group.
5. Separate coordinate columns with spaces or tabs. Consistent tab separation is recommended.
6. Save the file as UTF-8 plain text with a `.txt` extension. Avoid rich text and check whether copying has altered minus signs, full-width characters, or numbers.

The [synthetic example](../examples/synthetic-foci-MNI.txt) contains **three groups and eight foci**. Its first group represents two related contrasts from the same sample combined into one group, with Subjects recorded once. It is intended for practicing import and counting, rather than as a dataset with adequate power for meta-analysis.

### 8. Verify Each Entry and Freeze the Input

Check every focus against the page, table, and row in the original publication. Verify minus signs, column order, decimal values, coordinate space, analysis coverage, and sample size. Confirm that duplicate peaks, repeated contrasts, or shared samples have not been treated as independent units. Record the reviewer, date, and reasons for corrections. Detailed fields are provided in the [extraction template](../templates/extraction-and-grouping.md).

## Outputs

The completed records should include the search and screening history, a coordinate table with source locations, sample-overlap and grouping decisions, original foci files stored separately by coordinate space, and a summary of the relevant counts.

Proceed to [Coordinate Space Harmonization](02-coordinate-conversion.md).

## References

[Publications and official documentation](../references/README.md) · [BrainMap forum notes](07-forum-faq.md)
