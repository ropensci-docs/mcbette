# Check if the `mcbette_state` is valid.

Check if the `mcbette_state` is valid. Will
[stop](https://rdrr.io/r/base/stop.html) otherwise.

## Usage

``` r
check_mcbette_state(mcbette_state)
```

## Arguments

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

## Author

Richèl J.C. Bilderbeek
