---
aliases: 
title: Separate column by last underscore
created: 2023-10-06
updated: 2023-10-06
tags:
  - R
  - tidyverse
---
I never remember regex patterns, so here is a common one to separate a column by the last underscore in the name. It's handy to use when the column names contain information to be stored in a separate variable, for example time (\_PRE, \_POST, \_FU).

```r
separate(col, into = c("col1", "col2"), sep = "_(?=[^_]+$)")
```