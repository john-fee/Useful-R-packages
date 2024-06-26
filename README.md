Useful R packages
================
John Fee
2024-06-15

# Documenting data

- [codebookr](https://github.com/jfjelstul/codebookr)
- [codebook](https://rubenarslan.github.io/codebook/)
- [vtable](https://nickch-k.github.io/vtable/index.html)
  - Quick way to summarize data and expose data labels (Is there a way
    to integrate with other data documenting packages?)

# Creating Documents

- [Creating document
  templates](https://bookdown.org/yihui/rmarkdown/document-templates.html)
  - This will be useful to create a default analysis document so we
    don’t have to write boilerplate code to setup data access every time
- [bslib](https://rstudio.github.io/bslib/)
  - Nice options for theming html documents produced by Rmd
  - Should work with `flexdashboard`!
- [reactable](https://glin.github.io/reactable/) and
  [reactablefmtr](https://kcuilla.github.io/reactablefmtr/)
  - The best options (I’ve found) for creating nice customizable tables
    for html documents.
- [kableExtra](https://haozhu233.github.io/kableExtra/)
  - Nice lightweight table package for html/pdf documents
- [gt](https://gt.rstudio.com/)
  - Table making package which I’ve heard good things about - might be
    worth trying out

# Data processing

- `tidyverse` is generally useful, particularly `dplyr`, `tidyr`,
  `janitor`, `stringr`, `readr`, `glue`.
- [tidylog](https://github.com/elbersb/tidylog)
  - Provides helpful warnings/feedback when manipulating data with dplyr
    and tidyr.
- [powerjoin](https://github.com/moodymudskipper/powerjoin)
  - Extension to `dplyr` to check joins and do fuzzy matching
- [dtrackr](https://cran.r-project.org/web/packages/dtrackr/index.html)
  - Document data pipelines
- [dm](https://dm.cynkra.com/index.html)
  - Provides a grammer for working with and documenting related
    dataframes/tables. Successor to
    [datamodelr](https://github.com/bergant/datamodelr).
- [dtplyr](https://dtplyr.tidyverse.org/)
  - Provides `data.table` backend for `dplyr`
- [tidytable](https://github.com/markfairbanks/tidytable)
  - Provides implementation of `dplyr` syntax natively in `data.table`
- [arrow](https://arrow.apache.org/docs/r/)
  - is a really nice way to handle large datasets. Is a good option too
    if you can’t setup a dedicated database.  
- [dbplyr](https://dbplyr.tidyverse.org/)
  - is for when you *do* have to pull data out of databases, but your
    dplyr code to be translated to SQL.
- [duckplyr](https://duckdb.org/2024/04/02/duckplyr)
  - Native dplyr-style manipulation with DuckDB.
- [naniar](https://github.com/njtierney/naniar)
  - Helps identify and visualize missingness in a dataset
- [visdat](https://github.com/ropensci/visdat)
  - Provides some quick utilities for identifying the structure of a
    dataset

# Plotting

- [ggplot2](https://ggplot2.tidyverse.org/)
- [ggforce](https://ggforce.data-imaginist.com/)
  - A package with (lots of) extensions of to ggplot. A good place to
    look first when something is a little awkward to do in base ggplot.
- [scales](https://scales.r-lib.org/)
  - I use this a lot to create nicely formatted ggplot axes, but also
    the functions are useful for generic formatting (e.g. I use
    `label_comma` often to format data for tables)
- [cowplot](https://github.com/wilkelab/cowplot)
  - Nice theme, some functions for arranging and sizing plots
- [ggpubr](https://rpkgs.datanovia.com/ggpubr/)
  - Some nice shortcuts to make common plots good looking. E.g. density
    plots with median reference lines and rugs, lollipop chart, etc.
  - Also has a nice theme to use
- [ggside](https://github.com/jtlandis/ggside)
  - Nice option to add side plots
- [ggmosaic](https://haleyjeppson.github.io/ggmosaic/index.html)
  - Package to produce mosaic plots, which I think are intuitive but
    sadly seem to be confusing initially to others
- [ggfittext](https://github.com/wilkox/ggfittext)
  - Dynamically resize text/labels to fit into other geoms
- [binsreg](https://nppackages.github.io/binsreg/)
  - A package for plotting binscatters, which is an interesting
    (nonparameteric) approach for visualizing relationships. Not sure of
    the advantages vs splines though.
- [ggdist](https://mjskay.github.io/ggdist/)
  - A go-to library for communicating distributions,and uncertainty
    about distributions!
- [gghighlight](https://yutannihilation.github.io/gghighlight/)
  - Convenient way to highlight only a few obs (saves some typing)
- [geomtextpath](https://github.com/AllanCameron/geomtextpath)
  - Nice way to create labeled lines
- [ggrepel](https://ggrepel.slowkow.com/)
  - Extremely useful way to plot jittered labels and text
- [prettyunits](https://github.com/r-lib/prettyunits)
  - Has some nice heuristic functions for formatting numbers for
    presentation
- [marquee](https://marquee.r-lib.org/index.html)
  - Provides options render text using markdown syntax inside of
    graphics. Can be used to color text for ggplots!
  - Required updating R + RStudio (on 6/1/2024) to get the text to
    render.

## Options to arrange plots within a multiplot

- [patchwork](https://patchwork.data-imaginist.com/)
  - Syntax seems easy to use - I should explore it more!
- `cowplot`
  - More familiar with how to arrange plots with this
- [egg](https://github.com/baptiste/egg)

## Color palettes

This isn’t something I have been principled about - would be nice to
leverage these and start!

- [microshades](https://karstenslab.github.io/microshades/)
  - Nice package for color-blind accessible palettes. No ggplot themes
    built in (so this will require use the `scale_*_manual` functions),
    or some additional boilerplate to play nicely with ggplot.
- [palettes](https://tidytales.ca/posts/2022-12-20_palettes/)
  - A package for making a standardized color palette that plays nicely
    with various plotting libraries. I should lean on this for custom
    palettes!

# Coding/Productivity

## Functional programming

- [magrittr](https://cran.r-project.org/web/packages/magrittr/vignettes/magrittr.html)
  - The source of the pipe operator which is incorporated into the
    tidyverse. Also has some operators like `%$%` (pipes in and exposes
    names - like using `with`) and some aliases for operations to make
    them easier to use with pipe-syntax
- [purrr](https://purrr.tidyverse.org/)
  - is a great tool for handling situations that would require loops.
- [furrr](https://furrr.futureverse.org/)
  - is a good way to speed up `purrr` when needed

## Testing

- [testthat](https://testthat.r-lib.org/)
  - Unit testing in `R`
- [asserthat](https://github.com/hadley/assertthat)
  - utilities for run-time assertions
  - Use functions from here instead of `stopifnot`
- [checkmate](https://mllg.github.io/checkmate/index.html)
  - Convenient type checking assertions
- [cli](https://github.com/r-lib/cli)
  - In this context, could be useful for constructing nice error
    messages/warnings
- [hedgehog](https://cran.r-project.org/web/packages/hedgehog/vignettes/hedgehog.html)
  - Property testing package that integrates with testthat and quickly
    identifies useful counterexamples
- [quickcheck](https://armcn.github.io/quickcheck/)
  - Property testing package the builds on hedgehog, provides more
    generators and other useful functions

## Dev tools

- [fusen](https://thinkr-open.github.io/fusen/)
  - Build a package from Rmarkdown documents! I think this has a lot of
    potential.
- [lintr](https://github.com/r-lib/lintr) and
  [styler](https://github.com/r-lib/styler) are helpful packages for
  linting and styling R code
- [boomer](https://github.com/moodymudskipper/boomer) Debugging tools to
  view the intermediate results of a function call
- [flow](https://github.com/moodymudskipper/flow) code diagrams
- [import](https://cran.r-project.org/web/packages/import/index.html)
  - Nice package for controlling function imports (including from other
    scripts)
- [docstring](https://cran.r-project.org/web/packages/docstring/index.html)
  - Allows function documentation (with help pages) outside of a package

## Misc

- [memoise](https://memoise.r-lib.org/index.html)
  - Caches function output. Useful for interactive use (debugging), also
    for speeding up scripts with repetitive function calls!
- [chronicler](https://cran.r-project.org/web/packages/chronicler/index.html)
  - function logging
- [progressr](https://cran.r-project.org/web/packages/progressr/index.html)
  - lightweight package for reporting progress updates
- [zeallot](https://cran.r-project.org/web/packages/zeallot/index.html)
  - Provides packing and unpacking functionality similar to python’s
    `zip` and `unzip`

# I/O

- [unpivotr](https://cran.r-project.org/web/packages/unpivotr/index.html)
  - A very nice option for reading in Excel worksheets that are not
    designed to be machine readable
- [datapasta](https://github.com/MilesMcBain/datapasta)
  - A nice I/O library that helps get data into and out of R quickly!
    Best for quick requests where a reproducible process isn’t
    necessary - just up-front dev speed.

# Modeling

This section could conceivable take over the whole document, so I’m just
going to list a few things that are relevant to me right now.

- The [easystats](https://easystats.github.io/easystats/) ecosystem
  - Not a single package, but a collection of packages (like the
    tidyverse) that work together to help with statistical modeling. I
    would ideally like to lean on this more in the future.
- [marginaleffects](https://vincentarelbundock.github.io/marginaleffects/index.html)
  - A successor of sorts to the `emmeans` package.
- [ggeffects](https://github.com/strengejacke/ggeffects)
  - Lightweight `ggplot` extension for calculating and plotting marginal
    effects
- [modelsummary](https://vincentarelbundock.github.io/modelsummary/) is
  a cool package for reporting model results

## Survival analysis specific libraries

- [survival](https://cran.r-project.org/web/packages/survival/index.html)
  - The OG survival package - lots of excellent vignettes.
- [msm](https://cran.r-project.org/web/packages/msm/index.html)
  - Multi-state modeling package in R. Handles multi-state models with
    interval censoring (which `survival` doesn’t).
- `flexsurv`
- `ggsurvfit` provides ggplot visualizations for survival curves
- [condsurv](https://www.emilyzabor.com/condsurv/index.html)
  - is a quick way to calculate and plot conditional survival
- [contsurvplot](https://robindenz1.github.io/contsurvplot/)
  - is a useful package for visualizing the effect of continuous
    covariates on survival
