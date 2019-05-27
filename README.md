
<!-- README.md is generated from README.Rmd. Please edit that file -->

## Overview

<!-- badges: start -->

<!-- badges: end -->

A polynomial piecewise regression model for the optimal segmentation of
a time series with regime changes. It uses dynamic programming for the
segmentation and the LSE for the estimation of the regression
parameters.

## Installation

You can install the development version of RHLP from
[GitHub](https://github.com/) with:

``` r
# install.packages("devtools")
devtools::install_github("fchamroukhi/PWR_R")
```

To build *vignettes* for examples of usage, type the command below
instead:

``` r
# install.packages("devtools")
devtools::install_github("fchamroukhi/PWR_R", 
                         build_opts = c("--no-resave-data", "--no-manual"), 
                         build_vignettes = TRUE)
```

Use the following command to display vignettes:

``` r
browseVignettes("PWR")
```

## Usage

``` r
library(PWR)

data("simulatedtimeserie")
fData <- FData(simulatedtimeserie$X, t(simulatedtimeserie$Y))

K <- 5 # number of segments
p <- 3 # polynomial degree
modelPWR <- ModelPWR(fData, K, p)

solution <- fitPWRFisher(modelPWR)

solution$plot()
```

<img src="man/figures/README-unnamed-chunk-5-1.png" style="display: block; margin: auto;" /><img src="man/figures/README-unnamed-chunk-5-2.png" style="display: block; margin: auto;" />
