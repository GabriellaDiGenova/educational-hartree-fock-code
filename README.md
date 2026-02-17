# Hartree–Fock (RHF) Toy Code — s-type Gaussian Basis

Small educational Hartree–Fock program written for the TCCM Learning Unit (Hartree–Fock coding exercise).  
It solves the Roothaan–Hartree–Fock equations for **closed-shell systems** using **only s-type contracted Gaussian basis functions**, and computes all required one- and two-electron integrals analytically.

> This is a learning/teaching implementation, designed for debugging rather than performance.

## What this program does

Given a molecular geometry, total charge, and an s-type contracted Gaussian basis definition, the program:

- computes the nuclear repulsion energy,
- computes one-electron integrals: overlap **S**, kinetic **T**, nuclear attraction **V**,
- computes two-electron repulsion integrals **(μν|λσ)**,
- builds the core Hamiltonian **H_core = T + V**,
- orthogonalizes the AO basis via symmetric orthogonalization **X = S^{-1/2}**,
- runs an SCF loop (Restricted HF):
  - builds the Fock matrix **F = H_core + G(P)**,
  - diagonalizes **F' = Xᵀ F X**,
  - updates the density matrix from occupied MOs,
  - iterates until convergence.


## Repository contents

- `HF_code_DiGenova` — main Python script (currently expects an input file named `h4_sample.input`, can be edited if needed)
- `h4_sample.input` — sample input: H4 test case + basis definition (and also contains reference integrals)

---

## Requirements

- Python 3.x
- NumPy
