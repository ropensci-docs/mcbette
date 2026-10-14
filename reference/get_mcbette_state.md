# Get the current state of [mcbette](https://docs.ropensci.org/mcbette/reference/mcbette-package.md)

Get the current state of
[mcbette](https://docs.ropensci.org/mcbette/reference/mcbette-package.md)

## Usage

``` r
get_mcbette_state(beast2_folder = beastier::get_default_beast2_folder())
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

## Value

a [list](https://rdrr.io/r/base/list.html) with the following elements:

- beast2_installed [TRUE](https://rdrr.io/r/base/logical.html) if BEAST2
  is installed, [FALSE](https://rdrr.io/r/base/logical.html) otherwise

- ns_installed [TRUE](https://rdrr.io/r/base/logical.html) if the BEAST2
  NS package is installed [FALSE](https://rdrr.io/r/base/logical.html)
  if the BEAST2 or the BEAST2 NS package is not installed

## Examples

``` r
get_mcbette_state()
#> $beast2_installed
#> [1] FALSE
#> 
#> $ns_installed
#> [1] FALSE
#> 

beastier::remove_beaustier_folders()
beastier::check_empty_beaustier_folders()
```
