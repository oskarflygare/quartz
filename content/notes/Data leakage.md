---
aliases: []
created: 2022-09-07
updated: 2023-09-01
---

# Data leakage
Date created: 2022-08-17

This is an issue in statistics, particularly machine learning, where training and testing data are not independent.

> when information from the data set a model learns on includes data that it is later evaluated on. If these are not entirely separate, the model has effectively already seen the answers, and its predictions seem much better than they really are.

Some things to look at:
- Temporality - does the training data precede testing data?
- Generalization - are conclusions drawn for the population where there is data?
- Inappropriate shortcuts (assuming pictures with cows always include grass)

---
# References
* [[Kapoor2022 - Leakage and the Reproducbility Crisis in ML-based Science]]