## Task 1

1. Extract and store all FDA drugs via `Compounds` routes in [AnnotationDB](https://annotationdb.bhklab.ca/).
	- Extract **THE FIRST** mechanism entry and attach its information to the compound entry.
2. Extract all cell lines via `Cell Lines` routes in [AnnotationDB](https://annotationdb.bhklab.ca/) and the metadata for `accession`, `cell_line_name`, `age_at_sampling`, `sex_of_cell`.
3. Create an empty PharmacoSet (PSet) with [sample](https://bhklab.github.io/PharmacoGx/articles/CreatingPharmacoSet.html#sample) and [treatment](https://bhklab.github.io/PharmacoGx/articles/CreatingPharmacoSet.html#treatment) data frames using the data above and PharmacoGx.

Note: `PharmacoSet2()` will give you an error if `molecularProfiles` OR `treatmentResponse` is empty. Please use these placeholder slots upon PSet creation.

```R
placeholder_ids <- data.frame(treatmentid = "placeholder", sampleid = "placeholder")

one_row_response <- CoreGx::TreatmentResponseExperiment(
  rowData = placeholder_ids["treatmentid"], rowIDs = "treatmentid",
  colData = placeholder_ids["sampleid"],    colIDs = "sampleid",
  assays = list(raw = placeholder_ids),     assayIDs = list(raw = names(placeholder_ids))
)
empty_response <- one_row_response[0, 0]

placeholder_experiment <- SummarizedExperiment::SummarizedExperiment(
  colData = S4Vectors::DataFrame(sampleid = character(), batchid = character())
)
placeholder_profiles <- MultiAssayExperiment::MultiAssayExperiment(list(placeholder = placeholder_experiment))

pset <- PharmacoSet2(
  name = "AnnotationDB",
  sample = data.frame(),     # replace with your cell line table
  treatment = data.frame(),  # replace with your FDA compound table
  molecularProfiles = placeholder_profiles,
  treatmentResponse = empty_response,
  datasetType = "sensitivity"
)
```

Expected outputs: README.md, TSV or RDS of FDA compounds, TSV or RDS of cell lines, PharmacoSet.

Submit script(s), envs, and add your notes to the README within the `task_1` folder.

## YOUR COMMENTS AND EXPLANATIONS HERE