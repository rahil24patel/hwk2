Hello,

This is my Homework #2 submission, by Rahil Patel. For this assignment, I used three dataset-building notebooks that together generate all of the processed datasets needed for the analysis notebook (and the final figures/tables for Questions 1–10). Briefly:

1. hw2_enrollment

- Imports and cleans the monthly enrollment and service area files for 2014–2019.

- Merges enrollment to service area at the contract/plan/county level and collapses to a plan–county–year dataset (using December enrollment when available, otherwise average monthly enrollment).

- Applies the required exclusions: SNPs, 800-series plans, and PDP-only / non–Part C plans.

- Outputs: county plan counts by year and a county-year dataset with HHI (based on enrollment shares) and MA penetration/share (using the penetration denominator).

2. hw2_covariate

- Cleans the landscape/plan characteristics files (messy headers and inconsistent columns across years) to produce a consistent 2014–2019 landscape dataset.

- Builds FFS cost measures for counties (2014–2019) and computes 2018 FFS cost quartiles for stratification/controls in the treatment effect section.

- Fixes the ID mismatch between SSA-style county codes in the FFS files and standard county FIPS by constructing an SSA → FIPS crosswalk from the penetration files.

3. hw2_rebate

- Extracts and cleans the CMS payment / risk-rebate plan-level files for 2014–2019.

- Backs out plan bids (PMPM) using payment and rebate components and saves bid datasets for 2014 and 2018 for the histogram comparison.

- For 2018, merges plan bids to the plan–county–year file and aggregates to county-level mean bids (enrollment-weighted and unweighted).

- Merges county bids with county HHI and classifies markets as competitive (bottom 33% HHI) vs uncompetitive (top 66% HHI) for the ATE analysis.