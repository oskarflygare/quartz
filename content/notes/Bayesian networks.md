---
aliases: []
created: 2022-09-07
updated: 2023-09-01
---

# Bayesian networks
Date created: 2021-11-12

These networks produce [[directed acyclic graphs]]. You get both direction and % of bootstrap samples where the edge appeared. Resampling of the network.

"Treating a symptom that appears in the DAG should turn off activation in its descendant symptoms".

R package *bnlearn*.

![[Screenshot 2021-11-12 at 15.16.18.png]]

> Leaders in the field of causal inference and Bayesian network analysis agree that correlation (alone) does not signify causation. Nevertheless, they argue that under a certain set of assumptions one can reasonably make causal inferences from correlational, observational data (e.g., Pearl, 2011). First, there cannot be any unobserved variables influencing those in the network. That is, if there is another variable (e.g., unmeasured symptom of another disorder) that produces a strong causal effect on symptoms modeled by the DAG, then spurious associations between symptoms will be wrongly be interpreted as causal connections. Second, the causal Markov assumption must be met. That is, given its causes, each symptom must be independent of its direct and indirect non-effects. Third, certain assumptions about the probability distribution of each symptom must be met. Fourth, sometimes it is difficult to identify the single best causal Bayesian network. Sometimes computation returns several plausible causal DAGs, especially when the number of subjects is relatively small. Sometimes the direction of the edges varies among these DAGs.

## Limitations

Causal relations unfold over different time scales (seconds for panic attacks, weeks for response to medication), but the methodology assumes all of these effects are instant.

They prohibit "looping" effects where there is a causal cycle, like the CBT models for panic or OCD.

---
# References
* [[McNally2016 - Can network analysis transform psychopathology]]