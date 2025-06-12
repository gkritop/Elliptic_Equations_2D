# Elliptic_Equations_2D

## Overview

This project develops code to numerically solve the *Laplace* and *Poisson* equations on a two-dimensional rectangular domain, applying various boundary conditions (Dirichlet, Neumann, and Periodic).  

The solution method is the Gauss-Seidel iterative scheme with a relaxation factor to speed up convergence.

This work was completed as part of the **Computational Physics** course at the **Physics Department, University of Crete**.

## Problem Statement

We solve the Laplace and Poisson equations where the potential, charge density, and permittivity are the main variables.

## Methodology

### Grid Setup

- The domain is discretized using a uniform rectangular grid with spacing and a fixed number of points.
- Each grid point is assigned coordinates based on its position in the grid.

### Discretization

Using the central difference scheme, the Poisson equation is discretized to approximate the potential at each grid point.

The total energy is computed using a corresponding discrete form.

### Boundary Conditions

- **Dirichlet:** Fixed potential values on the boundaries (e.g., zero potential at edges).
- **Neumann and Periodic:** Also implemented to model constant flux or periodic repetition at the boundaries.

### Gauss-Seidel Iterative Solver

- Initialize the potential with an initial guess.
- Update values iteratively with relaxation to accelerate convergence.
- Iterate until the maximum change between successive values is below a specified threshold.

## Results

- Solutions for various cases corresponding to the assignment questions are presented.
- Results are documented in numbered sections from 1 to 11 inside the notebook.

## Conclusion

- The Laplace and Poisson equations were successfully solved with multiple boundary conditions.
- The relaxation factor significantly affects convergence speed, with optimal values typically between 1 and 2.
- Dipole position and grid resolution strongly influence the computed energy and solution accuracy.

## Usage

This repository contains a Jupyter Notebook performing all computations and visualizations.  
To run it, install required Python packages (e.g., NumPy, Matplotlib) and open the notebook in a Jupyter-supported environment.

## Acknowledgements

Developed by **Giorgos Kritopoulos**  
Computational Physics course, Physics Department, University of Crete  
Date: March 8, 2025
