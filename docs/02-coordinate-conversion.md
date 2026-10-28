# 02 Coordinate Space Harmonization

[Home](../README.md) · [Previous chapter](01-foci-extraction.md) · [Next chapter](03-ale-analysis.md)

## Purpose

Harmonize coordinates to the selected target space while retaining the original values and transformation history. Changing a space label, replacing a display underlay, and transforming coordinates are different operations.

## Inputs

- Original coordinates, publication sources, and sample/group IDs.
- Information from the original publications about coordinate space, templates, normalization software, and previous coordinate transformations.
- The selected target space and transformation method.
- Extraction and grouping records; the [coordinate space record template](../templates/extraction-and-grouping.md) may be used.

## Procedure

### 1. Establish the Original Space Rather Than Inferring It from Coordinate Values

Check the methods, table notes, and supplementary materials first. Distinguish the software used for analysis from the space in which coordinates were reported. If descriptions conflict, flag the entry for clarification and retain the evidence. The use of SPM alone does not justify relabeling a coordinate table as MNI.

In particular, establish whether the original authors or a database have already transformed the coordinates, whether MNI coordinates were loosely described as Talairach, and whether an extraction file contains more than one space. For database exports, retain the Reference declaration and processing information to avoid transforming the coordinates twice.

### 2. Select the Target Space in Advance

Choose a space appropriate to the research question and data sources, and record the reason. The space used by the majority of the available coordinates may be a practical consideration, but it does not replace a methodological decision.

Check the correspondence among the space reported in the publication, the Reference declaration in the foci file, the GingerALE analysis space, and the subsequent display template. When selecting an option such as MNI152, record its full name. Distinguish the specific MNI templates and masks involved.

### 3. Understand the Background and Limits of the Transformation Method

The [BrainMap icbm2tal documentation](https://brainmap.org/icbm2tal/) describes the Lancaster method, the SPM, FSL, and Other options, and their differences from the earlier Brett method. It also notes limited evidence for some software–template combinations.

| Data situation | Approach |
| --- | --- |
| Coordinates are already in the selected target space | Retain them and document why no transformation is needed |
| Coordinates require transformation between MNI and Talairach spaces | Match the original normalization procedure to the available software options. Record the full method name and transformation direction |
| The original authors previously applied the Brett transformation | Establish the earlier transformation history. Do not simply treat the resulting coordinates as native Talairach coordinates |
| Only the use of SPM or FSL is known, while the space or template is unclear | Seek further information. The software name alone does not establish the complete transformation history |
| Some coordinates have already been transformed and others have not | Process them separately and document the distinction to avoid transforming the entire file again |

Regarding whether FSL-reported MNI coordinates require another transformation into “SPM MNI,” [Mick Fox’s 2021 response](https://brainmap.org/forum/viewtopic.php?p=2136#p2136) explains that these options arose from the transformation-fitting procedure. It does not recommend imposing another such transformation on coordinates already in MNI space. Nor does it imply that differences among templates or nonlinear registration procedures from all periods can be ignored.

### 4. Transform Coordinates in GingerALE

Follow the [official instructions](https://brainmap.org/icbm2tal/):

1. Start GingerALE.
2. Open `Tools → Convert Foci`.
3. Select the batch of source coordinates requiring transformation.
4. Select the correct direction and method. Record the full option name shown in the menu.
5. Change `Output File` so that the output does not overwrite the original.
6. Run the transformation, retain any messages, and save the output in a traceable location.

Possible filenames include `dataset-A_original-Talairach.txt` and `dataset-A_target-MNI.txt`. The space indicated in the filename should match the coordinate values.

### 5. Confirm That the Transformation Has Preserved Grouping

Compare the numbers of groups and foci, Subjects values, and corresponding IDs before and after transformation. Check coordinate changes entry by entry or through a documented sample of entries. Record parsing failures or changes in counts. A coordinate transformation should not silently alter eligibility or grouping decisions.

Before updating the space declaration in the final text file, confirm that the coordinates actually belong to that space. Changing `Reference` alone does not transform coordinates. A display transformation in Mango also does not replace the documented preparation of the analysis input.

### 6. Record the Complete Transformation History

A complete record can follow this sequence:

> Publication/sample/contrast ID → Reported space and page number → Previous transformations, if any → Input file → Transformation option → Target space → Output file → Group and focus counts before and after transformation → Reviewer and date.

Coordinate transformation provides an approximate mapping of locations. It does not register the original study’s brain images again.

## Outputs

- A retained copy of the original coordinates.
- A foci file organized in the target space.
- Records of the transformation method, direction, and count checks.
- A list of entries with unresolved coordinate spaces or disputed transformations.

Once the analysis input has been established, proceed to [Single-Dataset ALE Analysis](03-ale-analysis.md).

## References

[Publications and official documentation](../references/README.md) · [BrainMap forum notes](07-forum-faq.md)
