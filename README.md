# Abiogenesis Simulation Project

This project focuses on simulating the chemical steps of abiogenesis using ORCA to optimize molecular geometries and analyze reaction energetics. The simulations investigate various molecular systems and their properties to understand the fundamental processes that may have led to the emergence of life.

## Project Structure

```
.
├── README.md
├── research.txt            # Findings
├── simulations/           # All simulation directories
│   ├── damn/             # Simulation: Optimization of a diaminomaleonitrile molecule (4 HCN-derived intermediate)
│   │                     # Purpose: Test whether a known prebiotic intermediate structure is stable and energetically favorable
│   │                     # Expected Outcome: Optimized bonded structure; compare energy to total of unreacted HCNs
│   │                     # What to Look For:
│   │                     # - damn.out: Geometry should be intact; check final energy vs 4HCN
│   │                     # - Bond lengths should reflect proper C=N and C–C connectivity
│   │                     # - damn.out: Geometry should be intact; check final energy vs 4HCN
│   │                     # - Bond lengths should reflect proper C=N and C–C connectivity
│   ├── hcn5/            # Simulation: Optimization of 5 isolated HCN molecules
│   │                     # Purpose: Establish a baseline energy and geometry of non-reacting, spatially separated HCN units
│   │                     # Expected Outcome: No bonding between molecules; serves as a reference system for stability and comparison
│   │                     # What to Look For:
│   │                     # - hcn5.out: Check FINAL SINGLE POINT ENERGY for total energy
│   │                     # - hcn5_trj.xyz: Trajectory to confirm that molecules stay unbonded
│   ├── 4hcn/            # Simulation: Optimization of 4 isolated HCN molecules (to match atom count in DAMN)
│   │                     # Purpose: Provide a direct comparison for the DAMN simulation to evaluate energy difference of reaction
│   │                     # Expected Outcome: No bonding; molecules should remain separate and linear
│   │                     # What to Look For:
│   │                     # - 4hcn.out: Use FINAL SINGLE POINT ENERGY to compare against damn.out
│   │                     # - Subtract to estimate ∆E for reaction favorability
│   ├── amn/             # Simulation: Optimization of aminomalononitrile molecule
│   │                     # Purpose: Test stability of AMN as a potential intermediate
│   │                     # Expected Outcome: Optimized structure with intact geometry
│   │                     # What to Look For:
│   │                     # - amn.out: Check FINAL SINGLE POINT ENERGY and geometry
│   │                     # - Compare energy with 3HCN+NH3 for reaction thermodynamics
│   ├── amn_solvent_dft/ # Simulation: AMN optimization with DFT and water solvation
│   │                     # Purpose: Evaluate solvent effects on AMN stability
│   │                     # Expected Outcome: Slightly modified geometry due to solvation
│   │                     # What to Look For:
│   │                     # - amn_solvent_dft.out: Compare energy with vacuum calculation
│   │                     # - Check geometry changes from vacuum structure
│   ├── 3hcn_nh3/        # Simulation: Optimization of 3 HCN + NH₃ cluster
│   │                     # Purpose: Study potential formation of AMN from simpler precursors
│   │                     # Expected Outcome: Non-bonded cluster of reactants
│   │                     # What to Look For:
│   │                     # - 3hcn_nh3.out: Check FINAL SINGLE POINT ENERGY
│   │                     # - Trajectory to confirm no spontaneous bonding
│   ├── 3hcn_nh3_solvent_dft/ # Simulation: 3HCN+NH3 cluster with DFT and water solvation
│   │                     # Purpose: Study solvent effects on reactant cluster
│   │                     # Expected Outcome: Non-bonded cluster with possible geometry changes
│   │                     # What to Look For:
│   │                     # - 3hcn_nh3_solvent_dft.out: Compare energy with vacuum calculation
│   │                     # - Check if solvation affects molecular spacing
│   └── intermediates/    # Contains:
│                         # - diaminomaleonitrile.xyz: Hand-built structure used in damn.inp
│                         # - 5HCN_cluster.xyz: Initial cluster used in hcn5.inp
└── orca jobs/
```

The project contains simulation data for different molecular systems, with each system's files organized in its own directory under the `simulations/` directory. The `damn` directory contains files related to diaminomaleonitrile simulations, while the `hcn5` directory contains files for HCN cluster simulations. The `intermediates` directory contains key intermediate structures. Additional files and results are stored in the `orca jobs` directory. 