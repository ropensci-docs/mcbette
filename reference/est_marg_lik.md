# Estimate the marginal likelihood for an inference model.

Estimate the marginal likelihood for an inference model.

## Usage

``` r
est_marg_lik(
  fasta_filename,
  inference_model = beautier::create_ns_inference_model(),
  beast2_options = beastier::create_mcbette_beast2_options(),
  os = rappdirs::app_dir()$os
)
```

## Arguments

- fasta_filename:

  name of the FASTA file

- inference_model:

  an inference model, as can be created by
  [create_inference_model](https://docs.ropensci.org/beautier/reference/create_inference_model.html)

- beast2_options:

  a `beast2_options` structure, as can be created by
  [create_mcbette_beast2_options](https://docs.ropensci.org/beastier/reference/create_mcbette_beast2_options.html).

- os:

  name of the operating system, must be `unix` (Linux, Mac) or `win`
  (Windows)

## Value

a [list](https://rdrr.io/r/base/list.html) showing the estimated
marginal likelihoods (and its estimated error), its items are::

- `marg_log_lik`: estimated marginal (natural) log likelihood

- `marg_log_lik_sd`: estimated error of `marg_log_lik`

- `esses` the Effective Sample Size

## See also

- [can_run_mcbette](https://docs.ropensci.org/mcbette/reference/can_run_mcbette.md):
  see if 'mcbette' can run

- [est_marg_liks](https://docs.ropensci.org/mcbette/reference/est_marg_liks.md):
  estimate multiple marginal likelihoods

## Author

Richèl J.C. Bilderbeek

## Examples

``` r
if (can_run_mcbette()) {

  # An example FASTA file
  fasta_filename <- system.file("extdata", "simple.fas", package = "mcbette")

  # A testing inference model with inaccurate (thus fast) marginal
  # likelihood estimation
  inference_model <- beautier::create_ns_inference_model()

  # Shorten the run, by doing a short (dirty, unreliable) MCMC
  inference_model$mcmc <- beautier::create_test_ns_mcmc()

  # Setup the options for BEAST2 to be able to call BEAST2 packages
  beast2_options <- beastier::create_mcbette_beast2_options()

  # Estimate the marginal likelihood
  est_marg_lik(
    fasta_filename = fasta_filename,
    inference_model = inference_model,
    beast2_options = beast2_options
  )

  beastier::remove_beaustier_folders()
}
```
