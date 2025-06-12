# Elliptic_Equations_2D

## Overview

This project presents the development of code that numerically solves the *Laplace* and *Poisson* equations on a two-dimensional rectangular domain, applying various boundary conditions (Dirichlet, Neumann, and Periodic).  

The implemented method is based on the Gauss-Seidel iterative scheme enhanced by a relaxation factor (ω) to accelerate convergence.

This work was completed as part of the **Computational Physics** course at the **Physics Department, University of Crete**.

---

## Problem Statement

We solve the following equations:

- *Laplace equation*:

  $$
  \nabla^2 \phi = 0
  $$

- *Poisson equation*:

  $$
  \nabla^2 \phi = -\frac{\rho}{\epsilon}
  $$

where \( \phi \) is the potential, \( \rho \) is the charge density, and \( \epsilon \) is the permittivity.

---

## Methodology

### Grid Setup

- The domain is discretized using a uniform rectangular grid with spacing \( h \) and \( N \times N \) points.
- Coordinates for each grid point \((i,j)\) are:

  $$
  (x_i, y_j) = ((i-1)h, (j-1)h)
  $$

### Discretization

Using central differences, the Poisson equation is approximated as:

$$
\phi_{i,j} = \frac{1}{4} \left( \phi_{i+1,j} + \phi_{i-1,j} + \phi_{i,j+1} + \phi_{i,j-1} + h^2 \frac{\rho_{i,j}}{\epsilon} \right)
$$

The total energy of the system is computed via the corresponding discrete formulation.

### Boundary Conditions

- **Dirichlet**: Fixed potential values on the domain boundaries (e.g., \( \phi = 0 \) at edges).
- **Neumann and Periodic**: Implemented to model scenarios with constant flux or repeating boundaries.

### Gauss-Seidel Iterative Solver

- Initialize \( \phi \) with an initial guess.
- Update values iteratively using:

  $$
  \phi_{i,j}^{(new)} = (1-\omega)\phi_{i,j}^{(old)} + \frac{\omega}{4} \left( \phi_{i+1,j} + \phi_{i-1,j} + \phi_{i,j+1} + \phi_{i,j-1} + h^2 \frac{\rho_{i,j}}{\epsilon} \right)
  $$

- Continue iterations until the maximum change between successive updates is less than a specified tolerance (e.g., \( 10^{-5} \)).

---

## Results

- Solutions were computed for various cases corresponding to the assignment's questions.
- Results are documented in numbered sections from 1 to 11 within the notebook.

---

## Conclusion

- The project successfully solves the Laplace and Poisson equations with multiple boundary conditions.
- The relaxation factor \( \omega \) strongly influences convergence speed, with optimal values found in \( 1 < \omega < 2 \).
- Dipole placement and grid resolution significantly impact the calculated energy and accuracy of the solution.

---

## Usage

This repository contains a Jupyter Notebook that runs all computations and visualizations.  
To run the notebook, install the required Python packages (e.g., NumPy, Matplotlib) and execute the notebook in an environment supporting Jupyter.

---

## Acknowledgements

Developed by **Giorgos Kritopoulos**  
Computational Physics course, Physics Department, University of Crete  
Date: March 8, 2025

---
