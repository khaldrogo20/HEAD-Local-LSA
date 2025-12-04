# HEAD-Local-LSA
Code for JFM Paper 2025
// ===============================================================================================================
// Run: FreeFem++ Master_loop.edp
// Driver script for temporal LSA (direct + adjoint + sensitivity)
// Code credits: HEAD Lab. EPFL, 2025 (L. Toledo, E. Yim) 
// Code details: Local linear stability analysis for arbitrary baseflow (ur = 0; ut = ut(r); uz = uz(r);) 
// ===============================================================================================================

// -----------------------------
// BASEFLOW CONFIGURATION
// -----------------------------
// baseflowType: Select baseflow profile
//   1 = Draft tube vortex
//   2 = Batchelor vortex
//   3 = Carton-Mcwilliams vortex

// hasWall: Wall damping for Draft tube vortex
//   0 = No wall damping
//   1 = Include wall damping

// idx: Turbine vortex profile index (only for Draft tube vortex)
//   1 = 0.92 BEP (DC = 0.340)
//   2 = 0.98 BEP (DC = 0.360)
//   3 = 1.00 BEP (DC = 0.368)
//   4 = 1.03 BEP (DC = 0.380)
//   5 = 1.06 BEP (DC = 0.390)
//   6 = 1.11 BEP (DC = 0.410)
//   7 = 0.95 BEP (DC = 0.350) - interpolated

// -----------------------------
// TURBULENCE MODEL CONFIGURATION
// -----------------------------
// turbVisc: Turbulent viscosity model
//   0 = No turbulence (nut = 0)
//   1 = k-epsilon model (requires turblength)
//   2 = Mixing length model
//   3 = Averaged k-eps nut

// turblength: Turbulent length scale (used only if turbVisc == 1)

// -----------------------------
// ADJOINT AND SENSITIVITY FLAGS
// -----------------------------
// adjointFlag: Solve adjoint equations
//   0 = No
//   1 = Yes

// sensFlag: Solve sensitivity equations
//   0 = No
//   1 = Yes

// -----------------------------
// BASEFLOW PERTURBATION CONFIGURATION
// -----------------------------
// perturbFlag: Apply Gaussian perturbation
//   0 = No
//   1 = Yes

// perturbType: Perturbation variable
//   0 = ur (radial velocity)
//   1 = ut (azimuthal velocity)
//   2 = uz (axial velocity)
//   3 = nut (turbulent viscosity)

// gamma: Width of Gaussian perturbation
// rc: Center of Gaussian perturbation
// epsilon: Magnitude of Gaussian perturbation

// -----------------------------
// MODE SWEEP CONFIGURATION
// -----------------------------
// mstart, mend: Azimuthal mode range
// kstart, kend: Axial wavenumber range
