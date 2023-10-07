---
aliases: 
title: Remove multiple string patterns using stringr
created: 2023-10-06
updated: 2023-10-07
tags:
  - R
  - tidyverse
---
A common task during data cleaning is to remove unnecessary fluff from variables, column names or other strings.

Here is an easy way to do it using the *stringr* package.

```r

# define strings to be removed
string_remove <- c("one", "two")

# remove strings in a variable
# this will search for everything in string_remove and remove all matches
df %>%
	mutate(variable = str_remove_all(variable, paste(string_remove, collapse = "|")))

```

If you want to remove strings from the column names, do this:

```r
colnames(df) = str_remove_all(colnames(df), paste(string_remove, collapse = "|"))
```