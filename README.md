# Abiogenesis Simulation Project

This project focuses on simulating the chemical steps of abiogenesis using ORCA to optimize molecular geometries and analyze reaction energetics. The simulations investigate various molecular systems and their properties to understand the fundamental processes that may have led to the emergence of life.

## Project Structure

```
.
├── README.md
├── damn/                    # Simulation: Optimization of a diaminomaleonitrile molecule (4 HCN-derived intermediate)
│                           # Purpose: Test whether a known prebiotic intermediate structure is stable and energetically favorable
│                           # Expected Outcome: Optimized bonded structure; compare energy to total of unreacted HCNs
│                           # What to Look For:
│                           # - damn.out: Geometry should be intact; check final energy vs 4HCN
│                           # - Bond lengths should reflect proper C=N and C–C connectivity
├── hcn5/                   # Simulation: Optimization of 5 isolated HCN molecules
│                           # Purpose: Establish a baseline energy and geometry of non-reacting, spatially separated HCN units
│                           # Expected Outcome: No bonding between molecules; serves as a reference system for stability and comparison
│                           # What to Look For:
│                           # - hcn5.out: Check FINAL SINGLE POINT ENERGY for total energy
│                           # - hcn5_trj.xyz: Trajectory to confirm that molecules stay unbonded
├── 4hcn/                   # Simulation: Optimization of 4 isolated HCN molecules (to match atom count in DAMN)
│                           # Purpose: Provide a direct comparison for the DAMN simulation to evaluate energy difference of reaction
│                           # Expected Outcome: No bonding; molecules should remain separate and linear
│                           # What to Look For:
│                           # - 4hcn.out: Use FINAL SINGLE POINT ENERGY to compare against damn.out
│                           # - Subtract to estimate ∆E for reaction favorability
├── intermediates/          # Contains:
│                           # - diaminomaleonitrile.xyz: Hand-built structure used in damn.inp
│                           # - 5HCN_cluster.xyz: Initial cluster used in hcn5.inp
└── orca jobs/
```

The project contains simulation data for different molecular systems, with each system's files organized in its own directory. The `damn` directory contains files related to diaminomaleonitrile simulations, while the `hcn5` directory contains files for HCN cluster simulations. The `intermediates` directory contains key intermediate structures. Additional files and results are stored in the `orca jobs` directory. 