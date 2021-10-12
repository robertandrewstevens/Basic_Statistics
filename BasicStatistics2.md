Basic Statistics 2
================
Robert A. Stevens
2021-10-12

## Normal Distribution

![](BasicStatistics2_files/figure-gfm/unnamed-chunk-1-1.png)<!-- -->

The Normal distribution is the most widely used distribution in
Statistics, because it fits data for many natural phenomenon: physical,
mechanical, electrical, chemical, etc. Here are just a few applications:

-   Capacity variation of electrical condensers

-   Tensile strength of aluminum alloy sheet

-   Monthly temperature variation

-   Penetration depth of steel specimens

-   Rivet-head diameters

-   Electrical power consumption in a given area

-   Electrical resistance

-   Gas molecules velocities

-   Wear

-   Noise generator output voltage

-   Wind velocity

-   Hardness

-   Chamber pressure from firing ammunition

## Probability Density Function (PDF)

![Figure 1. Normal PDF](normalpdf.png)

*μ* = Mean

*σ* = Standard Deviation

The normal distribution is defined by its Probability Density Function
(PDF). Think of this as the probability of a variable being equal to a
specific value. It’s actually more complicated than that, but don’t
worry about it.

Warnings:

-   Symmetric

-   \-∞ &lt; Values &lt; +∞

![](BasicStatistics2_files/figure-gfm/unnamed-chunk-2-1.png)<!-- -->

Here are 3 Normal distributions with the same mean (10), but different
standard deviations (sd = 1, 2 and 3).

If you were producing a part that had a target value of 10, which
distribution would you rather have?

For this distribution, if you wanted to outsource it and had to give
tolerances to a supplier, where would you set them?

## Example: Battery Life Data

40 observations of battery lives (years)

``` r
life <- c(2.2, 4.1, 3.5, 4.5, 3.2, 3.7, 3.0, 2.6,
          3.4, 1.6, 3.1, 3.3, 3.8, 3.1, 4.7, 3.7,
          2.5, 4.3, 3.4, 3.6, 2.9, 3.3, 3.9, 3.1,
          3.3, 3.1, 3.7, 4.4, 3.2, 4.1, 1.9, 3.4,
          4.7, 3.8, 3.2, 2.6, 3.9, 3.0, 4.2, 3.5)
mean(life)
```

    ## [1] 3.4125

``` r
sd(life)
```

    ## [1] 0.7028103

Mean *μ* = 3.4 years

Standard Deviation *σ* = 0.7 years

![Figure 2. Battery PDF](batterypdf.png)

Probability Density Function Plot for mean = 3.4 years and standard
deviation = 0.7 years.

``` r
x <- seq(1, 6, length = 1000)
y <- dnorm(x, mean = mean(life), sd = sd(life))
par(xaxs = "i", yaxs = "i")
plot(x, y, type = "l", lwd = 2, xlab = "Battery Life (years)", ylab = "Density", 
     main = "Battery Life PDF")
abline(v = mean(life))
```

![](BasicStatistics2_files/figure-gfm/unnamed-chunk-4-1.png)<!-- -->

## Cumulative Distribution Function (CDF)

![Figure 3. Normal CDF](normalCDF.png)

For a continuous random variable, the probability that it is exactly
equal to a specific value is infinitesimal.

It’s easier to find the probability that it is less than or equal to a
specific value.

CDF = Probability that a random variable (X) is less than or equal to a
specific value (x), i.e., the area under the PDF curve to the left of
the value.

``` r
x <- seq(1, 6, length = 1000)
y <- pnorm(x, mean = mean(life), sd = sd(life))
par(xaxs = "i", yaxs = "i")
plot(x, y, type = "l", lwd = 2, xlab = "Battery Life (years)", ylab = "CDF", 
     main = "Battery Life CDF")
abline(v = mean(life))
abline(h = 0.5)
```

![](BasicStatistics2_files/figure-gfm/unnamed-chunk-5-1.png)<!-- -->

Here is the CDF plot for the battery life data distribution.

The value of the integral from 0 to X is plotted for all values of X in
the range from 1 to 6.
