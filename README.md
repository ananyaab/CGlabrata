---
title: analyze time course gene expression data in _C. glabrata_ under phosphate starvation
author: Ananya Albrecht-Buehler, Amanda Caraballo, Bin He
---

# Goal
Identify temporal order of transcriptional response to phosphate starvation in the human commmensal and opportunistic pathogen _C. glabrata_

# Data
The transcriptome profiling experiment was performed in 2017. For the present analysis, we will only consider the non _pho80∆_ samples. There are two genotypes: wild type (wt) and _pho4∆_. They should be analyzed separately to identify transcriptional responses that either depend on the transcription factor Pho4 or not.

There are two data files in the `data` folder (see README.md therein). They can be directly read into R using the `tidyr::read_tsv()` function, which will automatically decompress the zip files.

Here are some sample code

```r
# assuming the R markdown is in the present (project root) folder.
library(tidyverse)
normalized <- read_tsv("data/Ex009_normalized_log2_read_counts.zip")
sampleinfo <- read_csv("data/Ex009_experiment_set_up_20171019.csv")
# to turn the data into a matrix
matrix.data <- as.matrix(normalized[,-1])
rownames(matrix.data) <- normalized$gene
```

# Resource
- <http://www.opiniomics.org/you-probably-dont-understand-heatmaps/>
- Bin's take on gene expression clustering (a rendering of the `analysis/c_glabrata_timecourse_analysis_HB_20200801.nb.html`): <https://rpubs.com/emptyhb/645504>
