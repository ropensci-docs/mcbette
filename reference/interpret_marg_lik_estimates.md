# Interpret the marginal likelihood estimates

Interpret the marginal likelihood estimates as created by
[est_marg_liks](https://docs.ropensci.org/mcbette/reference/est_marg_liks.md).

## Usage

``` r
interpret_marg_lik_estimates(marg_liks)
```

## Arguments

- marg_liks:

  a table of (estimated) marginal likelihoods, as, for example, created
  by
  [est_marg_liks](https://docs.ropensci.org/mcbette/reference/est_marg_liks.md).
  This [data.frame](https://rdrr.io/r/base/data.frame.html) has the
  following columns:

  - `site_model_name`: name of the site model, must be an element of
    [get_site_model_names](https://docs.ropensci.org/beautier/reference/get_site_model_names.html)

  - `clock_model_name`: name of the clock model, must be an element of
    [get_clock_model_names](https://docs.ropensci.org/beautier/reference/get_clock_model_names.html)

  - `tree_prior_name`: name of the tree prior, must be an element of
    [get_tree_prior_names](https://docs.ropensci.org/beautier/reference/get_tree_prior_names.html)

  - `marg_log_lik`: estimated marginal (natural) log likelihood

  - `marg_log_lik_sd`: estimated error of `marg_log_lik`

  - `weight`: relative model weight, a value from 1.0 (all evidence is
    in favor of this model combination) to 0.0 (no evidence in favor of
    this model combination)

  - `ess`: effective sample size of the marginal likelihood estimation

  Use
  [get_test_marg_liks](https://docs.ropensci.org/mcbette/reference/get_test_marg_liks.md)
  to get a test `marg_liks`. Use
  [is_marg_liks](https://docs.ropensci.org/mcbette/reference/is_marg_liks.md)
  to determine if a `marg_liks` is valid. Use
  [check_marg_liks](https://docs.ropensci.org/mcbette/reference/check_marg_liks.md)
  to check that a `marg_liks` is valid.

## Author

Richèl J.C. Bilderbeek
