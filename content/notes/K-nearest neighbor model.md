---
aliases:
  - KNN model
  - KNN
created: 2022-09-07
updated: 2023-09-01
---

# K-nearest neighbor model
Date created: 2022-08-23

"Given a set of reference data, a new sample is predicted by using the values of the _K_ most similar data in the reference set."

For example, if a book buyer needs a prediction for a new book, historical data from existing books may be available. A 5-nearest neighbor model would estimate the number of the new books to purchase based on the sales numbers of the five books that are most similar to the new one (for some definition of “similar”).

This model is defined only by the structure of the prediction (the average of five similar books). No theoretical or probabilistic assumptions are made about the sales numbers or the variables that are used to define similarity.

---
# References
* [[1 - Software for modeling]]