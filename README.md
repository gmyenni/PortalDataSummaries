
<!-- README.md is generated from README.Rmd. Please edit that file -->

# portalr

[![Build
Status](https://travis-ci.org/weecology/portalr.svg?branch=master)](https://travis-ci.org/weecology/portalr)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](https://raw.githubusercontent.com/weecology/portalr/master/LICENSE)

<img src="man/figures/portalr.png" width="200px">

## Overview

The **portalr** package provides collection of basic functions to
summarize the Portal porject data on rodents, plants, ants, and weather
at our long-term field site in the Chihuahuan Desert. The data begin in
1977 and are continuously updated today. There are functions to
summarize rodent abundance, biomass, or energy and by site, plot, or
treatment type. There are functions to summarize the weather data
collected from our automated weather stations and plant data that is
collected each summer and fall.

## Installation

You can install portalr from github with:

``` r
# install.packages("devtools")
devtools::install_github("weecology/portalr")
```

## Examples

1.  Load all data tables from the [PortalData GitHub
    repo](https://github.com/weecology/portalData):

<!-- end list -->

``` r
data_tables <- load_data("repo")
```

2.  Download and generate summaries of rodent abundance and biomass:

<!-- end list -->

``` r
download_observations(".")

rodent_data <- abundance(".") # default grouping is by sampling period

rodent_biomass_by_plot <- biomass(".", level = "plot", type = "granivores", 
shape = "flat", time = "date")
```

3.  Retrieve weather data:

<!-- end list -->

``` r
weatherdata <- weather("Monthly", ".")
```

For more detailed info, checkout the vignettes associated with the
package:

``` r
browseVignettes("portalr")
```

## More Information

#### [Portal Data Repo](github.com/weecology/PortalData)

The data repo contains useful details for issues with data collection,
and background on why we handle them the way we do. Of course, it also
contains the raw data, if you would like to create more complex data
summaries than what is provided here.

#### [The Portal Project](portal.weecology.org/)

Find a list of previous publications using the Portal data at our
website.

#### [The Portal Blog](portalproject.wordpress.com/)

Follow our blog to get the latest news on what is happening with our
project and at the site.
