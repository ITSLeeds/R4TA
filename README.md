
Welcome to R for Transport Applications.

Comments and links from the course.

Notes from day 1
----------------

``` r
# demonstration of key.pos
library(sf)
```

    ## Linking to GEOS 3.5.1, GDAL 2.2.2, proj.4 4.9.2

``` r
library(spData)
plot(world["pop"])
```

![](README_files/figure-markdown_github/unnamed-chunk-1-1.png)

``` r
plot(world["pop"], key.pos = 3)
```

![](README_files/figure-markdown_github/unnamed-chunk-1-2.png)

``` r
# for more info see:
# https://cran.r-project.org/web/packages/sf/vignettes/sf5.html
# vignette("sf")
?sf::plot
```

Demonstration of sfc to sf conversion:

``` r
asia = world[world$continent == "Asia", ]
asia = st_union(asia)
class(asia)
```

    ## [1] "sfc_MULTIPOLYGON" "sfc"

``` r
asia_df = st_sf(
  data.frame(name = "asia"),
  geometry = asia
  )
class(asia_df)
```

    ## [1] "sf"         "data.frame"
