# Multiple Regression & Feature Selection Modeling

This folder contains a statistical optimization and systems modeling approach to building Multiple Linear Regression models. It focuses on finding the optimal combination of independent variables (features) to predict a target outcome.

##  Implemented Methodology
* **Combinatorial Feature Selection:** Utilizing `itertools.combinations` to systematically evaluate all possible subsets of independent variables ($X_1, X_2, X_3, X_4$).
* **Model Evaluation ($R^2$ Optimization):** Running Ordinary Least Squares (OLS) regression for each subset to determine the coefficient of determination ($R^2$) and identify the mathematically optimal model (`best_model`).
* **Statistical Significance ($F$-test):** Implementing an $F$-test calculation to evaluate whether the inclusion of additional features significantly improves the model's explanatory power compared to a baseline model.

##  Technologies Used
* **Python 3**
* **Pandas & NumPy:** For structured dataset management and matrix operations.
* **Statsmodels:** For executing advanced statistical tests and Ordinary Least Squares (OLS) regression estimation.
* **Itertools:** For efficient mathematical combinations generation.
