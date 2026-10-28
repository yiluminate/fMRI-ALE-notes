# Result Interpretation Exercises

[Home](../README.md) · [Examples](README.md)

Answer each question before checking the explanation and related chapter.

## 1. More Colors Appear After Changing the Display Range

Question: Does applying Update to Image Range in Mango perform a new FWE correction?

Answer: No. It changes the display range. Statistical inference still comes from the corresponding analysis. See [Chapter 05](../docs/05-visualization.md).

## 2. The Software Recognizes Many Groups

Question: Three related contrasts from the same participants are entered as three text blocks, and the software reports three groups. Does this mean there are three independent experiments?

Answer: No. Successful parsing does not establish independence. Revisit the participant sources and grouping plan. See [Chapter 01](../docs/01-foci-extraction.md).

## 3. The Two Groups Contain 25 and 40 Participants

Question: For the original between-group comparison, can `Subjects=65` be entered without explanation?

Answer: No. Record both actual group sizes. For this type of comparison, the developer recommends the smaller group size and explains its conservative interpretation. Complex designs require separate consideration. See [Chapter 01](../docs/01-foci-extraction.md).

## 4. A Has Significant Clusters, but B Does Not

Question: Can the result be described as A being significantly greater than B?

Answer: The two significance outcomes alone do not establish a difference. An appropriate, valid comparison and supporting implementation are required. See [Chapter 04](../docs/04-conjunction-contrast.md).

## 5. An Earlier File Has a pID Suffix

Question: If a filename contains `pID05`, can it be treated as the final cFWE map because the accompanying notes mention cFWE?

Answer: No. The official historical parameters identify `pID` with FDR. Check the parameters and output records for that run. See [Chapter 03](../docs/03-ale-analysis.md).

## 6. Two Coordinate Files Are Combined and Analyzed Again

Question: Is the resulting output a conjunction?

Answer: This is a pooled analysis of the combined inputs. A conjunction is a different result representing shared regions. The terms are not interchangeable. See [Chapter 04](../docs/04-conjunction-contrast.md).

## 7. A Publication Reports Both Whole-Brain and ROI Tables

Question: Can both tables be entered into conventional whole-brain ALE simply to include more peaks?

Answer: Search coverage must be considered. Identify eligible whole-brain coordinates according to the protocol. Assess and document ROI/SVC peaks separately. See [Chapter 01](../docs/01-foci-extraction.md).

## 8. A Nondirectional F-Test Peak Falls in the Expected Region

Question: Can it be labeled patients > controls?

Answer: Neither its location nor its F value establishes direction. Check the actual comparison, post hoc results, and research question. Do not categorically exclude it solely because it came from an ANOVA. See [Chapter 01](../docs/01-foci-extraction.md).
