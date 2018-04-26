
Welcome to R for Transport Applications.

Comments, slide and links from the course can be found here.

Links
-----

-   [Gecomputation with R](http://geocompr.robinlovelace.net/) (Lovelace, Nowosad, and Muenchow 2018)
-   [R for Data Science](http://r4ds.had.co.nz/) (Grolemund and Wickham 2016)
-   [Efficient R Programming](https://csgillespie.github.io/efficientR/) (Gillespie and Lovelace 2016)
-   [sf](https://cran.r-project.org/web/packages/sf/vignettes/) package vignettes (see also `vignette(package = "sf")`)
-   [dodgr website](https://atfutures.github.io/dodgr/) (contains vignettes)
-   [tutorial by Mark Padgham](https://github.com/mpadge/r4trans-april18/blob/master/bristol.Rmd)

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

References
----------

Gillespie, Colin, and Robin Lovelace. 2016. *Efficient R Programming: A Practical Guide to Smarter Programming*. O’Reilly Media. <https://csgillespie.github.io/efficientR/>.

Grolemund, Garrett, and Hadley Wickham. 2016. *R for Data Science*. 1 edition. O’Reilly Media.

Lovelace, Robin, Jakub Nowosad, and Jannes Muenchow. 2018. *Geocomputation with R*.
