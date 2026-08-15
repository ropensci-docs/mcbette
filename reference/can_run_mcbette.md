# Can 'mcbette' run?

Can 'mcbette' run? Will return
[TRUE](https://rdrr.io/r/base/logical.html) if:

- \(1\) Running on Linux or MacOS

- \(2\) BEAST2 is installed

- \(3\) The BEAST2 NS package is installed

## Usage

``` r
can_run_mcbette(beast2_folder = beastier::get_default_beast2_folder())
```

## Arguments

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

## Author

Richèl J.C. Bilderbeek

## Examples

``` r
can_run_mcbette()
#> [1] FALSE

beastier::remove_beaustier_folders()
beastier::check_empty_beaustier_folders()
```
