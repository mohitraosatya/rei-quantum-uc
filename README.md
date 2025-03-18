# Quantum Unit Commitment Demo for Resilient Entanglement Inc.

This project is a proof-of-concept demonstration of using the Quantum Approximate Optimization Algorithm (QAOA) to solve a simplified Unit Commitment (UC) problem—an integral part of power grid operations. It is designed with Resilient Entanglement Inc.’s focus on quantum energy management in mind and showcases how small, targeted improvements to QAOA-based UC can help push quantum solutions closer to real-world readiness.

## Alignment with REI’s Quantum-Energy Vision
Resilient Entanglement Inc. has been pioneering quantum computing for grid resilience and optimization. This demo tackles a core operational challenge—Unit Commitment—using a hybrid quantum-classical approach. By improving QAOA formulations and penalty strategies, it offers a pathway for integrating advanced quantum solvers into REI’s platform.

## Potential for Scale-up
While this notebook shows a toy problem (3–5 generators), the underlying methodology can be extended to larger power systems. With refinements like problem decomposition or improved encoding, the approach could become part of REI’s Quantum Energy Management System (QEMS)—eventually handling real-world UC problems involving hundreds of generators.

## Error Mitigation & Practical Enhancements
This demo can serve as a sandbox for experimenting with noise mitigation and other advanced quantum features. REI’s production environment requires robust solutions. By starting with this small-scale proof-of-concept, the company can test new ideas (e.g., improved cost functions, advanced penalty terms, or hardware-specific optimizations) before deploying them in the QEMS platform.

## Improved Hybrid Workflow
The code shows how to combine classical solvers (as a baseline) with QAOA, illustrating a flexible hybrid workflow. Resilient Entanglement could incorporate such a workflow in a real-time setting—using quantum algorithms to tackle the combinatorial aspect of UC, while classical methods handle fine-tuning continuous variables (like generator dispatch levels).

## Project Overview

- Objective: Solve a simplified Unit Commitment problem: turn on or off certain generators to meet a fixed demand at minimal cost.
- Method: QUBO Formulation: Encode cost minimization and demand-fulfillment constraints into a single binary optimization problem.
QAOA: Use a variational quantum-classical algorithm to explore solutions in a quantum state space, guided by a classical optimizer.
Sampler (Qiskit Primitives): Leverage Qiskit’s new Sampler interface with an AerSimulator backend to run quantum circuits efficiently.
- Key Files & Cells
Problem Setup: Define generators (capacity, cost), demand, and penalty parameters.
QUBO Construction: Convert the objective + constraints into a Quadratic Unconstrained Binary Optimization problem.
Classical Baseline: Solve with a classical method (CPLEX or exact solver) for verification.
QAOA Execution: Run the QAOA algorithm, interpret the solution, and compare to the classical baseline.
Results
- In a toy scenario (3 generators, 50 MW demand), QAOA finds the correct minimal-cost solution that exactly meets demand.
Demonstrates how quantum methods can tackle small-scale UC, paving the way for real-world scenarios once hardware scales.
## How This Could Improve REI’s Quantum Software

- Enhanced Penalty Strategy:
The penalty approach used here (for exact demand matching) can be adapted for partial or flexible demand constraints—crucial in real grids with dynamic load.
Offers a template to incorporate advanced cost terms (startup costs, ramping constraints, or emission limits) that REI might want to integrate into its QEMS modules.
- Hybrid Flexibility:
Demonstrates how to embed QAOA within a hybrid environment. REI could extend this code to handle discrete–continuous decisions (generator on/off + dispatch levels) by bridging quantum combinatorial search with classical solvers for the continuous part.
- Scalable Testing & Verification:
The notebook structure allows for modular testing of different QAOA depths, penalty coefficients, or advanced optimizers.
This approach can be scaled and tested on bigger standard power-system test cases (e.g., IEEE 14-bus, 30-bus) to measure performance under more realistic conditions.
- Error Mitigation & NISQ Readiness:
Since real quantum hardware is noisy, REI can adapt the notebook to experiment with error mitigation techniques (e.g., zero-noise extrapolation) to improve solution fidelity on near-term devices.

By exploring these strategies in a small demo, they can refine best practices before deploying on actual hardware in a production environment.

## Getting Started

Clone / Download this repository or notebook.
Install the required packages:
```

pip install qiskit qiskit-aer
pip install qiskit qiskit-optimization --quiet
pip install qiskit-optimization[cplex] --quiet
pip install qiskit-optimization[gurobi] --quiet

```

## Contact:
Email: saka4331@colorado.edu  Linkedin: https://www.linkedin.com/in/mohitraosatya/
