---
aliases: 
title: Confidence interval formula in R
created: 2023-09-13
updated: 2023-09-13
tags:
  - R
  - tidyverse
---
Here's a simple way to calculate 95% confidence intervals around a mean value.

```r 
data %>%
  summarise(
    mean = mean(outcome),
    sd = sd(outcome),
    n = n(),
    error = qnorm(0.975) * sd / sqrt(n),
    lower_ci = mean - error,
    upper_ci = mean + error)
    ```

