# Aerodynamic Performance Enhancement of NACA 2412 Using a Gurney Flap — ANSYS Fluent CFD Study

## Overview
This repository documents a CFD study comparing the aerodynamic performance of a **baseline NACA
2412 airfoil** against the **same airfoil fitted with a trailing-edge Gurney flap** (h/c = 1.5%).
Steady 2D RANS simulations (k-ω SST turbulence model) are run in ANSYS Fluent across an angle-of-attack
sweep (−4° to 16°) to quantify how the flap affects lift, drag, and stall behavior.

Gurney flaps are a simple, low-cost passive flow-control device — a small tab perpendicular to the
chord at the trailing edge — known to increase lift at the cost of some added drag. This project
computationally validates that behavior for this specific airfoil and quantifies the tradeoff.

## Repository Layout
This project is organized as **two branches**, one per configuration, so each case's geometry, mesh,
solver setup, and results can be tracked independently without one overwriting the other:

| Branch | Contents |
|---|---|
| [`naca2412-baseline`](../../tree/naca2412-baseline) | Unmodified NACA 2412 airfoil — the reference case |
| [`gurney-flap`](../../tree/gurney-flap) | Same airfoil with a Gurney flap added at the trailing edge |

Each branch has its own README with full setup details, method summary, and results specific to that
configuration. This main branch serves as the entry point and holds the overall comparison once both
branches' sweeps are complete.

## Motivation
Before committing to a full geometry redesign for lift enhancement, it's worth understanding what a
minimal, low-cost passive modification (a flap that's ~1.5% of the chord in height) can achieve on its
own. This is also a useful bridge between classical CFD workflows and the broader flow-control
literature — later extensions of this idea (not covered here) include optimizing flap height/position,
or using machine-learning-based surrogate models to predict flap performance without rerunning full
CFD for every configuration.

## Method Summary (common to both branches)
| Parameter | Value |
|---|---|
| Airfoil | NACA 2412 |
| Turbulence model | k-ω SST |
| Domain | C-type, ~15–20c farfield, ~20–25c outlet |

| AoA range | −4° to 16°, 2° steps |
| Solver | Pressure-based, steady, Coupled scheme |

## Status
🚧 In progress
- `naca2412-baseline`: geometry + mesh complete, AoA = 0° solved, full sweep in progress
- `gurney-flap`: geometry + mesh complete, AoA = 0° solved, full sweep in progress
- Cross-branch comparison plots (Cl-α, Cd-α, Cl/Cd-α, both cases overlaid) to be added here once both
  sweeps are complete

## Planned Final Comparison (to be added here)
- Cl vs AoA — baseline vs. flap, overlaid
- Cd vs AoA — baseline vs. flap, overlaid
- Cl/Cd vs AoA — efficiency tradeoff
- Cp distribution comparison at representative AoA
- Flow visualization: counter-rotating vortex pair behind the flap
- Validation of baseline against NACA 2412 experimental/XFOIL data

## Author
Jaijy Paul — M.Tech, Thermal and Fluids Engineering, IIT Bombay, supervised by Prof. Rajneesh Bhardwaj
