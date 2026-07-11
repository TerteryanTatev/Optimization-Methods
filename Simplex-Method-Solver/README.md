# Simplex Method Solver for Linear Programming

This folder contains a custom Python implementation of the Simplex Method (incorporating artificial variables and Big-M style penalties), designed to solve multi-variable Linear Programming (LP) maximization problems from scratch.

##  Implemented Methodology
* **Canonical Form Transformation:** Introducing slack variables ($s_n$) and artificial variables ($y_n$) to convert inequality constraints into an operational linear system.
* **Simplex Tableau Matrix:** Structuring a dynamic computational matrix using `pandas` to keep track of basis variables, $C_j$ coefficients, and objective function indicators ($Z_j - C_j$).
* **Iterative Pivot Optimizations:** Implementing optimality tests to locate the entering/leaving variables and executing Gauss-Jordan elimination rows to transition across extreme points of the feasible region until convergence.

##  Technologies Used
* **Python 3**
* **NumPy:** For vector operations and row-transformation scaling.
* **Pandas:** For managing structural matrix representations and formatting the Simplex Tableau.
