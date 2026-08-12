# NACA 2412 — Baseline Airfoil CFD Study

**Branch:** `naca2412-baseline`
**Related branch:** `gurney-flap` — same airfoil with a trailing-edge Gurney flap added, for comparison

## Overview
This branch contains the CFD setup and results for the **unmodified NACA 2412 airfoil**, used as the
baseline against which the Gurney flap configuration (see the `gurney-flap` branch) is compared.
Steady 2D RANS simulations (k-ω SST) are run across an angle-of-attack sweep in ANSYS Fluent.

## Why a baseline case
Before evaluating whether a Gurney flap improves performance, the unmodified airfoil's own
lift/drag behavior needs to be established and validated against known NACA 2412 data. This branch
is that reference case.


## Method Summary
| Parameter | Value |
|---|---|
| Airfoil | NACA 2412 (unmodified) |
| Turbulence model | k-ω SST |
| Domain | C-type, ~15–20c farfield, ~20–25c outlet |
| AoA range | −4° to 16°, 2° steps | --- need to do
| Solver | Pressure-based, steady, Coupled scheme |

## Status
🚧 In progress — geometry created, meshed, AoA = 0° case solved.
Full AoA sweep in progress; results being added incrementally to `results/cl_cd_data/aoa_sweep_results.csv`.


## Validation
Cl-α curve compared against known NACA 2412 experimental/XFOIL data.

## How to Reproduce
1. Import curve files from `geometry/` into DesignModeler/SpaceClaim (Concept → 3D Curve → From Coordinates File)
2. Generate the closed airfoil surface (Concept → Surfaces From Edges)
3. Build the enclosure/farfield domain and mesh per settings in `mesh_journal/`
4. Set up Fluent per `fluent_journal/` (or replay the journal directly)
5. Sweep AoA by updating the Velocity Inlet X/Y components and force-coefficient direction vectors for each run

## Author
*(your name)* — M.Tech, Thermal and Fluids Engineering, IIT Bombay
