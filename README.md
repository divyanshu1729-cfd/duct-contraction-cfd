# duct-contraction-cfd
Documentation and report for a comparative CFD study of asymmetric duct contractions using OpenFOAM. It's a technical draft, not peer-reviewed.
# Irreversible-Loss Reduction in Asymmetric Duct Contractions

**Status:** Technical draft — not peer-reviewed  
**Solver:** OpenFOAM (`simpleFoam`)  
**Flow regime:** Steady, incompressible, laminar flow

## Overview

This project investigates the influence of wall-transition geometry on steady laminar flow through an asymmetric duct contraction. Three geometries are compared:

1. A sudden contraction with an abrupt change in the upper wall.
2. A cosine-bell transition designed to provide continuous wall slope.
3. A cubic Bézier transition with horizontal tangency at its endpoints.

The study uses computational fluid dynamics (CFD) to examine kinematic pressure, velocity fields, wall shear stress, flow separation, and grid sensitivity.

## Geometry and Flow Parameters

The current report specifies the following parameters:

| Parameter | Value |
|---|---:|
| Inlet height | 40 mm |
| Outlet height | 18 mm |
| Spanwise width | 20 mm |
| Total axial length | 150 mm |
| Inlet velocity | 1 m/s |
| Fluid density | 870 kg/m³ |
| Dynamic viscosity | 0.1 Pa·s |
| Reported inlet Reynolds number | Approximately 232 |

The flow is treated as steady, incompressible, Newtonian, and laminar.

## Numerical Methodology

The report describes simulations using OpenFOAM's `simpleFoam` solver. Geometry was developed using FreeCAD, with meshing described as a hexahedral-dominant workflow using cfMesh.

A three-level mesh-sensitivity study was reported, using maximum mesh edge lengths of 1.0 mm, 0.7 mm, and 0.5 mm. The report presents Richardson extrapolation and Grid Convergence Index (GCI) calculations for the kinematic-pressure metric.

The reported fine-grid cell counts are approximately 784,000 for each geometry, or approximately 2.36 million cells across the three fine-grid geometries combined.

## Results Reported in the Draft

The report gives the following fine-grid kinematic-pressure values at its specified measurement plane:

| Geometry | Kinematic pressure (m²/s²) |
|---|---:|
| Sudden contraction | 6.42 |
| Cosine-bell transition | 5.19 |
| Cubic Bézier transition | 4.88 |

The draft also reports a 2.97% difference between the cosine-bell and cubic Bézier cases in an outlet kinetic-energy-related metric. It argues that a lower kinematic-pressure value alone is insufficient to establish that a geometry is hydraulically more efficient.

These findings reflect the current report and should be treated as preliminary until the extraction methodology, definitions, units, and numerical calculations have been independently reviewed.

## Repository Contents

- `duct_LaTeX(3)_compressed.pdf` — Compressed PDF report.
- `duct_LaTeX.tex` — LaTeX source of the report.

## Reproducibility Status

The original OpenFOAM case dictionaries, meshes, CAD source files, and post-processing scripts are not currently included in this repository. The report also references external figure files and a bibliography file that must be supplied to make the LaTeX source self-contained.

**Consequently, this repository currently documents the study but does not yet provide a complete, runnable CFD case.** Any future reconstructed dictionaries will be identified as reconstructed rather than represented as the original simulation inputs.

## Limitations and Future Work

The report identifies several limitations:

- The simulations are restricted to a steady laminar regime.
- The Bézier control points were not subjected to a formal geometric optimization.
- Experimental validation was not performed.
- The results depend on the selected measurement planes and the reported numerical methodology.

Potential extensions include reviewing the energy-balance calculations, recovering or reconstructing the missing case files, conducting additional verification, and comparing the results with experimental measurements.

## Disclaimer

This is an undergraduate computational study presented as a technical draft. Its numerical results and physical interpretations have not been independently validated or peer-reviewed. The repository will be updated as supporting files and verification become available.
