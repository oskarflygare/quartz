---
created: 2022-09-07
updated: 2023-08-31
---
# What the Future Holds - Machine Learning Predicts Successful Psychotherapy
* Type: #article
* Year read: #read2021
* Subject:  [[machine learning]] [[prediction]]
* Bibtex: @author2021
* Bibliography: (peer-review assignment)
---
## Why and when I was reading this
I did a peer review for Behavior Research and Therapy

# Peer review report BRAT-D-21-00434
Manuscript title: *What the Future Holds: Machine Learning Predicts Successful Psychotherapy*

Manuscript number: **BRAT-D-21-00434**

Reviewer: Oskar Flygare, Karolinska Institutet
 
## Summary

The authors developed and evaluated machine-learning models to predict clinically significant change after psychotherapy in a relatively large sample of patients in routine care. The best performing model was a gradient boosting machine (GBM) which achieved a balanced accuracy of 69% in test data.

The strengths of this study includes the use of generalizable data routinely collected in a health care setting, the real-world sampling of both patients and therapists, as well as rigorous and state-of-the-art preprocessing techniques in their model development pipeline. This study is a significant contribution to the growing field of machine learning prediction in clinical psychology and psychiatry.

However, the prediction accuracy is relatively low and the authors are too quick to dismiss other potential strategies (e.g., clinician-rated assessments, disorder-specific prediction). These points and other issues are listed below.
  
## Major issues
1. Since this is a methodologically complex paper, my ability to assess the veracity of the findings is severely limited by not having access to the statistical scripts used. Even if the underlying data contains sensitive information that cannot be shared, I highly recommend that the authors share their analytical code somewhere so that myself and others can review the methods and techniques used. There are several services such as figshare, Open Science Framework, Github, Dryad, etc.
2. The authors discuss the strengths of machine learning models on page 4. I agree with the strengths but the drawbacks should be mentioned as well, for example lack of interpretability. I believe the authors are aware of this since they perform logistic regression to find associations of specific predictors, but this should be explicitly discussed in the introduction and discussion.
3. The authors dismiss the use of remission status as an outcome, citing that it can be a biased assessment if made by the treating therapist (page 5-6). However they do not address potential flaws in self-reported assessments (e.g., misinterpreting the questions, over-reporting of symptoms to ensure that they receive help).
4. Studies on disorder-specific prediction have achieved higher accuracy than the current study (see the review by Aafjes-van Doorn 2021, table 1), however these findings are quickly dismissed by referring to small sample sizes and potential publication bias by referring to only one early study in the field (page 15). Here, the authors do not address the potential strengths of disorder-specific studies: Using questionnaires that are valid specifically for evaluating symptom levels and change over time, inclusion of specific predictors that are relevant for a specific disorder, use of highly trained (and potentially blinded) evaluators. Indeed, it might be the case that the best therapy predictions will be achieved by developing specific models for each disorder. In my opinion the field has not yet reached a conclusion and the authors need to acknowledge this.

## Minor Issues
  5. Paragraphs on the application of ML in other areas of health care (page 4) and psychopathology with neuroimaging data (page 5) can be removed. In my opinion there is now sufficient data in the field of clinical psychology to keep the focus there.
  6. To complement the results, I would like to see figures of ROC-curves as well as a confusion matrix of the classification in the test sample. These two presentations give straight-forward ways to assess the strength of the prediction.
  7. The discussion mentions six dimensions that the authors have constructed based on the most important predictors. In my opinion, such a dimension reduction is not needed and makes the discussion unnecessarily long.