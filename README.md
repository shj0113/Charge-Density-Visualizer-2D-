# Charge Density Visualizer (2D)
Visualize 2D charge density difference maps from VASP calculations

📖 Overview
This project provides a simple way to visualize charge density difference data in 2D using Python.
The script is designed for rectangular (orthorhombic) cells only and supports visualization along three different directions.

⚡ Features
- Visualize 2D charge density difference maps.
- Slice atomic positions to selectively plot atoms, or plot all atoms.
- Separate atomic data into element-specific DataFrames (based on POSCAR).
- Adjustable color bar range (vmin, vmax) based on dataset min/max values.
- Atom plotting aligned with the chosen axis (x, y, or z).

🛠 Requirements
- Python 3.x
- NumPy
- Matplotlib
- (Optional) Scipy – for RBF interpolation (not recommended for sparse k-points due to high computational cost).

🚀 Usage
1. Download and open the Jupyter notebook:
Charge density difference.ipynb

2. Modify the following sections before running:
File path to your charge density difference data.
Atom selection: choose atoms to be plotted based on position.
Element-based DataFrames: rename according to the elements in POSCAR.
Color bar range: adjust vmin and vmax.
Plot direction: set axis (x, y, or z).

3. Run the notebook to generate the 2D plots.

📌 Notes
For sparse k-point grids, RBF interpolation can be used, but it is computationally expensive.
👉 Instead, it is recommended to increase the k-point density and recalculate.
