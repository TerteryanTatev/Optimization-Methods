# Method of Steepest Descent (Gradient Optimization)

This folder contains a custom Python implementation of the Method of Steepest Descent, a foundational multi-dimensional first-order optimization algorithm designed to locate local minima of unconstrained differentiable functions.

##  Implemented Methodology
* **Symbolic Gradient Computation:** Leveraging `sympy` to analytically evaluate partial derivative vectors ($\nabla f(x)$) across multi-variable systems.
* **Optimal Step Size Selection:** Dynamically computing the optimal learning rate ($\alpha_k$) at each iteration along the negative gradient vector path to ensure maximum objective value reduction per step.
* **Convergence Control:** Monitoring iteration cycles using Euclidean norm thresholds ($\|\nabla f(x)\| < \epsilon$) and programmatically tracking progress inside a structural `tabulate` matrix.

##  Technologies Used
* **Python 3**
* **NumPy:** For vector norms and coordinate transformations.
* **SymPy:** For analytical calculus and symbolic functional evaluation.
* **Tabulate:** For rendering execution logs into readable terminal tables.
