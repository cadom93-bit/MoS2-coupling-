# MoS2-coupling

A repository containing data and scripts for analyzing the electronic structure and coupling mechanisms of Molybdenum Disulfide (MoS₂) systems. This project specifically focuses on parsing, processing, and visualizing Projected Density of States (PDOS) calculations broken down by specific atomic orbitals (s, p, d).

## 📁 Repository Structure

The repository contains processed quantum mechanical simulation outputs (e.g., from Quantum ESPRESSO or similar DFT codes) organized by atomic projection:

*   **`MoS2.pdos_atm#1(S)_wfc#1(s)`** - PDOS for Sulfur (S) atom 1, wavefunction 1 (s-orbital).
*   **`MoS2.pdos_atm#1(S)_wfc#2(p)`** - PDOS for Sulfur (S) atom 1, wavefunction 2 (p-orbital).
*   **`MoS2.pdos_atm#2(Mo)_wfc#1(s)`** - PDOS for Molybdenum (Mo) atom 2, wavefunction 1 (s-orbital).
*   **`MoS2.pdos_atm#2(Mo)_wfc#2(p)`** - PDOS for Molybdenum (Mo) atom 2, wavefunction 2 (p-orbital).
*   **`MoS2.pdos_atm#2(Mo)_wfc#3(d)`** - PDOS for Molybdenum (Mo) atom 2, wavefunction 3 (d-orbital).
*   **`MoS2.pdos_atm#2(Mo)_wfc#4(s)`** - PDOS for Molybdenum (Mo) atom 2, wavefunction 4 (s-orbital).
*   **`MoS2.pdos_atm#3(S)_wfc#1(s)`** - PDOS for Sulfur (S) atom 3, wavefunction 1 (s-orbital).
*   **`MoS2.pdos_atm#3(S)_wfc#2(p)`** - PDOS for Sulfur (S) atom 3, wavefunction 2 (p-orbital).

## 🚀 Getting Started

### Prerequisites
To parse and plot this data, you will generally need Python 3.x along with standard scientific computing libraries:

```bash
pip install numpy pandas matplotlib
```

### Usage Example
You can load and visualize the orbital contributions using this basic Python snippet:

```python
import matplotlib.pyplot as plt
import numpy as np

# Example: Load Molybdenum d-orbital PDOS
# Standard format: Energy (eV) | PDOS(E) | Integrated PDOS(E)
data = np.loadtxt("MoS2.pdos_atm#2(Mo)_wfc#3(d)")

energy = data[:, 0]
pdos = data[:, 1]

plt.plot(energy, pdos, label="Mo d-orbital")
plt.xlabel("Energy (eV)")
plt.ylabel("DOS (states/eV)")
plt.title("Projected Density of States")
plt.legend()
plt.show()
```

## 📊 Methodology
The data files describe the localized electronic states of a $\text{MoS}_2$ monolayer or heterostructure. Analyzing the overlap between the Mo $d$-orbitals and S $p$-orbitals allows for the quantification of electronic coupling strengths, bandgap characteristics, and hybridization features.

## 🤝 Contributing
Contributions to analysis scripts, visualization tools, or extra dataset extensions are welcome. 
1. Fork the repository.
2. Create a feature branch (`git checkout -b feature/AnalysisUpdate`).
3. Commit changes (`git commit -m 'Add new plotting script'`).
4. Push to the branch (`git push origin feature/AnalysisUpdate`).
5. Open a Pull Request.

## 📄 License
This project is licensed under the MIT License - see the LICENSE file for details.


