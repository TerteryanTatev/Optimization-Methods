# Stepwise Regression & Fisher Selection Method

This folder contains a systems modeling and statistical analysis project focused on optimizing multi-variable regression models using the Stepwise Selection technique based on Fisher's $F$-test criteria.

##  Implemented Methodology
* **Stepwise Variable Selection:** Systematically adding or removing predictor variables ($X_1, X_2, X_3, X_4$) to construct the most efficient and parsimonious regression model.
* **Fisher's $F$-Test Evaluation:** Implementing a custom mathematical function (`fisher_stepwise`) to calculate the statistical significance of adding partial variables based on incremental changes in the coefficient of determination ($R^2$).
* **Iterative Model Comparison:** Testing and evaluating specific nested model combinations (e.g., comparing partial coefficient dynamics like $R_{12}$ vs $R_{24}$) to establish stable mathematical constraints for system outputs.

##  Technologies Used
* **Python 3**
* **NumPy:** For managing matrices and implementing statistical selection logic formulas.
* **Pandas:** For structural dataframe tracking and data sequence evaluation.
