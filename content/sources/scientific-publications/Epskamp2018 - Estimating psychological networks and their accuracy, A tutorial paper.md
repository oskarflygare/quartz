---
created: 2022-09-07
updated: 2023-08-31
---
# Epskamp2018 - Estimating psychological networks and their accuracy, A tutorial paper

* Type: #article
* Date read: 2022-08-30
* Subject: [[network analysis]]
* Bibtex: @epskamp2018
* Bibliography: Epskamp, S., Borsboom, D., & Fried, E. I. (2018). Estimating psychological networks and their accuracy: A tutorial paper. _Behavior Research Methods_, _50_(1), 195–212. [https://doi.org/10.3758/s13428-017-0862-1](https://doi.org/10.3758/s13428-017-0862-1)
---
# Example citation


# Key takeaways
* Non-parametric bootstrap can be used to assess:
	* Accuracy of network estimation
	* Significance testing in edge-weight differences
	* Significance testing of centrality measures
* One issue with networks is that the number of parameters to estimate grows quickly with the size of the network.
	* [[Lasso regularization]] can be used to trim network edges.
* In their simulations, the statistical test of differences in edge-weights becomes stable at ~250 individuals.

---

# Abstract

The usage of psychological networks that conceptualize behavior as a complex interplay of psychological and other components has gained increasing popularity in various research fields. While prior publications have tackled the topics of estimating and interpreting such networks, little work has been conducted to check how accurate (i.e., prone to sampling variation) networks are estimated, and how stable (i.e., interpretation remains similar with less observations) inferences from the network structure (such as centrality indices) are. In this tutorial paper, we aim to introduce the reader to this field and tackle the problem of accuracy under sampling variation. We first introduce the current state-of-the-art of network estimation. Second, we provide a rationale why researchers should investigate the accuracy of psychological networks. Third, we describe how bootstrap routines can be used to (A) assess the accuracy of estimated network connections, (B) investigate the stability of centrality indices, and (C) test whether network connections and centrality estimates for different variables differ from each other. We introduce two novel statistical methods: for (B) the correlation stability coefficient,and for (C) the bootstrapped difference test for edge-weights and centrality indices. We conducted and present simulation studies to assess the performance of both methods. Finally, we developed the free R-package bootnet that allows for estimating psychological networks in a generalized framework in addition to the proposed bootstrap methods. We showcase bootnet in a tutorial, accompanied by R syntax, in which we analyze a dataset of 359 women with posttraumatic stress disorder available online.

![[Screenshot 2022-08-30 at 09.53.32.png]]