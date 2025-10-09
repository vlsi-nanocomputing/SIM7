# MolPDK-SIM(7)
This repository provids the first fully simulated 7-cell MolFCN standard-cell library (SIM7), which is part of the The-OpenSource-MolPDK Public for Molecular Field-Coupled Nanocomputing technology. This work is obtained with a collaboration between between the [Quantum and Nanosystem (QNANO)](https://www.vlsilab.polito.it/) at [Politecnico di Torino](https://www.polito.it/) (Italy) and the [Chair for Design Automation](https://www.cda.cit.tum.de/) at the [Technical University of Munich](https://www.tum.de/) (Germany).

## PDK Description

The SIM(7) library is based on a uniform 10 × 10 molecular cell grid (400 nm²) with dedicated and fixed pin locations across all cells. This uniformity enables compatibility with state-of-the-art FCN physical design algorithms (e.g., the fiction framework) and supports automated placement and routing. All layouts were designed using MagCAD as the layout environment. The 10 × 10 size was selected to provide sufficient area for implementing the required logic and clocking elements, while minimising crosstalk between adjacent cells.

The library includes:

* Logic primitives: AND, OR, Majority voter, and Inverter
* Interconnect elements: wires, L-shaped wires, and fan-out structures

Each standard cell integrates the required four-phase FCN clocking scheme, ensuring correct information propagation across devices.

All devices are verified with the SCERPA tool using an ideal molecule. This choice avoids molecule-dependent layouts and ensures consistent behavior across the library. The intermolecular distance was fixed to 1 nm.

## Download/Installation and structure of the library
The library can be downloaded with the command:

```
git clone https://github.com/vlsi-nanocomputing/SIM7.git
```

The downloaded file will contain all the 7 library elements (AND, OR, Majority Voter, Inverter, wires, L-shaped wires, and fan-out structures) with different rotations and in different configurations (i.e. different position of constants for AND/OR gates and different orientations for L and T interconnections).

```bash
SIM7/
├── AND/
│   ├── 0_AND_dw.qll # MV-based AND gate with 0° rotation and constant input '0' directed downward
│   ├── 0_AND_lh.qll # MV-based AND gate with 0° rotation and constant input '0' on the left-hand side
│   ├── 0_AND_up.qll # MV-based AND gate with 0° rotation and constant input '0' directed upward
│   ├── 1_AND_dw.qll # MV-based AND gate with 90° rotation and constant input '0' directed downward
│   ├── 1_AND_lh.qll # MV-based AND gate with 90° rotation and constant input '0' on the left-hand side
│   ├── 1_AND_up.qll # MV-based AND gate with 90° rotation and constant input '0' directed upward
│   ├── 2_AND_dw.qll # MV-based AND gate with 180° rotation and constant input '0' directed downward
│   ├── 2_AND_lh.qll # MV-based AND gate with 180° rotation and constant input '0' on the left-hand side
│   ├── 2_AND_up.qll # MV-based AND gate with 180° rotation and constant input '0' directed upward
│   ├── 3_AND_dw.qll # MV-based AND gate with 270° rotation and constant input '0' directed downward
│   ├── 3_AND_lh.qll # MV-based AND gate with 270° rotation and constant input '0' on the left-hand side
│   └── 3_AND_up.qll # MV-based AND gate with 270° rotation and constant input '0' directed upwar 
├── OR/        
│   ├── 0_OR_dw.qll	# MV-based OR gate with 0° rotation and constant input '1' directed downward
│   ├── 0_OR_lh.qll	# MV-based OR gate with 0° rotation and constant input '1' on the left-hand side
│   ├── 0_OR_up.qll	# MV-based OR gate with 0° rotation and constant input '1' directed upward
│   ├── 1_OR_dw.qll	# MV-based OR gate with 90° rotation and constant input '1' directed downward
│   ├── 1_OR_lh.qll	# MV-based OR gate with 90° rotation and constant input '1' on the left-hand side
│   ├── 1_OR_up.qll	# MV-based OR gate with 90° rotation and constant input '1' directed upward
│   ├── 2_OR_dw.qll	# MV-based OR gate with 180° rotation and constant input '1' directed downward
│   ├── 2_OR_lh.qll	# MV-based OR gate with 180° rotation and constant input '1' on the left-hand side
│   ├── 2_OR_up.qll	# MV-based OR gate with 180° rotation and constant input '1' directed upward
│   ├── 2_OR_dw.qll	# MV-based OR gate with 270° rotation and constant input '1' directed downward
│   ├── 2_OR_lh.qll	# MV-based OR gate with 270° rotation and constant input '1' on the left-hand side
│   └── 2_OR_up.qll	# MV-based OR gate with 270° rotation and constant input '1' directed upwar 
├── MV/        
│   ├── 0_MV.qll # 3-input Majority Voter gate at 0° rotation
│   ├── 1_MV.qll # 3-input Majority Voter gate at 90° rotation
│   ├── 2_MV.qll # 3-input Majority Voter gate at 180° rotation
│   └── 3_MV.qll # 3-input Majority Voter gate at 270° rotation 
├── INVERTER/ 
│   ├── inv_horizontal_dx.qll # Inverter at 0° rotation
│   ├── inv_horizontal_dw.qll # Inverter rotated by 90°
│   ├── inv_horizontal_lh.qll # Inverter rotated by 180°
│   └── inv_horizontal_up.qll # Inverter rotated by 270° 
├── BUS/ 
│   ├── bus_horizontal_dx.qll # Straight bus tile at 0° rotation
│   ├── bus_horizontal_dw.qll # Straight bus tile at 90° rotation
│   ├── bus_horizontal_lh.qll # Straight bus tile at 180° rotation
│   └── bus_horizontal_up.qll # Straight bus tile at 270° rotation 
├── LWIRE_DXDW/ 
│   ├── 0_Lwire_dxdw.qll # L-shaped wire tile routing signal diagonally downward at 0° rotation
│   ├── 1_Lwire_dxdw.qll # L-shaped wire tile routing diagonally downward, rotated 90°
│   ├── 2_Lwire_dxdw.qll # L-shaped wire tile routing diagonally downward, rotated 180°
│   └── 3_Lwire_dxdw.qll # L-shaped wire tile routing diagonally downward, rotated 270° 
├── LWIRE_DXUP/
│   ├── 0_Lwire_dxup.qll # L-shaped wire tile routing signal diagonally upward at 0° rotation
│   ├── 1_Lwire_dxup.qll # L-shaped wire tile routing diagonally upward, rotated 90°
│   ├── 2_Lwire_dxup.qll # L-shaped wire tile routing diagonally upward, rotated 180°
│   └── 3_Lwire_dxup.qll # L-shaped wire tile routing diagonally upward, rotated 270° 
├── T_dxdw/
│   ├── 0_T_dxdw.qll # T-shaped interconnect, diagonal down, 0° rotation
│   ├── 1_T_dxdw.qll # T-shaped interconnect, diagonal down, 90° rotation
│   ├── 2_T_dxdw.qll # T-shaped interconnect, diagonal down, 180° rotation
│   └── 3_T_dxdw.qll # T-shaped interconnect, diagonal down, 270° rotation 
├── T_dxup/
│   ├── 0_T_dxup.qll # T-shaped interconnect, diagonal up, 0° rotation
│   ├── 1_T_dxup.qll # T-shaped interconnect, diagonal up, 90° rotation
│   ├── 2_T_dxup.qll # T-shaped interconnect, diagonal up, 180° rotation
│   └── 3_T_dxup.qll # T-shaped interconnect, diagonal up, 270° rotation 
└── T_updw/
    ├── 0_T_updw.qll # T-shaped interconnect, vertical up/down, 0° rotation
    ├── 1_T_updw.qll # T-shaped interconnect, vertical up/down, 90° rotation
    ├── 2_T_updw.qll # T-shaped interconnect, vertical up/down, 180° rotation
    └── 3_T_updw.qll # T-shaped interconnect, vertical up/down, 270° rotation

```

## Required tools

The library can be viewed with MagCAD, simulated with SCERPA, and used to automatic design circuits with fiction:

### MagCAD tool

This tool, developed by Politecnico di Torino (Turin, Italy), can be used to open/edit the layout of Molecular FCN layouts. MagCAD is part of the [ToPoliNano project](https://topolinano.polito.it/the-project/). The SIM(7) is fully compatible with the MagCAD tool. The tool is free of charge. Instructions for downloading, installing, and using MagCAD  can be found on the official [website](https://topolinano.polito.it/the-project/).

### SCERPA tool

This tool, developed by Politecnico di Torino (Turin, Italy), can be used to simulate Molecular FCN devices. The SIM(7) is fully compatible with the SCERPA tool. The tool is  available on [zenodo](https://zenodo.org/records/7457038) and can be downloaded free of charge on [github](https://github.com/vlsi-nanocomputing/SCERPA.git)
with:

```bash
git clone https://github.com/vlsi-nanocomputing/SCERPA.git
```

This tool requires a working version of [MATLAB](https://www.mathworks.com/products/matlab.html).

### Fiction tool

This tool, developed by Technische Universität München (Munich, Germany), can be used to automatically generate Molecular FCN layouts. The SIM(7) is fully compatible with the Fiction tool. Instructions for downloading, installing, and using Fiction framework can be found on the official [github](https://github.com/cda-tum/fiction).

# Contributors

The Physical Design Kit SIM(7) was developed by Benjamin Hien (TUM), Danilo Quinci (POLITO), Yuri Ardesi (POLITO), Giuliana Beretta (POLITO), Federico Ravera (POLITO), Marcel Walter (TUM), Robert Wille (TUM).

# Citation

If you use SIM(7), please cite the associated conference paper presented at IEEE-LANANO 2025:

```
B. Hien et al., "Bridging the Gap Between Molecular FCN and Design Automation with SIM(7)-MolPDK: A Physically Simulated Standard-Cell Library," 2025 IEEE Latin American Conference on Nanotechnology (IEEE-LANANO), Cusco, Peru, 2025, pp. -, doi: -.
```

Also available in the BibTeX format:

```
@inproceedings{sim7,
    author = {Hien, Benjamin and Quinci, Danilo and Ardesi, Yuri and Beretta, Giuliana and Ravera, Federico and Walter, Marcel and Wille, Robert},
    title = {Bridging the Gap Between Molecular FCN and Design Automation with SIM(7)-MolPDK: A Physically Simulated Standard-Cell Library},
    booktitle = {2025 IEEE Latin American Conference on Nanotechnology (IEEE-LANANO)},
    year = {2025},
    doi={-}
}
```

Citations for the single tools (SCERPA, fiction, MAGCAD) can be found in their website. 