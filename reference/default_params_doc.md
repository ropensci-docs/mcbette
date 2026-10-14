# Documentation of general function arguments. This function does nothing. It is intended to inherit function argument documentation.

Documentation of general function arguments. This function does nothing.
It is intended to inherit function argument documentation.

## Usage

``` r
default_params_doc(
  beast2_bin_path,
  beast2_folder,
  beast2_working_dir,
  beast2_options,
  beast2_optionses,
  clock_model,
  clock_models,
  epsilon,
  fasta_filename,
  inference_model,
  inference_models,
  marg_liks,
  mcbette_state,
  mcmc,
  os,
  rng_seed,
  site_model,
  site_models,
  tree_prior,
  tree_priors,
  verbose
)
```

## Arguments

- beast2_bin_path:

  path to the the BEAST2 binary file

- beast2_folder:

  the folder where the BEAST2 is installed. Note that this is not the
  folder where the BEAST2 executable is installed: the BEAST2 executable
  is in a subfolder. Use
  [get_default_beast2_folder](https://docs.ropensci.org/beastier/reference/get_default_beast2_folder.html)
  to get the default BEAST2 folder. Use
  [get_default_beast2_bin_path](https://docs.ropensci.org/beastier/reference/get_default_beast2_bin_path.html)
  to get the full path to the default BEAST2 executable. Use
  [get_default_beast2_jar_path](https://docs.ropensci.org/beastier/reference/get_default_beast2_jar_path.html)
  to get the full path to the default BEAST2 jar file.

- beast2_working_dir:

  folder in which BEAST2 will run and produce intermediate files. By
  default, this is a temporary folder

- beast2_options:

  a `beast2_options` structure, as can be created by
  [create_mcbette_beast2_options](https://docs.ropensci.org/beastier/reference/create_mcbette_beast2_options.html).

- beast2_optionses:

  list of one or more `beast2_options` structures, as can be created by
  [create_mcbette_beast2_options](https://docs.ropensci.org/beastier/reference/create_mcbette_beast2_options.html).
  Use of reduplicated plural to achieve difference with `beast2_options`

- clock_model:

  a clock model, as can be created by
  [create_clock_model](https://docs.ropensci.org/beautier/reference/create_clock_model.html)

- clock_models:

  a list of one or more clock models, as can be created by
  [create_clock_models](https://docs.ropensci.org/beautier/reference/create_clock_models.html)

- epsilon:

  measure of relative accuracy. Smaller values result in longer, more
  precise estimations

- fasta_filename:

  name of the FASTA file

- inference_model:

  an inference model, as can be created by
  [create_inference_model](https://docs.ropensci.org/beautier/reference/create_inference_model.html)

- inference_models:

  a list of one or more inference models, as can be created by
  [create_inference_model](https://docs.ropensci.org/beautier/reference/create_inference_model.html)

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

- mcbette_state:

  the
  [mcbette](https://docs.ropensci.org/mcbette/reference/mcbette-package.md)
  state, which is a [list](https://rdrr.io/r/base/list.html) with the
  following elements:

  - beast2_installed [TRUE](https://rdrr.io/r/base/logical.html) if
    BEAST2 is installed, [FALSE](https://rdrr.io/r/base/logical.html)
    otherwise

  - ns_installed [NA](https://rdrr.io/r/base/NA.html) if BEAST2 is not
    installed. [TRUE](https://rdrr.io/r/base/logical.html) if the BEAST2
    NS package is installed [FALSE](https://rdrr.io/r/base/logical.html)
    if the BEAST2 NS package is not installed

- mcmc:

  an MCMC for the Nested Sampling run, as can be created by
  [create_mcmc_nested_sampling](https://docs.ropensci.org/beautier/reference/create_ns_mcmc.html)

- os:

  name of the operating system, must be `unix` (Linux, Mac) or `win`
  (Windows)

- rng_seed:

  a random number generator seed used for the BEAST2 inference

- site_model:

  a site model, as can be created by
  [create_site_model](https://docs.ropensci.org/beautier/reference/create_site_model.html)

- site_models:

  a list of one or more site models, as can be created by
  [create_site_models](https://docs.ropensci.org/beautier/reference/create_site_models.html)

- tree_prior:

  a tree prior, as can be created by
  [create_tree_prior](https://docs.ropensci.org/beautier/reference/create_tree_prior.html)

- tree_priors:

  a list of one or more tree priors, as can be created by
  [create_tree_priors](https://docs.ropensci.org/beautier/reference/create_tree_priors.html)

- verbose:

  if TRUE show debug output

## Note

This is an internal function, so it should be marked with `@noRd`. This
is not done, as this will disallow all functions to find the
documentation parameters

## Author

Richèl J.C. Bilderbeek
