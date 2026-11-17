# Barnard 68: Morpho-kinematic Evolution and Spline Analysis

A kinematic particle model of the dark globule Barnard 68 colliding with a small companion core (the scenario of Burkert & Alves 2009). The model is turned into synthetic observations, which are then measured with splines.

## Pipeline

1. Builds a 3-D cloud of about 75 700 particles with a Bonnor-Ebert density profile and a companion globule.
2. Moves the particles with a prescribed velocity field (impact, tail compression, inside-out infall, rotation), integrated with RK4 over 0.4 Myr.
3. Produces extinction maps, an optical view, moment maps, PV diagrams and spectra.
4. Measures the maps with splines: boundary curvature, the companion peak and neck, the radial slope, and the velocity gradient. From the images alone it recovers the input approach speed (0.349 vs 0.335 km/s) and rotation (0.61 vs 0.60 km/s/pc).
5. Exports snapshots for ParaView.

## Requirements

Python 3.10+, NumPy ≥ 2.0, SciPy ≥ 1.10, Matplotlib, contourpy, Pillow, Jupyter. h5py is optional and only needed for the ParaView export.

```bash
pip install numpy scipy matplotlib contourpy pillow h5py jupyter
```

## Running

```bash
jupyter notebook barnard68_morphokinematics_paper.ipynb
```

## Output

- `b68_evolution.gif`: animation of the extinction and the velocity centroid
- `b68_snapshots/`: HDF5 snapshots plus `b68_evolution.xdmf`, which you can open in ParaView (Xdmf3 reader) as a time series
