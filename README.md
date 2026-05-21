# HCSC Search

This repository contains the code and data for a master's thesis 
project at Radboud University, focused on searching for 
Hyper Compact Stellar Systems (HCSCs) using Gaia DR3 data.

## Repository Structure

- `gaia_download.ipynb` — Downloads the Gaia DR3 data for the 
  b > 30 and b < -30 sky regions with a 30% relative distance 
  uncertainty filter
- `HCSC_search.ipynb` — Main analysis pipeline based on Fraser 
  (2023), extended with the 30% parallax uncertainty filter. 
  Performs Bayesian distance estimation using `pyrallaxes.py` and 
  DBSCAN spatial clustering
- `HCSC_pipeline.ipynb` — SIMBAD cross-matching, histogram of 
  SIMBAD object types, candidate table, PanSTARRS and SkyMapper 
  visual inspection, and DS9 region file generation
- `pyrallaxes.py` — Collection of functions required for the 
  Bayesian distance estimation, adapted from Fraser (2023)
- `PARSEC_isochrones.dat` — PARSEC isochrone for Z=0.0001, age 
  12 Gyr

## Data Availability

The raw Gaia DR3 catalogs and the distance computed catalogs 
are not included in this repository due to their size (~12 GB together). 
The raw Gaia data can be re-downloaded using `gaia_download.ipynb`. 
The distance computed catalogs required ~200 hours of computation 
per file and can be requested from the author or supervisor.

## How to Reproduce

1. Run `gaia_download.ipynb` to download the Gaia DR3 data
2. Run `HCSC_search.ipynb` to perform the distance estimation and 
   clustering
3. Run `HCSC_pipeline.ipynb` to perform the SIMBAD cross-matching 
   and visual inspection

## Results

- `All_Candidates_Summary_b_boven30deg_30per.csv` — All cluster 
  candidates found in the b > 30 region
- `All_Candidates_Summary_b_onder30deg_30per.csv` — All cluster 
  candidates found in the b < -30 region
- `Known_Simbad_Clusters_Matched_b_boven30deg_30per.csv` — Known 
  clusters matched in SIMBAD for b > 30
- `Known_Simbad_Clusters_Matched_b_onder30deg_30per.csv` — Known 
  clusters matched in SIMBAD for b < -30
- `Potential_New_Clusters_Matched_b_onder30deg_30per.csv` — 68 
  new HCSC candidates in the b < -30 region
- `Images/` — PanSTARRS and SkyMapper images of all candidates
- `Results_b_boven30deg_30per/` — Cluster data and plots for 
  b > 30
- `Results_b_onder30deg_30per/` — Cluster data and plots for 
  b < -30
