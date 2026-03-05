# Dichotomy Method (Interval Halving)

## Overview

The **Dichotomy Method** (also called **Interval Halving**) is a numerical optimization technique used to find the minimum of a unimodal function on a given interval `[a, b]` with a specified absolute precision `ε > 0`.

The main idea of the method is to iteratively reduce the interval containing the minimum by evaluating the function at two closely spaced points and selecting the subinterval where the minimum lies.

---

## Mathematical Formulation

Assume that `f(x)` is **unimodal** on `[a, b]` and we want to find the approximate location of its minimum `x*` with accuracy `ε`.

**Step 0:**  
Choose a small number `δ ∈ (0, 2ε)` and set `a = a0, b = b0`.  
Compute two points:

```
x1^(0) = (a0 + b0 - δ) / 2
x2^(0) = (a0 + b0 + δ) / 2
```

and evaluate

```
f1^(0) = f(x1^(0)),   f2^(0) = f(x2^(0))
```

**Step 1:**  
Determine the new search interval `[a1, b1]`:

- If `f2^(0) ≤ f1^(0)`, then `a1 = a0`, `b1 = x2^(0)`
- If `f2^(0) > f1^(0)`, then `a1 = x1^(0)`, `b1 = b0`

**Step k (k ≥ 1):**  
For the k-th iteration, compute:

```
x1^(k) = (ak + bk - δ) / 2
x2^(k) = (ak + bk + δ) / 2
f1^(k) = f(x1^(k)), f2^(k) = f(x2^(k))
```

Update the interval `[ak+1, bk+1]` as in Step 1.

**Stopping criterion:**  

Stop when 

```
|b - a| ≤ ε
```

The approximate minimum point is

```
x_m ≈ (a + b) / 2
f(x_m) ≈ f((a + b)/2)
```

The maximum possible error is

```
|x* - x_m| ≤ ε
```

---

## Advantages

- Simple and easy to implement  
- Does not require derivative information  

---

## Disadvantages

- Requires multiple function evaluations  
- Computational cost increases if high precision is needed  

---

## Python Implementation

```python
import sympy as sp
import numpy as np
import matplotlib.pyplot as plt

# Define symbolic variable and function
x = sp.symbols('x')
f_sym = (1/4) * x**4 + x**2 - 8*x + 12
f_num = sp.lambdify(x, f_sym, "numpy")  # For numerical evaluation and plotting

# Interval and precision
a, b = 0, 2
eps = 0.5
delta = 0.1

# Store midpoints for plotting
x_history = []

# Dichotomy iterations
while abs(b - a) > eps:
    x1 = (a + b - delta)/2
    x2 = (a + b + delta)/2
    
    y1 = f_sym.subs(x, x1)
    y2 = f_sym.subs(x, x2)
    
    xmin_iter = (a + b)/2
    x_history.append(xmin_iter)
    
    if y1 < y2:
        b = x2
    else:
        a = x1

# Approximate minimum
xmin = (a + b)/2
ymin = f_sym.subs(x, xmin)

# Visualization
X = np.linspace(a - 1, b + 1, 400)
Y = f_num(X)

plt.figure(figsize=(8, 5))
plt.plot(X, Y, label="f(x)", linewidth=2)
plt.scatter(x_history, f_num(np.array(x_history)), color="red", s=50, zorder=5, label="Iterations")
plt.scatter(xmin, ymin, color="green", s=100, label="Minimum")

plt.title("Dichotomy Method")
plt.xlabel("x")
plt.ylabel("f(x)")
plt.grid(True, linestyle='--', alpha=0.7)
plt.legend()
plt.tight_layout()
plt.show()
```

---

## Visualization

- **Red points** → midpoints at each iteration  
- **Green point** → approximate minimum  
- **Blue curve** → function `f(x)` over interval

This visualization shows how the interval shrinks toward the minimum point and illustrates convergence of the dichotomy method.

! [Dichotomy Method](images/interval_halving.png)
