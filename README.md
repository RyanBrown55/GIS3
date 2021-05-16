
# Quick Map

<!-- badges: start -->
<!-- badges: end -->

The goal of Quick Map is to enable users to create choropleth maps of spatial data in seconds! Create on OGR object and call the quickmap function with you data frame, column of interest and identifier column. After doing so a leaflet choropleth map which uses quantiles for binning will be returned. One can then further optimize the map or analyze it as is.

This package was designed and refined entierly for Lab 7 in GIS III. It containts one function (quickMap) which is described above. The function is my own but is heavily influnced by this guide to leaflet: (https://learn.r-journalism.com/en/mapping/census_maps/census-maps/). 


The quickMap function has three arguments:

1) DataFrame: The spatial polygons data frame (an example of how to read such a data frame can be found in the Example section) 
2) TargetColumn: The variable that you would like to use to create your choropleth map / bin
3) LabelColumn: The variable that you would like to use to label areal units. 
 
## Installation

You can install the released version of quickMap from [CRAN](https://CRAN.R-project.org) with:

``` r
devtools::install_github("RyanBrown55/GIS3")
```

If you have errors with this please try the following:

``` r
install.packages("devtools")
devtools::install_github("RyanBrown55/GIS3")
```

## Example

This is a basic example which shows you how to use the quickMap function with a spatial polygons data frame. The nyc data can be found in this package repository and is intended to be used by those who are interested in refining their skills in EDA. The nyc data is from the GeoDa data center
(https://geodacenter.github.io/data-and-lab/) and pertains to demographic and rent characteristic of different NYC boroughs. 

``` r
library(quickMap)
df <- rgdal::readOGR("nyc.geojson")
quickMap(df,df$rent2005,df$name)
```

