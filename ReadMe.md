Hello

This is my Homework #2 attempt, by Rahil Patel. For this assignment, I have 3 dataset building notebooks that include all necessary data to answer the questions. Here is a brief description of each:

1. hw2_enrollment

- Normalized column names across messy monthly files.

- Cleaned contract_id and plan_id, forced plan_id to 3 digits.

- Built consistent 5 digit county FIPS, including fallback logic when FIPS came as state plus county codes.

- Flagged and dropped SNP plans, 800 series plans, and PDP only plans into a single drop_hw2 flag.

- Merged enrollment with service area month by month, then collapsed to plan county year with enroll_sum, avg_enrollment, and dec_enrollment.

- Produced county plan counts for 2014 to 2019 and county HHI plus MA share using penetration files.

2. hwk2_covariate

- Auto detected header rows in landscape CSVs and standardized columns across years.

- Combined multiple landscape chunks per year into one cleaned long file for 2014 to 2019.

- Built a county year FFS cost measure from CMS master CSV for 2014 to 2015 and Excel files for 2016 to 2019.

- Cleaned the FFS code into county FIPS and enforced numeric reimbursements and enrollments.

- Created 2018 FFS quartiles with qcut and saved a small 2018 quartile file for matching and IPW.

3. hwk2_rebate

- Searched for the Part C plan level workbook and picked the best sheet using a scoring rule based on needed columns.

- Cleaned contract_id and plan_id again and forced plan_id to 3 digits to match other datasets.

- Parsed rebate PMPM, AB PMPM payment, and risk score, then computed bid_pmpm as AB payment minus rebate.

- Wrote plan level bid files for all years and year slices for 2014 and 2018.

- Merged 2018 plan bids onto the 2018 plan county year file and computed county bid means with and without enrollment weights.

- Merged county bids to 2018 HHI and classified markets using the 33rd and 66th percentile HHI cutoffs.