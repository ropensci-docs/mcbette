# Estimate the marginal likelihoods for one or more inference models

Estimate the marginal likelihoods (aka evidence) for one or more
inference models, based on a single alignment. Also, the marginal
likelihoods are compared, resulting in a relative weight for each model,
where a relative weight of a model close to `1.0` means that that model
is way likelier than the others.

## Usage

``` r
est_marg_liks(
  fasta_filename,
  inference_models = list(beautier::create_inference_model(mcmc =
    beautier::create_ns_mcmc())),
  beast2_optionses = rep(list(beastier::create_mcbette_beast2_options()), times =
    length(inference_models)),
  verbose = FALSE,
  os = rappdirs::app_dir()$os
)
```

## Arguments

- fasta_filename:

  name of the FASTA file

- inference_models:

  a list of one or more inference models, as can be created by
  [create_inference_model](https://docs.ropensci.org/beautier/reference/create_inference_model.html)

- beast2_optionses:

  list of one or more `beast2_options` structures, as can be created by
  [create_mcbette_beast2_options](https://docs.ropensci.org/beastier/reference/create_mcbette_beast2_options.html).
  Use of reduplicated plural to achieve difference with `beast2_options`

- verbose:

  if TRUE show debug output

- os:

  name of the operating system, must be `unix` (Linux, Mac) or `win`
  (Windows)

## Value

a [data.frame](https://rdrr.io/r/base/data.frame.html) showing the
estimated marginal likelihoods (and its estimated error) per combination
of models. Columns are:

- `site_model_name`: name of the site model

- `clock_model_name`: name of the clock model

- `tree_prior_name`: name of the tree prior

- `marg_log_lik`: estimated marginal (natural) log likelihood

- `marg_log_lik_sd`: estimated error of `marg_log_lik`

- `weight`: relative model weight, a value from 1.0 (all evidence is in
  favor of this model combination) to 0.0 (no evidence in favor of this
  model combination)

- `ess`: effective sample size of the marginal likelihood estimation

## Details

In the process, multiple (temporary) files are created (where `[x]`
denotes the index in a list)

- `beast2_optionses[x]$input_filename` path to the the BEAST2 XML input
  file

- `beast2_optionses[x]$output_state_filename` path to the BEAST2 XML
  state file

- `inference_models[x]$mcmc$tracelog$filename` path to the BEAST2 trace
  file with parameter estimates

- `inference_models[x]$mcmc$treelog$filename` path to the BEAST2 `trees`
  file with the posterior trees

- `inference_models[x]$mcmc$screenlog$filename` path to the BEAST2
  screen output file

These file can be deleted manually by
[bbt_delete_temp_files](https://docs.ropensci.org/babette/reference/bbt_delete_temp_files.html),
else these will be deleted automatically by the operating system.

## See also

- [can_run_mcbette](https://docs.ropensci.org/mcbette/reference/can_run_mcbette.md):
  see if 'mcbette' can run

- est_marg_liks: estimate multiple marginal likelihood of a single
  inference mode

## Author

Richèl J.C. Bilderbeek

## Examples

``` r
if (can_run_mcbette()) {

  # Use an example FASTA file
  fasta_filename <- system.file("extdata", "simple.fas", package = "mcbette")

  # Create two inference models
  inference_model_1 <- beautier::create_ns_inference_model(
    site_model = beautier::create_jc69_site_model()
  )
  inference_model_2 <- beautier::create_ns_inference_model(
    site_model = beautier::create_hky_site_model()
  )

  # Shorten the run, by doing a short (dirty, unreliable) MCMC
  inference_model_1$mcmc <- beautier::create_test_ns_mcmc()
  inference_model_2$mcmc <- beautier::create_test_ns_mcmc()

  # Combine the inference models
  inference_models <- list(inference_model_1, inference_model_2)

  # Create the BEAST2 options, that will write the output
  # to different (temporary) filanems
  beast2_options_1 <- beastier::create_mcbette_beast2_options()
  beast2_options_2 <- beastier::create_mcbette_beast2_options()

  # Combine the two BEAST2 options sets,
  # use reduplicated plural
  beast2_optionses <- list(beast2_options_1, beast2_options_2)

  # Compare the models
  marg_liks <- est_marg_liks(
    fasta_filename,
    inference_models = inference_models,
    beast2_optionses = beast2_optionses
  )

  # Interpret the results
  interpret_marg_lik_estimates(marg_liks)

  beastier::remove_beaustier_folders()
  beastier::check_empty_beaustier_folders()
}
```
