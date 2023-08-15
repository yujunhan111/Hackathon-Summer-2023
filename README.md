# University of Rochester Biomedical Data Science Hackathon Summer 2023
Welcome to the landing page for the hackathon. All important information will appear here when the competition starts. In the meantime, please register and watch for further instructions. All teams scoring better than random will receive a participation prize. 1st and 2nd place winning teams in each division will get a cash prize (see below).

# Logistics

- Registration is now closed.  Teams can consist of up to 4 people. Complete registration details on this [google form](https://docs.google.com/forms/d/e/1FAIpQLSdQbzq6q0RfRz4E9-r0cDUTW9a7YsMDyCOyuEtqcZaLpq0Omg/viewform). 
0.   Each team must have a github handle associated with it in order to participate.  Make sure you edit your registration or email the organizers to provide this, if you haven't yet.
1.   You may add team members up
to noon EDT on 8/17 by editing your response to the google form or emailing the organizers.
2.  Teams of entirely undergraduates will be in the undergraduate
division, else they will be in the open division.
3.  Predictions on test data set are submitted by pushing to
    github.  A repository with the name `Hackathon-Summer-2023`,
    owned by the team captain, will
    be queried for a file named [prediction/prediction.csv](prediction/prediction.csv).  **If the team captain forks this
    repository and writes predictions there everything should work
    (as long as the predictions are formatted correctly).**
2.  Predictions will be scored at least once daily, starting 8/16, with
    scores posted by 3 PM.  At
    the organizers' option, predictions may be scored more frequently
    than this.
2.  General questions/problems can be directed to [issues](https://github.com/Rochester-Biomedical-DS/Hackathon-Summer-2023/issues) page.  We encourage other hackathon participants to respond to issues.
3.  The scoreboard will be located
    [here](Leaderboard.Hackathon.2023.md).
   
    We  cannot provide support
    beyond the diagnostic output included on the scoreboard if an error is
    encountered in scoring your predictions.
5.  Interim scoring may employ forms of randomization (e.g. bootstrapping) from the test data set.  The final scores will use all the data and not be randomized.
4.  Competition runs through 2:59 PM EDT 19-August-2023.  The predictions each team has committed to their repository at that time will be used to determine their final score.

# Overview
Single cell RNA sequencing (scRNA-seq) is a recently developed technology platform used to measure gene expression from thousands of individual cells. scRNA-seq is transforming biology and medicine as it enables studies of cell-heterogeneity, identification of cell types and subpopulations in complex tissues and measuring cell transformations during development. However, scRNA-seq also has a number of analysis challenges commonly encountered in data science. One of the main challenges is that the read count matrix (genes x cells) is sparse in that it contains many zeros due to technological limitations (e.g. only a thousands genes have count data from an individual cell even though many more genes are expressed in that cell). For an overview of how scRNA-seq data is obtained and best practices for scRNA-seq analysis see Huemos et al. (2023, [PMC10066026](https://www.nature.com/articles/s41576-023-00586-w)).

The goal of this hackathon is to identify doublets in scRNA-seq data. Doublets or multiplets are cases where gene expression count data is generated from two or more cells rather than a single cell. This occurs when a unique molecular identifier (UMI) is associated with two cells in a liquid droplet rather than one, resulting in a mixture of expression from both cells. There are a variety of ways in which doublets can be detected, most often by cells that appear to show a mixture of expression patterns from two different cell types. Doublets involving the same cell type are much more difficult to detect. One's ability to detect doublets depends on how one deals with sparse data, normalization and cell type clustering. For a review of methods see Xi and Li (2021, [PMC7897250](https://doi.org/10.1016/j.cels.2020.11.008)). Accurate detection of doublets remains a significant challenge and no single method outperforms all others.

# Data
See [data description](Data.Description.md) for details.

   # Prizes
   
1.  First place in each division: $300 + $75 x (team size)
2.  Second place in each division: 0 + $50 x (team size)
  
