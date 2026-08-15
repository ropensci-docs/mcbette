# Create a [mcbette](https://docs.ropensci.org/mcbette/reference/mcbette-package.md) report, to be used when reporting bugs

Create a
[mcbette](https://docs.ropensci.org/mcbette/reference/mcbette-package.md)
report, to be used when reporting bugs

## Usage

``` r
mcbette_report(beast2_folder = beastier::get_default_beast2_folder())
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

nothing. It is intended that the output (not the return value) is
copy-pasted from screen.

## Author

Richèl J.C. Bilderbeek

## Examples

``` r
if(beautier::is_on_ci()) {
  mcbette_report()
}
```
