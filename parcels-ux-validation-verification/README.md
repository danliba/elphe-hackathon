# Parcels UX Validation

Verification notebooks for [OceanParcels](https://github.com/parcels-code/parcels) unstructured grid (UXArray) particle tracking.

## Tier 1 — Baseline / Trivial Trajectories

| Notebook | Field | Purpose |
|---|---|---|
| `T1-1_uniform_translation` | Uniform (u=U₀, v=V₀) | Smoke test: basic machinery, ODE integrator, I/O pipeline |
| `T1-2_solid_body_rotation` | Solid-body rotation (u=-Ωy, v=Ωx) | Angular momentum conservation; isolates time integrator on closed orbits |
| `T1-3_solid_body_rotation_3d` | 3D helix (u=-Ωy, v=Ωx, w=W₀) | Extends T1-2 to 3D grid; checks 3D interpolation stencils |
| `T1-4_pure_strain` | Hyperbolic (u=εx, v=-εy) | Exponential divergence; stress-tests integrator near stagnation point |

Each notebook defines velocity fields on both face centers and corner nodes, then tests all compatible interpolator / time integrator combinations against known analytical trajectories.

## Setup

Requires [pixi](https://pixi.sh).

```bash
pixi install
pixi run lab       # JupyterLab
pixi run notebook  # Jupyter Notebook
```

Parcels is installed from the main branch of `github.com/parcels-code/parcels.git`.
