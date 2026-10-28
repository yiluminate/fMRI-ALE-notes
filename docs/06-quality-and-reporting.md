# 06 Quality Checks, Sensitivity Analysis, and Reporting

[Home](../README.md) · [Previous chapter](05-visualization.md) · [Developer forum notes](07-forum-faq.md)

Data checks should extend across the search, extraction, grouping, analysis, and reporting stages.

## Checks at Each Stage

| Stage | What to check | Evidence to retain |
| --- | --- | --- |
| Research question | Are the target population, task, baseline, direction, and primary comparisons clearly defined? | Research protocol |
| Search | Can the databases, complete search strategies, dates, supplementary searches, and exclusions be traced? | Screening records and flow counts |
| Extraction | Are the coordinates, minus signs, sample sizes, spaces, whole-brain sources, and source locations correct? | Extraction tables, reviewer details, and correction records |
| Grouping | Are related contrasts from the same sample, reuse across publications, and partial overlap documented? | Sample/group ID correspondence table |
| Coordinate space | Are there repeated transformations, incorrect labels, mixed spaces, or mismatched templates? | Original and transformed files, with transformation history |
| Analysis | Are the software, mask, thresholds, permutations, and output prefixes fully specified? | Run records, logs, and output lists |
| Comparison | Are A/B/pooled inputs recorded separately from contrast thresholds? | Three-input table and direction labels |
| Display | Do the color-scale type, template, left–right orientation, and statistical procedure correspond? | Figures, legends, and display records |
| Reporting | Do the conclusions remain within the scope of the inputs and inference? | Results text, limitations, and accessible supporting materials |

State the number of people responsible for extraction and verification, their roles, the scope of the checks, and how disagreements were resolved. [Müller et al.](https://doi.org/10.1016/j.neubiorev.2017.11.012) provide explicit guidance on data verification and reporting.

## Sensitivity Analysis: Define a Purpose for Each Analysis

Sensitivity analysis should address a reasonable methodological question rather than repeatedly adjusting parameters until the expected map appears. State what changes, what will be compared, and how stability will be described.

| Method | What it can assess | What it does not justify |
| --- | --- | --- |
| Leave-one-experiment/group-out analysis, LOEO | Whether one independent unit has a large influence on the result | Claiming that bias is absent because significance remains after every omission |
| Subgroup analyses by task or population | Whether heterogeneity corresponds to prespecified categories | Treating different subgroup significance outcomes as a significant between-subgroup difference |
| Reasonable alternatives to eligibility decisions | Whether a particular selection decision determines the main conclusion | Reporting only the most favorable result among several alternatives |
| Prespecified handling of disputed spaces or groupings | Whether conclusions depend on a disputed entry | Undocumented coordinate changes or sample merging |
| Threshold or permutation stability checks | How results vary under explicitly labeled alternative settings | Describing revised settings as the same prespecified primary analysis |

The [CBMAT author repository](https://github.com/Jordi-Manuello/CBMAT) provides tools for preparing LOEO and subset files. Its conventions for identifying or selecting experiments by publication do not replace an assessment of the actual participant samples.

If a final input group represents a shared sample whose contrasts have been combined, the unit omitted in LOEO should match the independent unit defined for the primary analysis. Removing only one contrast from that sample is not equivalent to leaving out an independent experiment. Retain separate parameters, outputs, and logs for every reanalysis.

## Discuss Publication Bias, Power, and Robustness Separately

Restricting an analysis to studies that report peak coordinates may introduce problems related to selective reporting and missing results. LOEO mainly assesses influence; it is not a test of publication bias. Likewise, the absence of significant ALE clusters does not establish that no effect exists.

Use the [simulation study of experiment counts](https://doi.org/10.1016/j.neuroimage.2016.04.072) when discussing power and the influence of a small number of experiments. If publication-bias methods or other statistical diagnostics are used, establish their suitability for ALE and report them separately. Applying the name of a method from conventional effect-size meta-analysis does not establish that a valid diagnostic has been performed.

## Minimum Reporting Content

- The research question, prespecified protocol, amendments, and reasons for changes.
- Search procedures, deduplication, full-text screening, exclusion reasons, and the included set.
- Numbers of publications, participant samples, original contrasts, final input groups, and foci, reported for each analysis.
- Whole-brain coverage, coordinate spaces, transformations, sample overlap, and Subjects rules.
- Analysis space, mask, correction method, both threshold levels, permutation count, and extent restrictions.
- How pooled, conjunction, and contrast results were generated and interpreted.
- Actual peak and cluster results, figures, display settings, analyses with no significant findings, and failed runs.
- Sensitivity analyses, limitations concerning power and bias, and the inputs and records that are available.

Use the [official PRISMA 2020 checklist](https://www.prisma-statement.org/prisma-2020-checklist) to check search and screening reporting. The [reporting outline](../templates/reporting-outline.md) can be used directly.

## Organizing Results

Store the original extractions, analysis inputs, and statistical outputs separately. Organize analyses by run ID and retain the relationships among parameters, figures, tables, logs, and interpretations. See [Organizing Analysis Results](../results/README.md) for output and display records.
