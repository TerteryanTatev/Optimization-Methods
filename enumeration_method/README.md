# Enumeration Method

## Overview

The **Enumeration Method** (also known as **Grid Search**) is one of the simplest numerical optimization techniques used to approximate the minimum of a function on a given interval.

The main idea of the method is to divide the interval into equally spaced points, evaluate the function at each point, and choose the smallest value.

This approach is easy to implement and does not require derivative information.

---

## Mathematical Formulation

Assume that `f(x)` is a **unimodal function** on the interval `[a, b]`, meaning it has a single global minimum.

We want to find the minimum of `f(x)` with absolute accuracy `ε > 0`.

The interval `[a, b]` is divided into `n` equal parts:

```
x_k = a + k * (b - a) / n ,   k = 0,1,...,n
```

where

```
n ≥ (b - a) / ε
```

Then the function values are computed:

```
f(x0), f(x1), ..., f(xn)
```

The approximate minimum is determined as

```
f(x_m) = min f(x_k)
```

where `x_m` corresponds to the minimum function value.

The maximum possible error is

```
ε = (b - a) / n
```

---

## Advantages

- Simple to implement
- Does not require derivatives
- Works for many types of functions

---

## Disadvantages

- Requires many function evaluations
- Computational cost increases when high accuracy is required
- Accuracy depends on the step size

---

## Algorithm

```
1. Choose interval [a, b]
2. Select accuracy ε
3. Compute number of steps n = (b - a) / ε
4. Generate points x_k in the interval
5. Evaluate f(x_k) for each point
6. Choose the smallest value
```

---

## Python Implementation

```python
import sympy as sp
import matplotlib.pyplot as plt

x = sp.symbols('x')
f = (1/4) * x**4 + x**2 - 8*x + 12

a, b = 0, 2
eps = 0.5

n = int((b - a) / eps)

points = []

for i in range(n + 1):
    xi = a + i * (b - a) / n
    yi = f.subs(x, xi)
    points.append((xi, yi))

minimum = min(points, key=lambda p: p[1])

print("Sampled points:", points)
print("Approximate minimum:", minimum)
```

---

## Visualization

The following plot illustrates the sampled points used by the enumeration method.

- Line → sampled function values  
- Points → evaluated grid points

![Enumeration Method](images/enumeration_plot.png)
