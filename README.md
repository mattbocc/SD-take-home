# SD-REF60787

This repo contains a multistep takehome test for candidates of the Data Engineer opening in the Benjamin Haibe-Kains lab. We expect candidates to spend **no more** than 10 hours on this take home assessment, therefore, it is understandable if you are unable to complete the given tasks. If you run out of time, document what's left and how you would approach it in your `task_1` and `task_2` README.

Code review will grade the quality of the work you complete and not how much. The team is looking to specifically grade submissions on code clarity and legibility, pipeline/script reproducibility, proper workflow orchestration, and general attention detail.

This repo must also be **FULLY** explainable. This means if you advance to the in person, you must be able to walk the interview team through your thought process for each step, explain design decisions, highlight challenges, and provide clarity on where LLMs were leveraged for work.

For each task the major work MUST be completed in R (you will notice the necessary functions needed are exclusive to R). It is recommended but not necessary to utilize R for API queries and annotation formatting as well.

Before starting, we would recommend briefly reviewing the following material regarding different types of R objects and packages:

- [SummarizedExperiment Overview](https://bhklab.github.io/handbook/software_development/Languages/R/SummarizedExperiment_Ranged/)
- [MultiAssayExperiment](https://waldronlab.io/MultiAssayExperiment/articles/QuickStartMultiAssay.html) (specifically make note of construction and various component slots, notably `colData` and `ExperimentList`)
- [CoreGx](https://bhklab.github.io/CoreGx/) is a the base package inherited and built on by PharmacoGx.
- [PharmacoGx](https://bhklab.github.io/PharmacoGx/articles/CreatingPharmacoSet.html) is a package that allows for the creation and exploration of PharmacoSets. A PharmacoSet is simply a class that is used to store biological data (genomic and drug response data) in an organized and consistent way.

## Background

A biology background is not required for these tasks, but getting a rough understanding of these terms would help:

| Term | Meaning |
|---|---|
| Cell line | A population of cells grown in the lab, often taken from a patient's tumour. Each cell line has a name, e.g. `U266`. |
| Cellosaurus accession | The standard global identifier for a cell line, e.g. `CVCL_0566`. Names vary between datasets but the accession doesn't. |
| Mechanism of action (MOA) | How a drug produces its effect. |
| Gene | A section of DNA that holds the instructions for making a protein or a functional RNA molecule. |
| Gene symbol | A short human-readable gene name, e.g. `TP53`. |
| Ensembl gene ID | A stable identifier for a gene, e.g. `ENSG00000141510` (the ID for `TP53`). |
| GENCODE | A reference catalogue of all human genes, with their Ensembl IDs, symbols and positions in the genome. |
| Variant | A position where a cell line's DNA differs from the human reference genome. |
| Mutation | Strictly, a variant that arose in the tumour rather than being inherited. In Task 2, 'mutation' is used loosely for every variant listed in `mutations.tsv`, as is common in cell line datasets, so some listed variants may be inherited rather than tumour-specific. |

## Tasks

The README files in the `task_1` and `task_2` folders describe each task's deliverables.
