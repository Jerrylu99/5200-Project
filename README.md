# Card & Krueger (1994) Replication — Phase 1

## Track
Causal Policy Track (Difference-in-Differences)

## Paper
Card, D., & Krueger, A. B. (1994). Minimum Wages and Employment: A Case Study of the Fast-Food Industry in New Jersey and Pennsylvania.

## What this repo is (Phase 1)
For Phase 1 I set up the repo structure, downloaded the original replication dataset, and verified I can load the raw fixed-width file (`public.dat`) in Python.

## Data source
http://davidcard.berkeley.edu/data_sets/njmin.zip

## Repo structure
- data/raw: downloaded + unzipped raw files (do not overwrite)
- data/processed: small processed outputs from the code
- notebooks: analysis notebooks

## Phase 1 check
- successfully loaded `public.dat` using `pandas.read_fwf()` and displayed `head()`
- saved `data/processed/public_minimal_processed.csv`
