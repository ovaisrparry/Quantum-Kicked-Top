
# Quantum Kicked Top Level Spacing Analysis

## Overview

This repository contains a Python implementation for analyzing the **Quantum Kicked Top (QKT)** model, focusing on the level spacing statistics. The QKT is a widely studied model in quantum chaos, exhibiting classical chaos when kicked periodically. The code computes eigenvalues of the Floquet operator, applies symmetry constraints (e.g., parity), and analyzes the level spacing distribution of the filtered eigenvalues.

### Key Features
- Construction of the Floquet operator for the QKT model.
- Symmetry filtering based on parity.
- Calculation and visualization of level spacing statistics (`r_n` distribution).
  
## Installation

1. Install the required dependencies:
   ```bash
   pip install numpy matplotlib scipy
   ```

2. Clone the repository and navigate to the directory:
   ```bash
   git clone https://github.com/your-repository/qkt-level-spacing.git
   cd qkt-level-spacing
   ```

## Files

- `Quantum_Kicked_Top_Level_Spacing.ipynb`: Jupyter notebook implementing the level spacing analysis for the QKT model.

## Code Structure

### Key Functions

- **Pauli Matrices:**
  Constructs the Pauli matrices used for calculating angular momentum operators.
  
- **Angular Momentum Operators (`Jx`, `Jz`, `J+`, `J-`):**
  Constructs the angular momentum operators for the QKT model, required for the Floquet operator construction.

- **Floquet Operator Construction:**
  The code constructs the Floquet operator as:
  \[
  U_F = e^{-i rac{k}{2j} J_x^2} e^{-i  lpha J_z}
  \]
  where \(J_x\) and \(J_z\) are the angular momentum operators, \(k\) is the kicking strength, and \( lpha\) is the precession angle.

- **Symmetry Filtering:**
  The parity operator is applied to filter the eigenstates. Only those states with a parity eigenvalue of +1 are retained for further analysis.

- **Level Spacing Statistics:**
  After symmetry filtering, the level spacing distribution is analyzed. The `r_n` values are computed as:
  \[
  r_n = rac{\min(d_n, d_{n+1})}{\max(d_n, d_{n+1})}
  \]
  where \(d_n = 	heta_{n+1} - 	heta_n\) are the differences between successive eigenphases \(	heta_n\).

### Output

The code outputs the following:
- **Eigenvalues and eigenvectors** of the Floquet operator.
- **Filtered eigenvalues and eigenvectors** with +1 parity.
- **Histogram plot** showing the distribution of \(r_n\) values.

## Usage

1. Open the notebook file `Quantum_Kicked_Top_Level_Spacing.ipynb` and run the cells to compute the level spacing statistics.
   
2. Adjust the parameters for the kicked top:
   - `j`: Total angular momentum quantum number.
   - `k`: Kicking strength.
   - `alpha`: Precession angle.

3. The notebook will generate plots showing the distribution of \(r_n\), which is used to determine whether the system exhibits chaotic behavior (following the Wigner-Dyson distribution) or regular behavior (Poisson distribution).

## Example

Here is a simple example of how to use the code:

```python
# Parameters for the kicked top model
j = 15  # Angular momentum quantum number
k = 3.0  # Kicking strength
alpha = 0.5  # Precession angle

# Floquet operator construction and symmetry analysis
# Computes the eigenvalues and applies parity symmetry filtering

# Plot the level spacing statistics
plt.hist(r_n, bins=30, density=True, alpha=0.75, color='blue')
plt.xlabel('$r_n$')
plt.ylabel('Frequency')
plt.title('Distribution of $r_n$')
plt.grid(True)
plt.show()
```

## References

For more details on the Quantum Kicked Top and level spacing statistics:
- Haake, F. (2010). *Quantum Signatures of Chaos*. Springer Series in Synergetics.
