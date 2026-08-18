# FRESEAN-SVD

A scalable singular value decomposition implementation of FRESEAN mode analysis
for frequency-resolved characterization of collective dynamics in intact virus
capsids and other large macromolecular assemblies.

## What is here

- `FRESEAN-svd.ipynb` - annotated notebook running the full pipeline on the
  alanine dipeptide from the Heyden lab FRESEAN tutorial: windowed velocity FFTs,
  disk-backed block FFTs, and per-frequency modes via SVD.
- `unwrap.py`, `align.py`, `graphics.py`, `ctypes/` - helper modules and their C
  libraries, from the Heyden lab FRESEAN tutorial (see Third-party code).
- `fresean_svd_ala_out/` - example output (VDoS, per-bin modes, plots).

## Method in brief

The analysis works on velocities. For each frequency bin it stacks the
per-block velocity spectra into a matrix F (nDOF x nBlocks), then extracts the
dominant collective modes as the left singular vectors of F.

## Requirements

- Python 3 with: numpy, scipy, matplotlib, MDAnalysis, psutil

## Usage

Clone the repository:

    git clone https://github.com/Hadden-lab/FRESEAN-SVD.git

The alanine dipeptide trajectory (`traj.trr`, ~154 MB) exceeds GitHub's file size
limit and is not stored here. The notebook downloads the topology and trajectory
automatically on first run. Both originate from the Heyden lab FRESEAN tutorial:

    https://github.com/HeydenLabASU-collab/FRESEAN-tutorial

## Third-party code

`unwrap.py`, `align.py`, `graphics.py`, and the contents of `ctypes/` are from the
Heyden lab FRESEAN tutorial, released under the MIT License
(Copyright (c) 2025 Matthias Heyden). Their MIT license text is retained in
`LICENSE.Heyden`. The SVD pipeline and the annotated notebook are original to this
repository.

## Author

Anjali Krishna, University of Delaware, 2026
