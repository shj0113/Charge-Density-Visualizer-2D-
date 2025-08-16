# Charge Density Visualizer (2D)
Visualize 2D charge density difference maps from VASP calculations

## 📖 Overview
This project provides a simple way to visualize charge density difference data in 2D using Python.
The script is designed for **orthorhombic cells** only and supports visualization along three different directions.
<img width="1545" height="428" alt="image" src="https://github.com/user-attachments/assets/69faa57a-6ab6-41a3-9b3e-bbc988cd99db" />


## ⚡ Features
- Visualize 2D charge density difference maps.
- Slice atomic positions to selectively plot atoms, or plot all atoms.
- Separate atomic data into element-specific DataFrames (based on POSCAR).
- Adjustable color bar range (vmin, vmax) based on dataset min/max values.
- Atom plotting aligned with the chosen axis (x, y, or z).

## 🚀 Usage
1. Download and open the Jupyter notebook

2. Modify the following sections before running:
  1) File path to your charge density difference data.
```
path_AB = '/home/shj/PbS_ligand_effect/100/pentDT/total' 
path_A = '/home/shj/PbS_ligand_effect/100/pentDT/surf' 
path_B = '/home/shj/PbS_ligand_effect/100/pentDT/ligand'
```

  2) Atom selection: choose atoms to be plotted based on position.
```
df_atomic_position = df_atomic_position[((4 < df_atomic_position['y']) & (df_atomic_position['y'] < 7)) | (12 < df_atomic_position['z'])]
df_atomic_position = df_atomic_position[((5 < df_atomic_position['y']) & (df_atomic_position['y'] < 7) & (13 > df_atomic_position['y'])) | (13 < df_atomic_position['z'])]
df_atomic_positiondf_atomic_position[((5 < df_atomic_position['y']) & (df_atomic_position['y'] < 7) & (13 > df_atomic_position['y'])) | (13 < df_atomic_position['z'])]
```

  3) Element-based DataFrames: rename according to the elements in POSCAR.
```
H_df = tag_dataframes['H']
Pb_df = tag_dataframes['Pb']
C_df = tag_dataframes['C']
O_df = tag_dataframes['O']
S_df = tag_dataframes['S']
```

  4) Color bar range: adjust vmin and vmax.
    (print('min: ', min(Z.ravel())), print('max: ', max(Z.ravel())))
```
vmin = -0.015
vmax = 0.015
```
 
  5) Plot direction: set axis (x, y, or z).
```
ax.scatter(H_df['x'], H_df['z'], s=50,facecolors="#00FFDD", edgecolors='black', lw=lw, label='H')
ax.scatter(Pb_df['x'], Pb_df['z'], s=300,facecolors="#4137E7", edgecolors='black', lw=lw, label='Pb')
ax.scatter(S_df['x'], S_df['z'], s=150,facecolors="#F4E407", edgecolors='black', lw=lw, label='S')
ax.scatter(C_df['x'], C_df['z'], s=150,facecolors="#E83B3B", edgecolors='black', lw=lw, label='C')
ax.scatter(O_df['y'], O_df['z'], s=150,facecolors="#FF0F4A", edgecolors='black', lw=lw, label='O')
```

4. Run the notebook to generate the 2D plots.
<img width="3305" height="1348" alt="그림1" src="https://github.com/user-attachments/assets/e6db572f-647c-4309-b729-fc68c98e82ef" />


## 📌 Notes
For sparse k-point grids, RBF interpolation can be used, but it is computationally expensive.
👉 Instead, it is recommended to increase the k-point density and recalculate.


