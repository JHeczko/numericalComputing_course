# Numerical Computing Course

This repository contains a collection of small numerical analysis projects and experiments. Each folder focuses on a specific numerical method or topic, using Python (primarily NumPy) to implement algorithms and compare results.

---

## 📁 Folder Overview

### `derivative_approximations`
- Implements numerical differentiation using finite difference formulas (forward, central, and higher-order).
- Computes approximation errors for different step sizes `h` and outputs plots showing convergence behavior.

### `eigenvalue_methods`
- Implements several eigenvalue extraction methods for small matrices:
  - Power method (dominant eigenvalue)
  - Inverse power method / Rayleigh Quotient Iteration (RQI)
  - QR algorithm (using NumPy QR decomposition)
- Compares results against NumPy’s built-in `linalg.eigvals`.

### `monte_carlo_integral`
- Jupyter notebook with Monte Carlo demonstrations:
  - Generating random numbers (seeded vs unseeded)
  - Estimating π using random sampling inside a quarter circle
  - (Partially completed) Monte Carlo integration examples

### `tridiagonal_solver`
- Compares solving a tridiagonal linear system using:
  - Thomas algorithm (specialized tridiagonal solver)
  - NumPy LU solve (`numpy.linalg.solve`)
- Measures and prints runtime comparisons.

### `tridiagonal_solver_bc`
- Similar to `matrix_solver/`, but uses alternate boundary conditions or matrix setup.
- Includes plotting and runtime comparisons for different solver setups.

### `floating_point_error`
- Investigates numerical error in evaluating a sum:
  - `func` uses a loop with repeated operations
  - `func2` uses vectorized NumPy operations
- Prints and compares results to demonstrate differences due to floating point precision and evaluation order.

### `root_finding`
- Implements classical root-finding methods for a polynomial function:
  - Bisection method
  - Regula falsi (false position)
  - Secant method
- Compares convergence and prints the roots found for given intervals.

### `conditioning`
- Explores sensitivity and conditioning of linear systems:
  - Solve `Ax = b` for two matrices A and B
  - Perturb the right-hand side vector `b` with a small random error
  - Compare result differences and compute condition numbers (`cond(A)`)

### `sherman_morrison`
- Demonstrates solving tridiagonal systems with a rank-1 update:
  - `main_jawnie.py` compares an explicit formula (“jawnie”) vs LU solve
  - `main_morison.py` implements Sherman–Morrison + Thomas algorithm and compares with LU

### `iterative_solvers`
Contains implementations of iterative linear solvers for tridiagonal systems:
- `gaus.py` – Gauss–Seidel (with tridiagonal structure)
- `jacobi.py` – Jacobi method
- `overrelaxation.py` – Successive Overrelaxation (SOR)
- `richardsonn.py` – Richardson iteration

### `conjugate_gradient`
- Implements conjugate gradient (CG) methods for symmetric positive definite linear systems:
  - Basic CG solver using tridiagonal representation
  - Preconditioned CG using diagonal scalings
  - Verified positive definiteness and compares norms against NumPy direct solve

### `inverse_power_method`
- Implements inverse power iteration for eigenvalue computation:
  - Uses a tridiagonal solver (Thomas) as the linear solve inner step
  - Compares eigenvectors / eigenvalues against NumPy’s `linalg.eig`

### `vegas_integral`
- 

### `ditribution_generator`
- 

---

## 🚀 How to Run
Most scripts can be executed from the command line, e.g.: 

```bash
python <folder>/main.py
```

For Jupyter notebooks (in `integrals/`), open the notebook using:

```bash
jupyter notebook integrals/integrals_monte_carlo.ipynb
```

---

## 📝 Notes
- All implementations are intended for educational purposes and are written for clarity rather than production performance.
- Many of the solvers assume small to moderate matrix sizes and do not optimize memory usage.