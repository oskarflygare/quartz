---
created: 2023-02-15
updated: 2023-09-01
---
* Type: #article
* Date read: 2023-02-15
* Subject: [[Suicide]] [[ecological momentary assessment]]
* Bibtex: @kleiman2018
* Bibliography: Kleiman, E. M., Turner, B. J., Fedor, S., Beale, E. E., Picard, R. W., Huffman, J. C., & Nock, M. K. (2018). Digital phenotyping of suicidal thoughts. _Depression and Anxiety_, _35_(7), 601–608. [https://doi.org/10.1002/da.22730](https://doi.org/10.1002/da.22730)
---
# Example citation

[[The mean level and variability of suicidal ideation identified subgroups of individuals with a previous suicide attempt]]

# Key takeaways
* The data is the same as in [[Kleiman2017 - Examination of Real-Time Fluctuations in Suicidal Ideation and Its Risk Factors, Results From Two Ecological Momentary Assessment Studies]]
* Their aim was to find distinct phenotypes of suicidal thinking. They used latent profile analysis.
	* frequency/intensity/variability
* Here again they used the RMSSD technique to get within-individual variability. Also:
	* Mean scores over time
	* Within-person SD
	* Maximum score
	* Percent of prompts with a non-zero score on suicidal thoughts
	* RMSSD
* After getting the profiles they checked group differences using ANOVA or chi2 for suicide history variables
* Groups:
	* 1 - low mean, low variability
	* 2 - low mean, moderate variability
	* 3 - moderate mean, high variability
	* 4- high mean, low variability
	* 5 - high mean, high variability

---

They did analyses in MPlus but there's an R package called [tidyLPA](https://cran.r-project.org/web/packages/tidyLPA/vignettes/Introduction_to_tidyLPA.html)

![[Screenshot 2023-02-15 at 10.11.31.png]]