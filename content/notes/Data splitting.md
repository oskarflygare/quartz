---
aliases: []
created: 2022-09-20
updated: 2023-09-01
---

# Data splitting
Date created: 2022-09-20

The primary approach to spending data efficiently. Most commonly splitting into train/test sets. 80/20 is a common split.

- Most of the time you are well off to just do a random split, some exceptions:
	- If there is large class imbalance (e.g., the outcome is very rare) you can stratify to ensure that it is allocated to both train/test splits.
	- In time-series data you typically use the most recent data as test


---
# References
* https://www.tmwr.org/splitting.html#splitting