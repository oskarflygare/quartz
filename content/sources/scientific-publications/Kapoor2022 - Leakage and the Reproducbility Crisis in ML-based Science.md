---
created: 2022-09-07
updated: 2023-08-31
---
# Kapoor2022 - Leakage and the Reproducbility Crisis in ML-based Science

* Type: #article
* Date read: 2022-08-17
* Subject: [[machine learning]]
* Bibtex: @kapoor2022
* Bibliography: Kapoor, S., & Narayanan, A. (2022). _Leakage and the Reproducibility Crisis in ML-based Science_ (arXiv:2207.07048). arXiv. [https://doi.org/10.48550/arXiv.2207.07048](https://doi.org/10.48550/arXiv.2207.07048)
---
# Example citation

Inappropriate use of machine learning techniques results in reproducibility issues across scientific fields [@kapoor2022].

# Key takeaways
* The key issue is [[Data leakage]]
* The authors develop a checklist to check whether you have one of eight types of leakage.
	* BUT, this has zero value if there is not also computational reproducibility.
* Adjusting for leakage and other inappropriate statistics makes advantages over logistic regression disappear in many cases.
* No convergence on addressing these issues across fields.

---

# Main categories

## Lack of clean separation of training and test dataset

Test set needs to be separate during all pre-processing, modeling and evaluation steps. Otherwise the model has access to information in the test set before performance evaluation.

- No test set, textbook example of [[Overfitting]]
- Pre-processing on training and test set
- Feature selection on training and test set
- Duplicates in datasets

## Model uses features that are not legitimate

This can happen if a feature (predictor) is a proxy for the outcome. Use of drugs against hypertension to predict hypertension.

Which predictors are legitimate and should be used requires domain knowledge.

## Test set is not drawn from the distribution of scientific interest

Basically differences between the samples you use and the samples you want to predict.

- Temporal leakage
- Nonindependence between train and test samples
- Sampling bias in test distribution

# Notes

![[Screenshot 2022-08-17 at 10.16.57.png]]

> We say that ML-based science is suffering from a reproducibility crisis for two related reasons: First, our results show that reproducibility failures in ML-based science are systemic. In nearly every scientific field that has carried out a systematic study of reproducibility issues, papers are plagued by common pitfalls.

> Second, despite the urgency of addressing reproducibility failures, there are no systemic solutions that have been deployed for these failures.

## Conclusion

"The attractiveness of adopting ML methods in scientific research is in part due to the widespread availability of offthe-shelf tools to create models without expertise in ML methods (Hutson, 2019). However, this laissez faire approach leads to common pitfalls spreading to all scientific fields that use ML. So far, each research community has independently rediscovered these pitfalls. Without fundamental changes to research and reporting practices, we risk losing public trust owing to the severity and prevalence of the reproducibility crisis across disciplines. Our paper is a call for interdisciplinary efforts to address the crisis by developing and driving the adoption of best practices for ML-based science. Model info sheets for detecting and preventing leakage are a first step in that direction."