# Project 2: Quantum for Portfolio Optimization

## Team 
Team Name: NaiveQuantum

Members:
| Name | WISER Enrollment ID |
|------|-------------------|
| La Wun Nannda | gst-9Znx386rMl8rJMQ |
| Aung Phone Kyaw | gst-lXnHQNnvqFrUrS6 |

## Project Summary

This project demonstrates a basic implementation of quantum computing techniques to solve portfolio optimization problems. It uses a straightforward Variational Quantum Algorithm (VQA) approach, specifically the Variational Quantum Eigensolver (VQE) with Conditional Value-at-Risk (CVaR) optimization, to address the task of selecting optimal bond portfolios from a universe of 31 fixed income securities.

The core problem involves minimizing the difference between a portfolio's characteristics and target values while satisfying various constraints. Traditional classical optimization methods, such as linear programming with CPLEX or Gurobi, face computational challenges as the problem size scales. Quantum computing offers a promising alternative through its inherent ability to explore large solution spaces efficiently using quantum superposition and entanglement.

Our implementation utilizes a basic TwoLocal ansatz with full entanglement patterns, designed to capture correlations between different bonds in the portfolio. The choice of full entanglement is motivated by recent advances in quantum hardware architecture such as tunable couplers in the Ankaa architecture. This advancement eases the implementation of fully entangled circuits, such as the two-local full entanglement ansatz, making them more practical on real quantum hardware. The algorithm employs CVaR optimization, which focuses on the worst-case scenarios rather than average performance, making it suitable for risk-sensitive financial applications. The CVaR approach optimizes the conditional value-at-risk objective, providing a different perspective compared to traditional mean-variance optimization.

Our results show convergence behavior with the algorithm completing in 931 iterations, and the solution selects 24 out of 31 bonds (77.4% selection rate). While these results are promising, it's important to note that this represents a basic, unoptimized implementation rather than a fully optimized solution.

Key technical aspects include the implementation of a QUBO (Quadratic Unconstrained Binary Optimization) formulation that transforms the original linear programming problem into a format suitable for quantum variational algorithms. The conversion process involves constraint handling and objective function reformulation to ensure the quantum algorithm can explore the solution space effectively.

**Important Limitation:** Although I understand the problem and the need to optimize it across various quantum hardware configurations, we are unable to compare different approaches (different ansatzes, different entanglements, different circuit repetitions, different backends, and different algorithms) due to our inexperience. Therefore, we project connects the existing parts in the repository to demonstrate how an ordinary, unoptimized quantum approach would solve the problem.

This project represents a learning exercise and proof-of-concept implementation rather than a comprehensive optimization study. It demonstrates the feasibility of applying quantum computing to real-world financial applications while acknowledging the limitations of a basic implementation. The work provides valuable insights into the practical challenges of quantum portfolio optimization and serves as a starting point for more sophisticated approaches.

Future work would ideally focus on systematic comparison of different quantum circuit architectures, investigation of various hyperparameters, testing on different quantum backends, and implementing post-processing techniques to improve solution quality. However, this current implementation successfully demonstrates the basic workflow of quantum portfolio optimization and provides a working example for educational purposes.

## Key Results

- **Best Objective Value:** -2237.1308551437114
- **Convergence:** 931 iterations
- **Solution Quality:** 24 selected bonds (77.4% selection rate)
- **Algorithm:** VQE with CVaR optimization
- **Ansatz:** TwoLocal with full entanglement

## Technologies Used

- **Quantum Framework:** Qiskit
- **Optimization:** Variational Quantum Eigensolver (VQE)
- **Risk Measure:** Conditional Value-at-Risk (CVaR)
- **Backend:** AerSimulator
- **Problem Formulation:** QUBO transformation

