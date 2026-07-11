# Multi-Dimensional Transportation Problem via Dynamic Programming

This project presents a **multi-dimensional transportation optimization framework** based on **Dynamic Programming (DP)**.

The implementation solves a complex resource allocation and transportation routing problem by modeling multiple resource constraints simultaneously and applying recursive optimization principles.

The project was developed as an **Operational Research term paper**, demonstrating the practical application of dynamic programming techniques for optimization problems.

## Features

- Implements a multi-dimensional Dynamic Programming optimization model.
- Tracks multiple resource constraints throughout sequential decision stages.
- Applies Bellman's principle of optimality to determine minimum-cost solutions.
- Reconstructs the optimal decision path using forward-backward tracking.
- Generates structured analytical reports and optimization results.

## Algorithm Overview

The implementation follows the Dynamic Programming optimization process:

### 1. Multi-State Space Representation

The problem is represented using a multi-dimensional state space where each state tracks available resources:

**s₁, s₂**

at different stages of the transportation process.

Each state represents a possible resource configuration and stores the optimal cost required to reach that state.

### 2. Bellman Functional Recurrence

The optimal solution is calculated using Bellman's recursive equation:

**Vⱼ(s₁, s₂) = min { Costⱼ(x₁, x₂) + Vⱼ₊₁(s₁ - x₁, s₂ - x₂) }**

where:

- **Vⱼ(s₁, s₂)** represents the minimum cost at stage j with available resources s₁ and s₂.
- **Costⱼ(x₁, x₂)** represents the current transportation cost.
- **x₁, x₂** represent resource allocation decisions.
- The recurrence evaluates current decisions together with future optimal sub-solutions.

### 3. Forward-Backward Policy Reconstruction

After computing the dynamic programming table:

- A backward induction process identifies optimal states.
- A forward tracking procedure reconstructs the exact sequence of decisions.
- The final result represents the global minimum-cost transportation strategy.

### 4. Result Analysis

The program generates:

- Dynamic programming state tables.
- Optimal policy paths.
- Resource allocation decisions.
- Structured execution reports.

## Technologies

- **Python 3**
- **NumPy** – Multi-dimensional array operations, state indexing, and optimization matrix handling.
- **Pandas** – Data organization and analytical reporting.
- **Tabulate** – Formatting optimization results and execution logs.

## Mathematical Background

Dynamic Programming is an optimization technique based on the principle of optimality:

> An optimal solution contains optimal solutions to its subproblems.

The transportation problem is decomposed into smaller decision stages, where each stage evaluates possible resource allocations and stores the best achievable cost.

By combining recursive optimization with state tracking, the algorithm avoids repeated calculations and efficiently finds the global minimum solution.

## Output

The program provides:

- Complete dynamic programming state matrix.
- Minimum transportation cost.
- Optimal resource allocation vector.
- Reconstructed decision pathway.
- Formatted analytical reports.

## Applications

Multi-dimensional transportation optimization methods are used in:

- Supply chain optimization
- Logistics planning
- Resource allocation
- Production scheduling
- Network optimization
- Operations research systems
