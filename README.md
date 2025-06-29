# 🧩 CSS Quantum Hamming Code [[15,7,3]] Error Correction in Qiskit

This code demonstrates the implementation of the quantum Hamming CSS error correcting code \([[15,7,3]]\). Random Pauli errors are applied to each qubit with probability \( 0 \leq p \leq 1 \) and the corresponding corrections are performed.

---

## Overview

The code provides quantum circuit constructions for:

- **Logical zero state preparation** of the [[15,7,3]] CSS code  
- **Random Pauli error application** to simulate depolarizing noise  
- **Syndrome extraction circuits** for X and Z stabilizers  
- **Correction operations** based on measured syndromes  
- **Success probability calculation** across various error probabilities

---

## Benchmark Results

- **Code**: [[15,7,3]] CSS Hamming code  
- **Trials per p-value**: 50  
- **Total sampled p-values**: 1000 (uniform between 0 and 1)  
- **Gate set used**: {H, CX, X, Z, measurement}  
- **Circuit features**:
  - Logical state preparation  
  - Pauli noise channel  
  - Syndrome extraction  
  - Recovery operation

---

## Usage Instructions

1. **Run the package imports.**

2. **Initialize parity matrices and logical zero state.**  
   - Run the first cell to generate the parity check matrix, its RREF form (with column swaps), and the logical \(|0_L\rangle\) components.

3. **Run the random Pauli error cell.**  
   - Applies a uniformly chosen random Pauli operator to each qubit with probability \( p \).

4. **Run the extract_Xsyndromes cell.**  
   - Applies CX gates from data qubits to X-ancillas based on the parity check matrix.  
   - *(Optional)* Uncomment example usage to view the circuit.

5. **Run the extract_Zsyndromes cell.**  
   - Applies CX gates from Z-ancillas to data qubits based on the parity check matrix.  
   - *(Optional)* Uncomment example usage to view the circuit.

6. **Run the Quantum_Hamming_Circuit cell.**  
   - Prepares the logical zero state, applies errors, extracts syndromes, and performs corrections.  
   - *(Optional)* Uncomment example usage to view the circuit for a chosen p-value (e.g. \( p = 0.2 \)).

7. **Run the success_probabilities cell.**  
   - Calculates and plots success probabilities for various values of \( p \).  
   - Default: `total_trials = 20`, `p_values = [0, 0.04, 0.08, 0.12, 0.16]`.  
   - Prints each \((p, \text{success probability})\) pair during simulation.  
   - Produces a final plot showing success/(20 trials) vs error probability.

---

## Results

The provided plot was generated using **1000 p-values sampled uniformly between 0 and 1**, each with **50 trials** to compute the corresponding success probability.

---

## References

- Gottesman, Daniel. *Stabilizer Codes and Quantum Error Correction*. Ph.D. thesis, California Institute of Technology, 1997.  
  [https://arxiv.org/pdf/quant-ph/9705052](https://arxiv.org/pdf/quant-ph/9705052)

- Nielsen, Michael A., and Isaac L. Chuang. *Quantum Computation and Quantum Information*. 10th Anniversary ed., Cambridge University Press, 2010.
