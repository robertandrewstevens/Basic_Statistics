Estimation of Parameters
================
Robert A. Stevens
2021-10-13

## Outline

-   Measures of central tendency and variability

-   Histograms

-   Normal probability plots

-   Box plots

## Measures of Central Tendency

Sample of 15 of the 40 battery life data values.

Mean (a.k.a. Average): Sum of Observations/Number of Observations = 3.33

Median: Middle number: 50th Percentile (If even number of observations,
take average of two middle values) = 3.40

Mode: Most common value (if a tie occurs, Excel picks the lowest;
Statistica doesn’t report anything) = 3.10

## Measures of Variability

The same sample of 15 of the 40 battery life data values.

Variance: sum\[(Value - Mean)^2\]/(n - 1) = 0.63

Standard Deviation: Square Root of Variance = 0.80

Range: Maximum Value - Minimum Value = 3.10

Why do we use Standard Deviation instead of Variance? Units are the same
as the measurement scale.

### Statistica Analysis

Statistics &gt; Basic Statistics/Tables &gt; Descriptive Statistics

Mean = 3.33

Median = 3.40

Mode = “Multiple” and “Frequency of Mode” is blank, because there are
two values (3.1 and 3.4) that occur twice in the sample.

Variance = 0.63

Std. Dev. = 0.80

Range = 3.10

## Exercise 3-1

-   Analyze Belt Life data
    -   Mean
    -   Median
    -   Standard Deviation
    -   Variance
    -   Range

Data is located in “Basic Statistics.xls” tab “Belt A”

## “You can observe a lot by watching”

\[<http://www.yogi-berra.com/yogiisms.html>\]

Before we go any further, we should look at the data.

Simply “plugging and chugging” can be very dangerous.

If the the normal distribution doesn’t fit the data well, then the
statistics we calculate (mean and standard deviation), and the estimates
we derive from them, are useless (i.e., WRONG).

## Histograms

Graphs &gt; Histograms (Advanced tab with “Fit type:” equal to “Off”)

-   What: A bar graph display of the distribution of measurement data of
    a product or process

-   Why: Determine the shape of a distribution

    -   Whether the “spread” of the data falls within specifications,
        and, if not, how much falls outside
    -   Whether the data is centered at the right place - are there too
        many items on the “high” or “low” side?

-   When:

    -   Need to identify the distribution in order to apply the proper
        statistical tools
    -   Need to show process capability graphically

-   How:

    -   Count the number of data points in the data set
    -   Determine the range R for the entire data set
    -   Divide the range value into a certain number of classes,
        referred to as K
    -   Determine the class width (R/K)
    -   Determine the class boundary or end points
    -   Construct a frequency table based on the values computed above
    -   Construct a bar graph based on the frequency table

Statistics &gt; Descriptive Statistics – Quick tab &gt; Histograms

Histogram with PDF superimposed.

Can use either:

Statistics &gt; Descriptive Statistics – Quick or Normality tabs

or

Graphs &gt; Histograms – Advanced tab (slightly different appearance)

## Normal probability plots

-   What: A 2-dimensional plot of a data set versus its corresponding
    percentile

-   Why:

    -   Identify the data’s distribution
        -   Histograms can be misleading, especially if sample size is
            small
    -   Estimate the distribution’s parameters

-   When:

    -   Need to identify the distribution in order to apply the proper
        statistical tools
    -   Need to assess fit of a distribution
    -   Need to check model assumptions

-   How:

    -   Sort data from lowest (1) to highest (n) and assign numbers i =
        1…n
    -   Calculate Percentile: p(i)

## Battery Life Data Percentiles

Statisica has 4 methods to determine ranks.

This is important when there are ties in the data set.

For the Normal Probability Plot, the “mean” ranking method is used,
i.e., take the mean of the order (i) of the tied data.

Then Statistica uses the empirical percentile formula:

    p(i) = [3(Rank) – 1]/[3(n)]

If we plotted X (Life) versus Y1 (Percentile), we get a “S” shaped curve
like the one above. We want to “linearize” this with a transformation.

Inverse Normal CDF plot: *N*<sup> − 1</sup>(*p*)

Normal Probability Plot:

-   How - continued:
    -   Transform Percentile using inverse of the Standard Normal
        Cumulative Distribution Function
    -   Plot data point versus transformed Percentile
    -   If data falls along a straight line, use the normal distribution
        and estimate parameters, e.g. mean, median, and standard
        deviation \[show how with linear regression - advanced topic\]

### Standard Normal CDF Notation

Value (x) -&gt; *N*(*x*) -&gt; Probability (p)

Probability (p) -&gt; *N*<sup> − 1</sup>*p*(*i*) -&gt; Value (x)

“Linearize” Y1 to Y2 using inverse Normal CDF:
*N*<sup> − 1</sup>*p*(*i*).

If you want to do this yourself, the name of the Normal CDF function is
“INORMAL” for the integral of the Normal distribution, and the inverse
of the Normal CDF is “VNORMAL” (I don’t know what the “V” stands for).

*N*(*x*): INORMAL(x, 0, 1)

*N*<sup> − 1</sup>*p*(*i*): VNORMAL(p, 0, 1)

## Statistica

Statistica’s Probability Distribution Calculator gives an idea of what’s
going on.

If you plug in an “X” value, you get a “p” value, and the inverse box is
not checked.

If you plug in a “p” value, you get an “X” value, and the inverse box is
checked.

These are important concepts that you will use throughout the rest of
the course.

## Battery Life Data Transformed Percentiles

Apply the inverse Normal CDF to the percentile data, Y1, to get
*N*<sup> − 1</sup>*p*(*i*), i.e., Y2.

Now plot Y2 versus X.

Points falling along a straight line implies the normal distribution
works for this data set.

You can also find the mean and distances from the mean by projecting
from the Y-axis to the X-axis.

## Box plots

Statistics &gt; Descriptive Statistics – Quick tab &gt; Box & whisker
plot for all variables

This default (?) version gives the:

-   Mean

-   Mean +/- 1\*(std. dev.) = Top and bottom of box

-   Mean +/- 1.96\*(std. dev.) = Whiskers on box

    -   This is a pseudo confidence interval (sample size and Normality
        issues?).

There are 3 more versions available in Statistica and many variations
are possible.

The Options tab “Options for Box-Whisker plots” section lets you change
the type of box plot.

Try them all and compare.

Also, you could have used:

Graphs &gt; 2D Graphs &gt; Box Plots

to get different versions these and modify them.

## Exercise 3-2

For the data in “Basic Statistics.xls” tab “Belt A”, create a histogram
with superimposed PDF, Normal probability plot, and box plot.

Is the normal distribution appropriate for this data set?

## Mean or Standard Deviation Concern?

Review: Do you know how to use Statistica to:

-   Estimate the statistics for the Normal distribution?

    -   Mean
    -   Variance or Standard Deviation

-   Make a histogram?

-   Make a Normal probability plot?

-   Make a box plot?
