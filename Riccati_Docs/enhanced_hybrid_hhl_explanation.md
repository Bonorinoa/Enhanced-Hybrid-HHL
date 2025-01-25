# Enhanced Hybrid HHL Module Explanation

This document provides detailed explanations of each main component of the `enhanced_hybrid_hhl` module. The explanations include relevant mathematics and references to the step-by-step HHL paper.

## Overview

The `enhanced_hybrid_hhl` module is designed to solve quantum linear systems using the Harrow-Hassidim-Lloyd (HHL) algorithm. The module includes various components such as preprocessing algorithms, eigenvalue inversion circuits, and result evaluation functions.

## Components

### 1. HHL Class

The `HHL` class implements the HHL algorithm for solving linear systems of equations using quantum computers. It supports different preprocessing algorithms and eigenvalue inversion circuits.

#### Key Methods:
- `__init__`: Initializes the HHL object with optional functions for result retrieval, preprocessing, and eigenvalue inversion.
- `construct_circuit`: Constructs the quantum circuit for the HHL algorithm using specified subcircuits.
- `estimate`: Runs the HHL algorithm with specified preprocessing and circuit construction.

### 2. Preprocessing Algorithms

The preprocessing algorithms are used to estimate the eigenvalues and eigenbasis projections of the input matrix.

#### Key Classes:
- `Yalovetzky_preprocessing`: Implements the Quantum Clock Quantum Phase Estimation (QCL-QPE) algorithm.
- `Lee_preprocessing`: Implements the canonical quantum phase estimation algorithm.
- `Iterative_QPE_Preprocessing`: Implements an iterative procedure to scale the quantum linear system problem.

### 3. Eigenvalue Inversion Circuits

The eigenvalue inversion circuits are used to perform the inversion of the eigenvalues in the HHL algorithm.

#### Key Functions:
- `EnhancedHybridInversion`: Constructs a quantum circuit for hybrid inversion based on given eigenvalues and eigenbasis projections.
- `HybridInversion`: Constructs a quantum circuit for hybrid inversion with a simpler approach.
- `CanonicalInversion`: Creates a universally controlled rotation on a specified number of clock qubits.
- `GrayCodeInversion`: Returns an ExactReciprocal object with specified parameters.

### 4. Result Evaluation Functions

The result evaluation functions are used to process the results of the quantum circuit and compute the final solution.

#### Key Functions:
- `get_circuit_depth_result`: Transpiles a given quantum circuit and calculates its depth.
- `get_fidelity_result`: Simulates the HHL circuit and returns the inner product between the simulated estimate and the classically calculated solution.
- `get_simulator_result`: Simulates the HHL circuit and returns the inner product between the simulated estimate and the classically calculated solution.

## Mathematics

### Matrix Riccati Equation

The matrix Riccati equation is a key component in the LQR problem. It is given by:

\[ \frac{dP(t)}{dt} = P(t)B(t)R^{-1}(t)B^T(t)P(t) - A^T(t)P(t) - P(t)A(t) - Q(t) \]

The solution of the Riccati equation is used to compute the optimal control function.

### Quantum Phase Estimation

Quantum phase estimation is used to estimate the eigenvalues of the input matrix. The phase estimation algorithm is implemented using the `PhaseEstimation` class from Qiskit.

### Eigenvalue Inversion

The eigenvalue inversion step is crucial for solving the linear system. The inversion circuits use controlled rotations to perform the inversion of the eigenvalues.

## References

The step-by-step HHL paper provides detailed insights into the HHL algorithm and its implementation. The paper can be found in the `Riccati_Docs/step_by_step_HHL_paper.pdf` file.

