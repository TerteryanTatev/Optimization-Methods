# Regression Residual Analysis & Error Evaluation

This folder contains a statistical systems modeling task focused on analyzing regression residuals ($z = y - \hat{y}$) to validate model assumptions and evaluate error independence.

##  Implemented Methodology
* **Residual Computation:** Calculating the exact deviations between the observed data points ($y$) and the model's fitted predictions ($\hat{y}$).
* **Sum of Squared Errors (SSE):** Computing the cumulative squared residuals ($\sum z^2$) to quantify the total unexplained variance within the evaluated model.
* **Lagged Dependency & Autocorrelation Check:** Structuring sequential residual comparisons ($z_t$ vs $z_{t-1}$) to inspect potential autocorrelation and verify if the error terms are independent and identically distributed (I.I.D.).

##  Technologies Used
* **Python 3**
* **NumPy:** For vectorized operations, error squaring, and array aggregations.
* **Pandas:** For handling dataset sequences and structured data logging.
