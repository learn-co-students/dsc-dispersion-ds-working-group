
# Measures of Dispersion

## Introduction

Previously, you learned about three measures of central tendency: the mean, median, and mode. These metrics can give you a general understanding of where data values lie within the range of the whole dataset but they don't tell you the whole story. In fact, they can often be misleading!

To truly understand your data, you also need **Measures of Dispersion**, namely: absolute deviation, standard deviation, and variance. These measures tell you how tightly (or loosely) your data is clustered around its center. Generally, measures of dispersion report on how "noisy" your dataset is. 

In this lesson, you'll learn about the different measures of dispersion and explore how they are related to each other as well as other summary statistics.
 
## Objectives
You will be able to:

* Compare the different measures of dispersion
* Create a box plot and use it to interpret the spread of data


## Absolute Deviation

**Absolute Deviation** is the simplest way of calculating the dispersion of a data set. It is calculated by taking a value from the dataset and subtracting the mean of the dataset. This helps to identify the "distance" between a given value and the mean. In other words, how much a value *deviates* from the mean.  

> $ \left|x_i - \bar{x}\right|$

Here $x_i$ denotes an element from $[x_1, x_2, .., x_n]$ , where $n$ is the total number of data points in the dataset. Recall, the symbol $\bar{x}$ (pronounced "x-bar") represents the sample mean. The vertical bars are used to denote absolute value so all absolute deviation values are positive. This is important because when measuring deviation, you just want to focus on how big the difference is, not its sign.

If that sounded a little confusing, consider this example: Say the mean test score for a group of 100 students is 58.75 out of 100. If a particular student scored 60 out of 100, the absolute deviation of that score from the mean is:

> $ \left|60 - 58.75\right| = 1.25 $ 

**Average Absolute Deviation** is calculated by taking the mean of all individual absolute deviations in a data set as shown in the formula below:

$$\large \dfrac{1}{n}\sum^n_{i=1}\left|(x_i-\bar x)\right| $$

The advantage here is that the average absolute deviation yields one number to describe dispersion. To illustrate this, consider this example: In a group of four people, two people earn 50K USD a year and two earn 60K USD a year. The mean of the data set is 55K USD. The absolute deviations are:

> $ \left|50 - 55\right| = 5 $   
> $ \left|50 - 55\right| = 5 $   
> $ \left|60 - 55\right| = 5 $     
> $ \left|60 - 55\right| = 5 $     

The average absolute deviation is:

> $ \large \frac{5+5+5+5}{4} = 5 $

## Variance

A more complex measure of dispersion is **Variance**. Remember, measures of dispersion emphasize the magnitude of differences from the mean, not their sign. Unlike the absolute deviation, which uses the absolute value of the deviation to take care of negative values, the variance achieves positive values by *squaring* each of the deviations. Similar to what you saw with the average absolute deviation, the next step in calculating variance is to add up the squared deviations (the **sum of squares**), then divide by the total number of values in your dataset. 

OK, that was a mouthful but you can break it down mathematically as follows:

$$ \large \sigma^2 = \dfrac{1}{n}\displaystyle\sum^n_{i=1}(x_i-\mu)^2 $$

> Recall the distinction between the sample mean ($\bar{x}$) and the population mean ($\mu$) - namely, that a sample mean is calculated using a subset of the population whereas the population mean is calculated using the entire population. You'll see here that the population mean is used. This is because unlike the mean, the variance formula changes slightly depending on whether you are working with data from a sample or data from the entire population. Don't worry if this is a little confusing now, the details will be discussed later. 

Say you want to calculate the variance of our salary data above. The first step is to calculate all of the differences from the mean:

> $ 50 - 55 = -5 $   
> $ 50 - 55 = -5 $   
> $ 60 - 55 = 5 $     
> $ 60 - 55 = 5 $  

*Note: no absolute values, the signs are kept*

Next, square the differences:

> $ (-5)^2 = 25 $   
> $ (-5)^2 = 25 $   
> $ 5^2 = 25 $     
> $ 5^2 = 25 $

Finally, add them up and divide by the total number of data points:

> $ \large \frac{25+25+25+25}{4} = 25 $

As a measure of dispersion, the variance is very useful. If the values in the data set are spread out about their mean, the variance will be a large number. On the other hand, if the values are clustered closely around their mean, the variance will be a much smaller number. 

There are, however, two potential problems with the variance. First, because the deviations of values from the mean are squared, this gives more weight to extreme values. Outliers, which differ substantially more from the mean than the rest of the data in a data set, will impact the variance. Secondly, the variance is not in the same *units* as the individual values in a data set. Variance is measured in the *units squared*. This means we cannot directly relate a variance value to the values in our data set. If this isn't clear, go back to the salary example above. The salaries are measured in USD but the variance is measured in *USD squared* which is not the same thing.

Fortunately, calculating the standard deviation rather than the variance fixes this problem. 

## Standard Deviation

The **Standard Deviation** is another measure of the spread of values within a dataset. 
It is simply the square root of the variance. In the above formula, $\sigma^2$ is the variance so $\sigma$ is the standard deviation. 

$$ \large \sigma = \sqrt{\dfrac{1}{n}\displaystyle\sum^n_{i=1}(x_i-\mu)^2} $$

So for the salary example above, you can calculate:

> $ \sigma = \sqrt{\sigma^2} = \sqrt{25} = 5 $

Now, the units are in USD again!

## Quantiles, Percentiles, and Quartiles

**Quantiles** are points in a distribution that relate to the *rank order* of values in that distribution. Rank ordering just means the data are sorted in ascending order. You can find any quantile by sorting the sample. The middle value of the sorted sample (middle quantile, 50th percentile) is known as the **median**. The **limits** are the **minimum** and **maximum** values. Any other locations between these points can be described in terms of **percentiles**.

Percentiles are descriptions of quantiles relative to 100. So the 80th percentile is 80% of the way up an ascending list of sorted values of data. For example, take a look at the image below: 80% of people in the data set are shorter than you so you are in the 80th percentile for height. 

<img src="./images/new_percent.png" width="600">


## InterQuartile Range - IQR
The **quartiles** of a dataset divide the data into **four** equal parts. Since there are four equal parts, there are 3 quartile positions that divide them. These are denoted by Q1, Q2, and Q3. The second quartile position, Q2, is the median of the dataset, which divides the dataset in half. Q1 divides the lower half and is known as the "lower quartile". Similarly, Q3 divides the upper half and is known as the "upper quartile". The image below illustrates how this looks:

<img src="images/new_measuresofdispersion2.png" width="600">

The **InterQuartile Range (IQR)** is a measure of where the “middle fifty” is in a dataset which is given by $ Q3 - Q1 $. This is useful because it tells you where the bulk of the values lie. To relate these concepts back to percentiles, Q1 is the 25th percentile and Q3 is the 75th percentile. The IQR is calculated by subtracting the 25th percentile from the 75th percentile. In the image above, the IQR is 18. 



Great, that's enough for now. Let's move on to a quiz!

## Summary

In this lesson, you learned about some commonly used measures of dispersion. These measures identify the spread or deviation present in a dataset. You also looked at quantiles, percentiles, quartiles, and IQR as well. You will revisit these topics continuously throughout the bootcamp and will see how these concepts are used toward effective data analysis. 
