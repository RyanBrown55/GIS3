
# quickMap

<!-- badges: start -->
<!-- badges: end -->

The goal of quickMap is to enable users to create choropleth maps of spatial data in seconds! Create on OGR object and call the quickmap function with you data frame, column of interest and identifier column. After doing so a leaflet map using quantiles will be returned. One can then further optimize the map or analyze it as is.

## Installation

You can install the released version of quickMap from [CRAN](https://CRAN.R-project.org) with:

``` r
devtools::install_github("RyanBrown55/GIS3")
```

## Example

This is a basic example which shows you how to use the quick map function with a spatial polygons data frame. 

``` r
library(quickMap)
df <- rgdal::readOGR("nyc.geojson")
quickMap(df,df$rent2005,df$name)
```

