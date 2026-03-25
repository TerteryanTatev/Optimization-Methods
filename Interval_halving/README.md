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


## Visualization

- **Red points** → midpoints at each iteration  
- **Green point** → approximate minimum  
- **Blue curve** → function `f(x)` over interval

This visualization shows how the interval shrinks toward the minimum point and illustrates convergence of the dichotomy method.

! [Dichotomy Method](images/Interval_halving.png)
