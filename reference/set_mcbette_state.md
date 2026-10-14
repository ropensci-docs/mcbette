# Set the [mcbette](https://docs.ropensci.org/mcbette/reference/mcbette-package.md) state.

Set the
[mcbette](https://docs.ropensci.org/mcbette/reference/mcbette-package.md)
state to having BEAST2 installed with or without installing the BEAST2
NS package.

## Usage

``` r
set_mcbette_state(
  mcbette_state,
  beast2_folder = beastier::get_default_beast2_folder(),
  verbose = FALSE
)
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

- verbose:

  if TRUE show debug output

## Note

In newer versions of BEAST2, BEAST2 comes pre-installed with the BEAST2
NS package. For such a version, one cannot install BEAST2 without NS. A
warning will be issues if one intends to only install BEAST2 (i.e.
without the BEAST2 NS package) and gets the BEAST2 NS package installed
as a side effect as well.

Also, installing or uninstalling a BEAST2 package from a BEAST2
installation will affect all installations.

## See also

- Use
  [get_mcbette_state](https://docs.ropensci.org/mcbette/reference/get_mcbette_state.md)
  to get the current
  [mcbette](https://docs.ropensci.org/mcbette/reference/mcbette-package.md)
  state

- Use
  [check_mcbette_state](https://docs.ropensci.org/mcbette/reference/check_mcbette_state.md)
  to check the current
  [mcbette](https://docs.ropensci.org/mcbette/reference/mcbette-package.md)
  state
