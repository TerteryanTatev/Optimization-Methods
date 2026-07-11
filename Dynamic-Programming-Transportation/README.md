# Multi-Dimensional Transportation Problem via Dynamic Programming

This folder contains a comprehensive operational research framework designed as a term paper project. It solves a complex, multi-resource network transportation and distribution routing problem using multi-dimensional Dynamic Programming (DP).

##  Implemented Methodology
* **Multi-State Space Tracking:** Formulating a dynamic state matrix that monitors multiple bounded resource capacities simultaneously ($s_1, s_2$) across sequential routing nodes.
* **Bellman Functional Recurrence:** Constructing recursive optimization algorithms to compute the minimal cost boundary by evaluating current trade-offs against future optimal sub-policies:
  $$V_j(s_1, s_2) = \min_{x_1, x_2} \{ \text{Cost}_j(x_1, x_2) + V_{j+1}(s_1 - x_1, s_2 - x_2) \}$$
* **Forward-Backward Policy Reconstruction:** Executing a complete backward induction pass to populate the DP state cache, followed by a forward tracking function to isolate the precise global minimum vector layout.
* **Structured Analytics Reporting:** Generating descriptive pandas dataframes and rendering finalized execution policies into formatted text matrices.

##  Technologies Used
* **Python 3**
* **NumPy & Pandas:** For indexing multi-dimensional state coordinates and tracking optimization matrices.
* **Tabulate:** For formatting high-contrast execution logs and policy trajectory pathways.
