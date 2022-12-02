Bootstrapping
================
Lectured by Jeff Goldsmith
2022-11-17

``` r
knitr::opts_chunk$set(warning = FALSE, message = FALSE)

library(tidyverse)
```

    ## ── Attaching packages ─────────────────────────────────────── tidyverse 1.3.2 ──
    ## ✔ ggplot2 3.3.6     ✔ purrr   0.3.4
    ## ✔ tibble  3.1.8     ✔ dplyr   1.0.9
    ## ✔ tidyr   1.2.1     ✔ stringr 1.4.1
    ## ✔ readr   2.1.2     ✔ forcats 0.5.2
    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()

``` r
library(p8105.datasets)
```

### Bootstrapping

The idea of bootstrapping is to mimic repeated sampling with the one
sample we have. Our sample is randomly drawn from the population of
interest:  
- We would like to draw more samples, but we can’t do that in real
life.  
- So we draw a “*bootstrap sample*” from the one sample we have.  
- The bootstrap sample has the same size as the original sample, and is
drawn with replacement.  
- Analyze this sample using whatever approach we want to apply.  
- Repeat.

**Why bootstrap?**

The repeated sampling framework often provides useful theoretical
results under certain assumptions and/or asymptotics (like a limiting
behavior):  
- *Sample means*, *regression coefficients*, *odds ratios* follow a
known distribution.

If the assumptions are not met, or the sample size is not large enough,
we can’t use the “known distribution”. Bootstrapping gives us repeated
sampling, and uses an empirical rather than a theoretical distribution
for our statistic of interest.