# Magnetic Reconnection within Mature Kelvin–Helmholtz Structures at the Distant Dawnside Magnetopause

This repository contains the analysis code supporting the manuscript:

**C. L. Lentz, S. Eriksson, N. Ahmadi, and D. N. Baker**  
*Magnetic Reconnection within Mature Kelvin–Helmholtz Structures at the Distant Dawnside Magnetopause*  
Submitted to **Journal of Geophysical Research: Space Physics**

## Overview

The Kelvin–Helmholtz instability (KHI) is an important mechanism for transferring mass and energy across Earth's magnetopause. This study examines magnetic reconnection embedded within mature Kelvin–Helmholtz structures observed by NASA's Magnetospheric Multiscale (MMS) mission at the distant dawnside magnetopause.

Between **17 June 2020 and 18 June 2020**, MMS observed approximately **4.5 hours of Kelvin–Helmholtz wave activity** near average GSE coordinates of approximately

\[
(x, y, z)_{GSE} = (-18.2, -21.3, 3.4)\,R_E.
\]

The analysis identifies **15 current sheets** with signatures consistent with magnetic reconnection:

- **6 leading-edge events**
- **7 trailing-edge events**
- **2 unclassified events** associated with rapid plasma-regime switchbacks

The observations show that reconnection can remain active within mature Kelvin–Helmholtz structures far down the magnetopause flank and can occur at both leading and trailing boundaries.

## Repository Contents

The notebooks and scripts in this repository are used to reproduce the analysis presented in the manuscript. Depending on the current repository structure, these may include workflows for:

- Loading MMS burst-mode data with PySPEDAS
- Processing FGM magnetic-field measurements
- Processing FPI ion and electron moments
- Processing EDP electric-field measurements
- Converting MMS measurements from GSE coordinates into local LMN coordinates
- Time-aligning measurements from multiple MMS instruments
- Identifying Kelvin–Helmholtz current-sheet crossings
- Calculating current-sheet properties and plasma parameters
- Evaluating ion exhaust jets
- Performing Walén relation comparisons
- Evaluating nonlinear Kelvin–Helmholtz signatures
- Estimating Kelvin–Helmholtz wavelength
- Calculating reconnection-related quantities such as electron-frame energy dissipation, \(D_e\)
- Generating manuscript figures

## Data

This project uses observations from the **Magnetospheric Multiscale (MMS)** mission.

Primary instruments include:

- **FGM — Fluxgate Magnetometer**
  - Magnetic-field measurements

- **FPI — Fast Plasma Investigation**
  - DIS ion moments and distributions
  - DES electron moments and distributions

- **EDP — Electric Double Probe**
  - Electric-field measurements

The primary event interval is:

**2020-06-17 to 2020-06-18 UTC**

with MMS burst-mode measurements used for detailed current-sheet and reconnection analysis.

MMS data are publicly available through the NASA Space Physics Data Facility and can also be accessed programmatically using PySPEDAS.

## Software

The analysis is performed primarily in Python using Jupyter notebooks.

Common dependencies include:

```text
python
numpy
pandas
scipy
matplotlib
plotly
pyspedas
```

The analysis was developed using **PySPEDAS 2.1.3**.

Additional dependencies may be required by individual notebooks.

## Coordinate System

Current sheets are analyzed in a local **LMN boundary-normal coordinate system**, where:

- **L** is approximately aligned with the reconnecting magnetic-field component
- **M** is approximately aligned with the current-sheet guide-field direction
- **N** is normal to the current sheet

For the low-shear current sheets considered in this study, boundary normals are determined using the magnetic-field cross-product method, with minimum variance analysis used as an additional reference where appropriate.

## Main Analysis Results

The analysis presented in the manuscript includes:

- First direct evidence of leading-edge Kelvin–Helmholtz reconnection at a distant dawnside magnetopause flank under sustained northward IMF conditions
- Reconnection signatures at both leading and trailing Kelvin–Helmholtz boundaries
- Ion exhaust jets directed both sunward and tailward
- Current-sheet widths spanning approximately **2.0–13.7 ion inertial lengths**
- Median current-sheet thicknesses of approximately:
  - **5.4 \(d_i\)** for leading-edge events
  - **4.5 \(d_i\)** for trailing-edge events
- An estimated Kelvin–Helmholtz wavelength upper bound of approximately **12 \(R_E\)**
- Boundary-normal rotations and nonlinear density–velocity behavior consistent with an advanced nonlinear stage of Kelvin–Helmholtz evolution

## Reproducing the Analysis

A typical workflow is:

1. Install the required Python packages.
2. Download or load MMS burst-mode FGM, FPI, and EDP data for the event interval.
3. Construct time-indexed Pandas DataFrames for each instrument.
4. Transform the measurements into the appropriate LMN coordinate system.
5. Time-align the datasets to a common reference cadence.
6. Run the current-sheet, reconnection, and Kelvin–Helmholtz analysis notebooks.
7. Generate the plots and derived quantities used in the manuscript.

Because MMS instruments have different native cadences, careful time alignment and interpolation are required before combining electric field, magnetic field, and plasma moments.

## Citation

If you use this repository, its analysis workflow, or derived results, please cite the associated manuscript.

The repository also includes a `CITATION.cff` file so that citation metadata can be accessed directly through GitHub.

### Manuscript citation

> Lentz, C. L., Eriksson, S., Ahmadi, N., & Baker, D. N.  
> *Magnetic Reconnection within Mature Kelvin–Helmholtz Structures at the Distant Dawnside Magnetopause.*  
> Manuscript submitted to *Journal of Geophysical Research: Space Physics*.

The citation should be updated with the DOI and final publication information after the manuscript is accepted and published.

## Data Availability

MMS data used in this study are publicly available through NASA's Space Physics Data Facility and the MMS Science Data Center.

Users are responsible for following the citation and acknowledgement requirements associated with MMS mission data and individual MMS instruments.

## Authors

- **Christy L. Lentz**
- **Stefan Eriksson**
- **Narges Ahmadi**
- **Daniel N. Baker**

Laboratory for Atmospheric and Space Physics  
University of Colorado Boulder  
Boulder, Colorado, USA

