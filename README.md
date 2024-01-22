# NDD_x_sleep
Repository for analyses exploring NDD and sleep disorder associations in a hypothesis free manner.

These notebooks are mean to be used with the UKB's DNA Nexus platform.

## 01_pull_NDD_cases.ipynb

This notebook allows users to pull neurodegenerative disease (NDD) cases in the UKB, creating a data frame that includes: ID, GENETIC_SEX, BIRTH_YEAR, TOWNSEND, ETHNICITY, AGE_OF_RECRUIT, first 5 PCs, date_of_death, and the first date of diagnosis for ALS, AD, DEM, MS, PD, VAS, and FTD. 

## 02_make_NDD_free_controls.ipybh

This notebook allows users to make a "healthy" cohort free of all the NDDs listed above, as well as a number of associated conditions.  See notebook for exact condicitons which are excluded. It pulls the same covariates as the first notebook.

## 03_pull_ICD_dates.ipynb

This notebooks allows users to pull the dates of the first date of diagnosis of selected ICD10 codings.

## 04_PREP_files.ipynb

This files combines the previously created files and preps the dataframe for use in a cox regression. This includes eliminating exposures that occur either before the start of the study or after NDD diagnosis.  It also creates a "tenure" column and "lag" variables for exposure endpoints.
