Assignment_B2
================
Han Wang
2023-11-08

<!-- README.md is generated from README.Rmd. Please edit that file -->

# assignmentB2Han

<!-- badges: start -->
<!-- badges: end -->

Given a data frame `data` and a ’ column `group`,
`count_all_missing_by_group()` creates a new data frame with one row per
level of `group`. The first column of the output data frame contains the
levels of `group`, and the rest of the columns contain the number of
missing values for all columns in `data` except `group`. This function
is a wrapper around the `group_by()` and `summarize()` functions in the
`dplyr` package.

## Installation

You can install the development version of assignmentB2Han from
[GitHub](https://github.com/) with:

``` r
# install.packages("devtools")
devtools::install_github("stat545ubc-2023/assignmentB2Han", ref = "0.1.0")
```

## Example

This is a basic example which shows you how to solve a common problem:

``` r
library(assignmentB2Han)
## basic example code
example1 <- count_all_missing_by_group(airquality, Month)
print(example1)
#> # A tibble: 5 × 6
#>   Month Ozone Solar.R  Wind  Temp   Day
#>   <int> <int>   <int> <int> <int> <int>
#> 1     5     5       4     0     0     0
#> 2     6    21       0     0     0     0
#> 3     7     5       0     0     0     0
#> 4     8     5       3     0     0     0
#> 5     9     1       0     0     0     0
example2 <- airquality |> count_all_missing_by_group(Month)
print(example2)
#> # A tibble: 5 × 6
#>   Month Ozone Solar.R  Wind  Temp   Day
#>   <int> <int>   <int> <int> <int> <int>
#> 1     5     5       4     0     0     0
#> 2     6    21       0     0     0     0
#> 3     7     5       0     0     0     0
#> 4     8     5       3     0     0     0
#> 5     9     1       0     0     0     0
example3 <- count_all_missing_by_group(airquality, Month, .groups = "keep")
print(example3)
#> # A tibble: 5 × 6
#> # Groups:   Month [5]
#>   Month Ozone Solar.R  Wind  Temp   Day
#>   <int> <int>   <int> <int> <int> <int>
#> 1     5     5       4     0     0     0
#> 2     6    21       0     0     0     0
#> 3     7     5       0     0     0     0
#> 4     8     5       3     0     0     0
#> 5     9     1       0     0     0     0
```

You’ll still need to render `README.Rmd` regularly, to keep `README.md`
up-to-date. `devtools::build_readme()` is handy for this.

In that case, don’t forget to commit and push the resulting figure
files, so they display on GitHub and CRAN.

After installing the package, you can also access the full documentation
with:

``` r
?count_all_missing_by_group
```
