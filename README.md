
<!-- badges: start -->

[![CRAN
status](https://www.r-pkg.org/badges/version/bslib)](https://cran.r-project.org/package=bslib)
[![Lifecycle:
experimental](https://img.shields.io/badge/lifecycle-experimental-orange.svg)](https://www.tidyverse.org/lifecycle/#experimental)
[![R build
status](https://github.com/rstudio/bslib/workflows/R-CMD-check/badge.svg)](https://github.com/rstudio/bslib/actions)

<!-- badges: end -->

# bslib

The `bslib` R package provides tools for customizing [Bootstrap
themes](https://getbootstrap.com/docs/4.6/getting-started/theming/)
directly from R, making it much easier to customize the appearance of
[Shiny](https://shiny.rstudio.com/) apps & [R
Markdown](https://rmarkdown.rstudio.com/) documents. `bslib`’s primary
goals are:

  - Make [custom
    theming](https://rstudio.github.io/bslib/articles/bslib.html#custom)
    as easy as possible.
      - Custom themes may even be created interactively in
        [real-time](https://rstudio.github.io/bslib/articles/bslib.html#real-time).
  - Also provide easy access to pre-packaged [Bootswatch
    themes](https://rstudio.github.io/bslib/articles/bslib.html#bootswatch).
  - Make [upgrading from Bootstrap 3 to 4 (and
    beyond)](https://rstudio.github.io/bslib/articles/bslib.html#versions)
    as seamless as possible.
      - Shiny and R Markdown default to Bootstrap 3 and will continue to
        do so to avoid breaking legacy code.
  - Serve as a general foundation for Shiny and R Markdown extension
    packages such as `{flexdashboard}`, `{pkgdown}`, `{bookdown}`, etc.

## Installation

Install the stable release of `bslib` on CRAN:

``` r
install.packages("bslib")
```

Usage with Shiny requires version 1.6 or higher:

``` r
install.packages("shiny")
```

Usage with R Markdown requires version 2.7 or higher:

``` r
install.packages("rmarkdown")
```

## Basic usage

`bslib` is designed for use with any Shiny or R Markdown project that
uses Bootstrap. In most cases, you can identify a project that uses
Bootstrap when the relevant page constructor has a `theme` parameter.
For example, most Shiny page layout functions (e.g.,
`shiny::navbarPage()`) and some popular R Markdown formats (e.g.,
`rmarkdown::html_document`) all have a `theme` parameter.

To use `bslib` in Shiny, provide a `bs_theme()` *object* to the `theme`
parameter; and in R Markdown, provide `bs_theme()` *parameters* to
`theme`. For example, here’s a way to upgrade Shiny and R Markdown from
Bootstrap 3 to 4:

<div style="display:flex; justify-content:space-between">

<div style="flex:1">

``` r
library(shiny)
ui <- navbarPage(
  theme = bs_theme(version = 4),
  ...
)
shinyApp(ui, function(...) {})
```

</div>

<div style="flex:1">

``` r
---
output:
  html_document:
    theme:
      version: 4
---
```

</div>

</div>

See the [Get
Started](https://rstudio.github.io/bslib/articles/bslib.html) article to
learn more about Bootstrap versions, pre-packaged Bootswatch themes,
(real-time) custom theming, and more.

To get started more quickly, choose a relevant R Markdown template from
inside RStudio by going to File -\> New File -\> R Markdown -\> From
Template:

<img src="man/figures/rstudio-templates.png" width="60%" style="display: block; margin: auto;" />

## Getting help

There are two main places to get help with `bslib`:

  - The [RStudio
    community](https://community.rstudio.com/tags/c/R-Markdown/10/bslib)
    is a friendly place to ask any questions about flexdashboard. Be
    sure to use the `bslib` tag. Add also the `shiny` tag is you are
    using a Shiny runtime.

  - [Stack Overflow](https://stackoverflow.com/questions/tagged/bslib)
    is a great source of answers to common `bslib` questions. It is also
    a great place to get help, once you have created a reproducible
    example that illustrates your problem. Use the tags
    [`[r][bslib]`](https://stackoverflow.com/questions/tagged/bslib+r)
    if you ask a question. Add the tag `[bslib]` if you are using a
    Shiny runtime.

## Code of Conduct

Please note that the bslib project is released with a [Contributor Code
of
Conduct](https://github.com/rstudio/bslib/blob/master/CODE_OF_CONDUCT.md).
By contributing to this project, you agree to abide by its terms.
