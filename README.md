#HEAD-Local-LSA

Local linear stability analysis (LSA) code for JFM Paper (2025)
This repository contains the FreeFEM implementation used to perform local (temporal) linear stability analysis of swirling base flows, including the computation of direct modes, adjoint modes, and sensitivity fields.

Primary driver:
Master_loop.edp

Developed at:
HEAD Lab, EPFL (2025)
Authors: L. Toledo, E. Yim

1. Main features

Local temporal linear stability analysis (cylindrical coordinates)
Supports analytical and extracted baseflow profiles
Direct and adjoint eigenmodes
Sensitivity analysis
Optional Gaussian baseflow perturbations
Multiple turbulence models
Parametric sweep in azimuthal mode number m and axial wavenumber k

The baseflow is assumed in the following form:
ur = 0
ut = ut(r)
uz = uz(r)

2. How to run
FreeFem++ Master_loop.edp

3. Baseflow configuration
// baseflowType:
// 1 = Draft tube vortex
// 2 = Batchelor vortex
// 3 = Carton–McWilliams vortex

// hasWall: (Draft tube vortex only)
// 0 = No wall damping
// 1 = With wall damping

// idx: (Draft tube vortex only)
// 1 = 0.92 BEP (DC = 0.340)
// 2 = 0.98 BEP (DC = 0.360)
// 3 = 1.00 BEP (DC = 0.368)
// 4 = 1.03 BEP (DC = 0.380)
// 5 = 1.06 BEP (DC = 0.390)
// 6 = 1.11 BEP (DC = 0.410)
// 7 = 0.95 BEP (DC = 0.350) — interpolated

4. Turbulence model configuration
// turbVisc:
// 0 = No turbulence       (nut = 0)
// 1 = k–ε model           (requires turblength)
// 2 = Mixing length model
// 3 = Averaged k–ε nut

// turblength: turbulent length scale (used only if turbVisc = 1)

5. Adjoint and sensitivity options
// adjointFlag:
// 0 = No
// 1 = Yes

// sensFlag:
// 0 = No
// 1 = Yes

6. Baseflow perturbation options
// perturbFlag:
// 0 = No
// 1 = Yes

// perturbType:
// 0 = ur  (radial velocity)
// 1 = ut  (azimuthal velocity)
// 2 = uz  (axial velocity)
// 3 = nut (turbulent viscosity)

// gamma   = width of Gaussian
// rc      = center radius of Gaussian
// epsilon = amplitude of Gaussian perturbation

7. Mode sweep configuration
// mstart, mend : azimuthal mode range
// kstart, kend : axial wavenumber range

// Example:
mstart = 1
mend   = 6
kstart = 0.1
kend   = 25

8. Output

The code generates:
Eigenvalues (growth rate and frequency)
Direct eigenmodes
Adjoint eigenmodes (if enabled)
Sensitivity fields (if enabled)
VTK files for post-processing (ParaView or Tecplot)

9. Paper reference
This code supports the results presented in:

L. Toledo, A. Gesla, and E. Yim (2025)
Local linear stability analysis of swirling draft-tube vortex structures in hydraulic turbines
Journal of Fluid Mechanics (under review)

The final citation and DOI will be added upon acceptance.
