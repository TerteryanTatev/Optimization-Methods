# Dynamic Programming & Backward Induction Solver

This folder contains a custom Python implementation of Bellman's Optimality Principle utilizing Backward Induction to solve multi-stage sequential decision problems and optimal stopping limits under uncertainty.

##  Implemented Methodology
* **Stochastic Stage Mapping:** Structuring continuous resource/reward probabilities across discrete operational periods ($t=1 \dots N$).
* **Bellman Equation Optimization:** Recursively calculating expected values backwards from the terminal state to establish threshold values for each stage:
  $$V_t(s) = \max \{ W_t(s), \mathbb{E}[V_{t+1}(s')] \}$$
* **Tabular Log Sequencing:** Formatting state values, transition strategies, and policy logs into a readable summary using structural layout components.

##  Technologies Used
* **Python 3**
* **NumPy:** For processing matrix distributions and computing mathematical vector state expectations.
* **Tabulate:** For printing organized iteration logs into terminal-friendly tables.
