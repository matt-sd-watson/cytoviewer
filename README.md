# cytoviewer

<!-- badges: start -->
[![codecov](https://codecov.io/gh/BodenmillerGroup/cytoviewer/branch/devel/graph/badge.svg)](https://app.codecov.io/gh/BodenmillerGroup/cytoviewer/tree/devel)
[![docs](https://github.com/BodenmillerGroup/cytoviewer/actions/workflows/docs.yml/badge.svg)](https://github.com/BodenmillerGroup/cytoviewer/actions/workflows/docs.yml)
<!-- badges: end -->

An interactive multi-channel image viewer for R. 

This shiny application allows users to interactively visualize multi-channel 
images and masks. The `cytoviewer` package is divided into image-level (Composite and Channels) 
and cell-level visualization (Masks). It allows users to overlay individual images 
with masks and integrates well with [SingleCellExperiment](https://bioconductor.org/packages/release/bioc/html/SingleCellExperiment.html) 
and [SpatialExperiment](https://bioconductor.org/packages/release/bioc/html/SingleCellExperiment.html) objects for metadata visualization. 

## Check status

| Bioc branch | Checks |
|:-----------:|:------:|
| Release     |[![build-check-release](https://github.com/BodenmillerGroup/cytoviewer/workflows/build-checks-release/badge.svg)](https://github.com/BodenmillerGroup/cytoviewer/actions?query=workflow%3Abuild-checks-release)|
| Devel       |[![build-check-devel](https://github.com/BodenmillerGroup/cytoviewer/workflows/build-checks-devel/badge.svg)](https://github.com/BodenmillerGroup/cytoviewer/actions?query=workflow%3Abuild-checks-devel)|


## Requirements

The `cytoviewer` package requires R version >= 4.0.
It builds on data objects and functions contained in the [cytomapper](https://bioconductor.org/packages/release/bioc/html/cytomapper.html) package. 

## Installation 

The `cytoviewer` package can be installed from `Bioconductor` via:

```r
if (!requireNamespace("BiocManager", quietly = TRUE))
    install.packages("BiocManager")

BiocManager::install("cytoviewer")
```

The development version of `cytoviewer` can be installed from Github via:

```r
if (!requireNamespace("remotes", quietly = TRUE))
    install.packages("remotes")

remotes::install_github("BodenmillerGroup/cytoviewer")
```

To load the package in your R session, type the following:

```r
library(cytoviewer)
```
## Usage

```r
library(cytoviewer)
library(cytomapper)

# Load example datasets 
data("pancreasImages")
data("pancreasMasks")
data("pancreasSCE")

# Use shiny with images, masks and SCE object
app <- cytoviewer(image = pancreasImages, mask = pancreasMasks, object = pancreasSCE, img_id = "ImageNb", cell_id = "CellNb")
shiny::runApp(app, launch.browser = TRUE)
```

## Contributing

For feature requests, please open an issue [here](https://github.com/BodenmillerGroup/cytoviewer/issues).

Alternatively, feel free to fork the repository, add your changes and issue a pull request.

## Citation 

A manuscript is in preparation.

If you are using `cytoviewer` in your work, please reach out to inquire how to best cite the tool.

## Authors

[Lasse Meyer](https://github.com/lassedochreden) lasse.meyer 'at' dqbm.uzh.ch

[Nils Eling](https://github.com/nilseling) nils.eling 'at' dqbm.uzh.ch
