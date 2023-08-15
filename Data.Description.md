
# **Hackathon 2023: Identification of doublets in single cell sequencing data**

-   **Overview**
- Single cell RNA sequencing (scRNA-seq) is a recently developed technology platform used to measure gene expression from thousands of individual cells. scRNA-seq is transforming biology and medicine as it enables studies of cell-heterogeneity, identification of cell types and subpopulations in complex tissues and measuring cell transformations during development. However, scRNA-seq also has a number of analysis challenges commonly encountered in data science. One of the main challenges is that the read count matrix (genes x cells) is sparse in that it contains many zeros due to technological limitations (e.g. only a thousands genes have count data from an individual cell even though many more genes are expressed in that cell).

- A typical goal in an scRNA-seq experiment is to obtain a gene expression profile of each cell type in mixed tissue sample. For example, samples from different tumors can be better compared. Typically, there are 5-15 common cell types (e.g. B lymphocytes, natural killer cells, monocytes in blood), and cell types differ in their expression profiles, i.e. which genes are expressed and their expression levels. Gene expression is measured by the amount of messenger RNA that is produced and reflects the amount of protein made for each gene. Gene expression can thus be measured by sequencing RNA extracted from a cell and counting the number of sequencing reads for each gene. In scRNA-seq, one obtains read counts for each cell and often over 10k cells per experiment. A common aim in analysis of scRNA-seq data is to group or cluster the cell into types (using clustering methods or known marker genes), then obtain an expression profile for all cells of a given type. Finally, different biological or medical samples can be compared to one another. For an overview of how scRNA-seq data is obtained and best practices for scRNA-seq analysis see Huemos et al. (2023, [PMC10066026](https://www.nature.com/articles/s41576-023-00586-w)).

- The goal of this hackathon is to identify doublets in scRNA-seq data. Doublets or multiplets are cases where gene expression count data is generated from two or more cells rather than a single cell. This occurs when a unique molecular identifier (UMI) is associated with two cells in a liquid droplet rather than one, resulting in a mixture of expression from both cells. There are a variety of ways in which doublets can be detected, most often by cells that appear to show a mixture of expression patterns from two different cell types. Doublets involving the same cell type are much more difficult to detect. Ones ability to detect doublets depends on how one deals with sparse data, normalization and cell type clustering. For a review of methods see Xi and Li (2021, [PMC7897250](https://doi.org/10.1016/j.cels.2020.11.008)). Accurate detection of doublets remains a significant challenge and no single method outperforms all others.

\****Data***
- The data for this hackathon comes from a single cell sequencing experiment where doublets were independently identified experimentally. The data are available as a sparse matrix in two easy to load formats: an R rds file containing a SingleCellExperiment Class object and an AnnData object in h5ad format for Python. These sparse matrices are much smaller (23Mb) than the full uncompressed matrix (3.9Gb), making them faster to load and analyze. The two files (containing the same data) are: sce.rds and sce.h5ad.

- Information on the SingleCellExperiment class is available [here.](https://bioconductor.org/packages/release/bioc/vignettes/SingleCellExperiment/inst/doc/intro.html)
- An R package that handles this class and can be used to convert to other commonly used R packages is available [here:](https://bioconductor.org/packages/release/bioc/html/SingleCellExperiment.html)

- Information on AnnData objects that are part of the Scanpy Python package can be found [here.](https://scanpy.readthedocs.io/en/stable/api.html#reading)
-And information on installing Scanpy is [here.](https://scanpy.readthedocs.io/en/stable/installation.html)

- For both files, UMIs (single cells) are indicated by 16 bp DNA barcodes and genes by their names. An additional file is provided: training.csv, which contains training data for 1000 cells (UMIs) and whether they are singlets (0) or doublets (1). Importantly, the training data are randomly sampled from the full data and thus provides an estimate of the true fraction of doublets.

- The entire data set is represented by 21,954 UMIs and 25,269 genes.

\ **Hackathon objective and evaluation**
- The objective of the hackathon is to correctly predict whether the remaining 20,954 UMIs represent single (singlet) or multiple (doublet) cells. Predictions will be scored using Matthews correlation coefficient (MCC).

\ **Submission**
- Predictions should be posted to your github account as plain text files with two comma delimited columns without headers, the first containing the UMI and the second containing a prediction of whether it is a doublet (1) or singlet (0).

\ **Scoring**
- Text files associated with hackathon registered github accounts will be assessed each day of the competition.  To submit predictions, please make sure that your properly-formatted prediction.csv file is in your forked repository of “/Hackathon-Summer-2023/main/prediction/prediction.csv”.  Prediction files will be pulled at 3 PM and MCC results will be posted shortly afterwards.


