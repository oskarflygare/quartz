---
aliases:
  - Node predictability
created: 2022-12-20
updated: 2023-09-01
---

# Network/Node predictability
Date created: 2022-12-20

Predictability is a technique used in [[network analysis]] where each node is predicted by all the others. You then calculate the explained variance R<sup>2</sup> for each node in the network. This is a Bayesian R<sup>2</sup> because so far I have only seen it applied using the ```BGGM``` package which uses Bayesian Gaussian Graphical Models. 

One measure of node centrality is predictability, i.e. how much of the variance of a node that is explained by all other nodes in the network. Predictability in the BGGM framework is estimated using Bayesian R<sup>2</sup> with 95% credible intervals from the posterior distribution.

---
# References
* Williams, D. R. (2021). Bayesian Estimation for Gaussian Graphical Models: Structure Learning, Predictability, and Network Comparisons. _Multivariate Behavioral Research_, _56_(2), 336–352. [https://doi.org/10.1080/00273171.2021.1894412](https://doi.org/10.1080/00273171.2021.1894412)