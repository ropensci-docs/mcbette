# Calculate the weights for each marginal likelihood

Calculate the weights for each marginal likelihood

## Usage

``` r
calc_weights(marg_liks)
```

## Arguments

- marg_liks:

  (non-log) marginal likelihood estimates

## Value

the weight of each marginal likelihood estimate, which will sum up to
1.0

## Author

Richèl J.C. Bilderbeek

## Examples

``` r
# Evidences (aka marginal likelihoods) can be very small
evidences <- c(0.0001, 0.0002, 0.0003, 0.0004)

# Sum will be 1.0
calc_weights(evidences)
#> [1] 0.1 0.2 0.3 0.4

beastier::remove_beaustier_folders()
beastier::check_empty_beaustier_folders()
```
