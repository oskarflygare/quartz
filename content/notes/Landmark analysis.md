---
aliases: []
created: 2022-09-07
updated: 2023-09-01
---

# Landmark analysis
Date created: 2021-11-02

Typically used in [[Survival analysis]] settings to overcome guarantee-time bias.

Landmark analysis is when you select a time point during follow-up and analyze only the subjects who have survived until then. Any subjects who were lost to follow-up or died prior to the landmark are excluded. You then classify response and apply the usual survival analysis methods.

## Choosing the landmark

- Late landmarks = smaller sample size & lower statistical power
- Early landmarks = late responders are misclassified as non-responders, low Sensitivity

Usually the landmark is picked from a clinically meaningful period, or you use multiple landmark times for sensitivity analyses.

---
# References
* [[Morgan2019 - Landmark analysis, A primer]]