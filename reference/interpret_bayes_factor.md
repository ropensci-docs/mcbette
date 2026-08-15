# Interpret a Bayes factor

Interpret a Bayes factor, using the interpretation from \[1\].

## Usage

``` r
interpret_bayes_factor(bayes_factor)
```

## Arguments

- bayes_factor:

  Bayes factor to be interpreted

## Value

a string with the interpretation in English

## Details

- \[1\] H. Jeffreys (1961). The Theory of Probability (3rd ed.).
  Oxford. p. 432

## Author

Richèl J.C. Bilderbeek

## Examples

``` r
interpret_bayes_factor(0.5)
#> [1] "in favor of other model"

beastier::remove_beaustier_folders()
beastier::check_empty_beaustier_folders()
```
