# Abiogenesis Simulation Project

This project focuses on simulating the chemical steps of abiogenesis using ORCA to optimize molecular geometries and analyze reaction energetics. The simulations investigate various molecular systems and their properties to understand the fundamental processes that may have led to the emergence of life.

## Project Structure

```
.
├── README.md
├── damn/
│   ├── damn.inp
│   ├── damn.out
│   ├── damn.xyz
│   ├── damn_trj.xyz
│   ├── damn.opt
│   ├── damn.engrad
│   ├── damn.gbw
│   ├── damn.densities
│   ├── damn.densitiesinfo
│   ├── damn.property.txt
│   └── damn.bibtex
├── hcn5/
│   ├── hcn5.inp
│   ├── hcn5.out
│   ├── hcn5.xyz
│   ├── hcn5_trj.xyz
│   ├── hcn5.opt
│   ├── hcn5.engrad
│   ├── hcn5.gbw
│   ├── hcn5.carthess
│   ├── hcn5.densities
│   ├── hcn5.densitiesinfo
│   ├── hcn5.property.txt
│   └── hcn5.bibtex
├── intermediates/
│   ├── diaminomaleonitrile.xyz
│   └── 5HCN_cluster.xyz
└── orca jobs/
```

The project contains simulation data for different molecular systems, with each system's files organized in its own directory. The `damn` directory contains files related to diaminomaleonitrile simulations, while the `hcn5` directory contains files for HCN cluster simulations. The `intermediates` directory contains key intermediate structures. Additional files and results are stored in the `orca jobs` directory. 