
<!-- README.md is generated from README.Rmd. Please edit that file -->

# qwickr

<!-- badges: start -->

<!-- badges: end -->

qwickr provides a quick and easy way to analyze clinical trial and other
similar data, and report results in Word format.

## Installation

You can install the released version of qwickr from
[CRAN](https://CRAN.R-project.org) with:

``` r
install.packages("qwickr")
```

## Example

This is a basic example which shows you how to solve a common problem:

``` r
knitr::opts_chunk$set(
  collapse = TRUE,
  comment = "#>",
  fig.path = "README-"
)
library(qwickr)
## summarize results for a catetorical outcome based on a categorical independent variable
group <- rep(c("A", "B"), 10)
gender <- rep(c(1,1,0,0), 5)
time <- rep(1, 10)
x <- data.frame(group, gender, time)
grab <- q.cat(x, outcomevar="gender", groupvar = "group", timevar = "time", writetoword = T)
#> Study groups:  A B 
#> Time points:  1 
#> Outcomes:  0 1 
#> Minimum count per cell:  5 
#> Fisher's p-value:  1 
#> Chi Square p-value:  1 
#> Final p-value:  1.000 
#>  
#>   Variable          A          B p-value
#> 1   gender                              
#> 2  Visit 1                         1.000
#> 3        0 5 (50.00%) 5 (50.00%)        
#> 4        1 5 (50.00%) 5 (50.00%)        
#>   Variable A B p-value
#> 1   gender            
#> [1] "gender"
#> ##------ Fri Apr 10 17:54:26 2020 ------##
```
