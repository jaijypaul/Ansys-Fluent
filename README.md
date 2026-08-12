# NACA 2412 with Gurney Flap — CFD Study

**Branch:** `gurney-flap`
**Related branch:** `naca2412-baseline` — the unmodified airfoil, used as the comparison reference for this study

## Overview
This branch contains the CFD setup and results for a **NACA 2412 airfoil with a trailing-edge Gurney
flap** (h/c = 1.5%), modeled as a thin, zero-thickness tab perpendicular to the chord on the pressure
side. Steady 2D RANS simulations (k-ω SST) are run across the same angle-of-attack sweep as the
baseline case, for direct comparison.

## Motivation
Gurney flaps are a simple, low-cost passive flow-control device known to increase lift with a modest
drag penalty. This study quantifies that tradeoff for this specific airfoil/flap configuration and
compares it against the unmodified baseline (see the `naca2412-baseline` branch).


## Method Summary
| Parameter | Value |
|---|---|
| Airfoil | NACA 2412 + Gurney flap |
| Flap height (h/c) | 1.5% |
| Flap type | Thin flat tab, perpendicular to chord, pressure side, zero thickness |
| Turbulence model | k-ω SST |
| Domain | C-type, ~15–20c farfield, ~20–25c outlet |
| AoA range | −4° to 16°, 2° steps |
| Solver | Pressure-based, steady, Coupled scheme |

## Status
🚧 In progress — geometry created (flap closure resolved as a separate line edge), meshed, AoA = 0° case solved.
Full AoA sweep in progress; results being added incrementally to `results/cl_cd_data/aoa_sweep_results.csv`.

## Validation
Flap case trend (Cl increase, Cd penalty) compared qualitatively against Gurney flap literature
(e.g., Liebeck 1978 and later CFD studies) — exact magnitudes won't match due to differing
geometry/Re, but the qualitative trend should agree.



