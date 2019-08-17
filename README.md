
<!-- README.md is generated from README.Rmd. Please edit that file -->

# Ipaper

<!-- badges: start -->

[![Travis Build
Status](https://travis-ci.org/kongdd/Ipaper.svg?branch=master)](https://travis-ci.org/kongdd/Ipaper)
[![AppVeyor Build
Status](https://ci.appveyor.com/api/projects/status/github/kongdd/rwiki?branch=master&svg=true)](https://ci.appveyor.com/project/kongdd/Ipaper)
[![codecov](https://codecov.io/gh/kongdd/Ipaper/branch/master/graph/badge.svg)](https://codecov.io/gh/kongdd/Ipaper)
[![License](http://img.shields.io/badge/license-GPL%20%28%3E=%203%29-brightgreen.svg?style=flat)](http://www.gnu.org/licenses/gpl-3.0.html)
[![CRAN](http://www.r-pkg.org/badges/version/rwiki)](https://cran.r-project.org/package=rwiki)
<!-- badges: end -->

## Installation

``` r
devtools::install_github("kongdd/Ipaper")
```

## FUNCTIONS

### `rstudio` shortcuts addin

| Description                                       | Shortcut     |
| ------------------------------------------------- | ------------ |
| copy lines at the cursor position (sublime style) | Alt+c        |
| clip lines at the cursor position                 | Alt+x        |
| Insert `%<>%`                                     | Ctrl+Shift+, |
| Insert `%do% {}`                                  | Ctrl+Shift+D |
| Insert `%in% {}`                                  | Ctrl+Shift+I |

### Visualization

  - `draw.colorkey`: modified from lattice, add triangle head and tail
    
    ![](man/figures/lgd_draw.colorkey.svg)

  - `geom_boxplot2`: boxplot without outlier
    
    ![](man/figures/geom_boxplot2.svg)

  - `ggplot_legend`: get the legend (grid obj) of ggplot object

  - `write_fig`: Unify figure writing functions, e.g. png, pdf, tif, svg

### Parallel functions

  - e.g. `InitCluster`, `killCluster`.

### Base tools

  - `dir.show`: open at assigned directory in explorer
  - `runningId`: print the running ID in the console
  - `fprintf`: c style `fprintf`
  - `subl`: open sublime text at assigned directory
  - `github`: open github desktop at assigned directory
  - `melt_list`, `melt_tree`, `listk`, `dcast2`

<!-- end list -->

``` r
df <- data.frame(year = 2010, day = 1:2, month = 1, site = "A")
l  <- list(a = df, b = df)
melt_list(l, "id")
#>   year day month site id
#> 1 2010   1     1    A  a
#> 2 2010   2     1    A  a
#> 3 2010   1     1    A  b
#> 4 2010   2     1    A  b

l2 <- listk("type1" = l, "type2" = l)
melt_tree(l2, c("type", "id"))
#>   year day month site id  type
#> 1 2010   1     1    A  a type1
#> 2 2010   2     1    A  a type1
#> 3 2010   1     1    A  b type1
#> 4 2010   2     1    A  b type1
#> 5 2010   1     1    A  a type2
#> 6 2010   2     1    A  a type2
#> 7 2010   1     1    A  b type2
#> 8 2010   2     1    A  b type2
```

  - `mkTrend`, `slope`

<!-- end list -->

``` r
x <- c(4.81,4.17,4.41,3.59,5.87,3.83, 6.03,4.89,4.32,10,4.69)
# r <- mkTrend(x)
par(mar = c(3, 3, 1, 1), mgp = c(2, 0.6, 0))
r_cpp <- mkTrend_rcpp(x, IsPlot = TRUE)
```

<img src="man/figures/README-mkTrend-1.svg" width="100%" />

  - `reoder_name`, `rm_empty`, `match2`
  - `write_list2xlsx`, `read_xlsx2list`
  - `which.na`, `which.notna`
