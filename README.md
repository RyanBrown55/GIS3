
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
(https://geodacenter.github.io/data-and-lab/) and pertains to demographic and rent characteristic of different NYC subboroughs. 

``` r
library(quickMap)
df <- rgdal::readOGR("nyc.geojson")
quickMap(df,df$rent2005,df$name)
```

## Data

As previously mentioned attached New York City (nyc.geojson) data pertains to demographic and rent characteristic of different NYC subboroughs from 2002 - 2009. 

Here is a break down of the dataset from its source (https://geodacenter.github.io/data-and-lab/nyc/):


Observations = 55
Variables = 34
Years = 1990-2009


Variable 	    |                 Description	                                    | Source	 
code	         | NYC Sub-Borough Neighborhood unique ID	 	                       | NA
subborough	   | NYC Sub-Borough Neighborhood name	 	                            | NA
forhis06-09   | Percentage of hispanic population, not born in US	New York City | Neighborhood Information by Furman Center Terms can be found at Furman Center.	 
forwh06-09	   | Percentage of white population, not born in US                  |	same as above	 
hhsiz1990	    | Average number of people per household	United States Census 2000| New York City Housing and Vacancy Survey.	 
hhsiz00	      | Average number of people per household	                         | see above	 
hhsiz02-05-08 |	Average number of people per household	                         | see above	 
kids2000 -2009| Percentage households w kids under 18	United States Census 2000 | American Community Survey.	 
rent2002,2005,2008 |	Median monthly contract rent	                              | New York City Housing and Vacancy Survey	 
rentpct02,05,08	| Percentage of housing stock that is market rate rental units  |	New York City Housing and Vacancy Survey.	 
pubast90,00 |	Percentage of households receiving public assistance.             |	United States Census	 
yrhom02,05,08 |	Average number of years living in current residence	            | New York City Housing and Vacancy Survey.

