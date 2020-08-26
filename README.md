
<!-- *********** -->

<!-- Note: README.md is generated from README.Rmd.   -->

<!-- Be sure to edit README.Rmd and generate the README.md file by Cmd/Ctl-shift-K -->

<!-- *********** -->

# PFU-Database

This repository contains analysis code for the fellowship project for
Paul Brockway. One goal of the fellowship is building a world database
of country-specific primary, final, and useful exergy for 1960–2015.

Analyses are completed using the
[drake](https://github.com/ropensci/drake) environment which provides
helpful dependency management.

## Quick start

At the RStudio console, type

``` r
library(drake)         # to load the drake package   
vis_drake_graph(plan)  # to see a directed acyclic graph of the calculations that will take place   
r_make()               # to execute the calculations
```

## Advanced

### Keyboard shortcuts

Consider setting RStudio keyboard shortcuts for executing the drake plan
in this repository. See `Tools|Modify keyboard shortcuts...`. Some
convenient keyboard shortcuts are:

  - `command-option-control-D` (for *d*rake) to execute the “Run a drake
    workflow” command on the `plan`
  - `command-option-control-V` (for *v*isualize) to execute the
    “Visualize a drake workflow” command on the `plan`

With those keyboard shortcuts in place, the

`library(drake)`

command needs to be issued only *once* after first opening the project
in RStudio.

Thereafter, type the keyboard shortcut `command-option-control-D`
(instead of `r_make()`) to re-run the analysis. Type the keyboard
shortcut `command-option-control-V` (instead of `vis_drake_graph(plan)`)
to visualize the dependency tree as a directed acyclic graph. The
command `sankey_drake_graph(plan)` will produce a Sankey diagram of the
dependency tree.

### Programming

Source the `R/init.R` file to load all resources for computation at the
RStudio console.

### Accessing targets

`readd(<<target>>)` pulls the value of a target out of `drake`’s cache.
`<<target>>` should be a quoted character string such as “Specified”.

`loadd(<<target>>)` copies the value of a target out of `drake`’s cache
into the environment.

`readd_by_country(<<target>>, <<country>>)` will reads country-specific
data out of the `drake` cache. Both `<<target>>` and `<<country>>`
should be strings. `<<country>>` should be a 3-letter ISO abbreviation
such as “ESP” or “ZAF”.

### Fresh start

`clean()` invalidates `drake`’s cache and forces reanalysis of
everything. Reanalyzing everything may take a while.

### More

See the [drake manual](https://books.ropensci.org/drake/) for details.

## Contributors

  - Emmanuel Aramendia, University of Leeds
  - Paul Brockway, University of Leeds
  - Matthew Kuperus Heun, Calvin University
  - Zeke Marshall, University of Leeds
