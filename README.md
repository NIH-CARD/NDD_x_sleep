# NDD_x_sleep
Repository for analyses exploring NDD and sleep disorder associations in a hypothesis free manner.

These notebooks are meant to be used with the UKB's DNA Nexus platform.

## 01_pull_NDD_cases.ipynb

This notebook allows users to pull neurodegenerative disease (NDD) cases in the UKB, creating a data frame that includes: ID, GENETIC_SEX, BIRTH_YEAR, TOWNSEND, ETHNICITY, AGE_OF_RECRUIT, first 5 PCs, date_of_death, and the first date of diagnosis for ALS, AD, DEM, MS, PD, VAS, and FTD. 

## 02_make_NDD_free_controls.ipybh

This notebook allows users to make a "healthy" cohort free of all the NDDs listed above, as well as a number of associated conditions.  See notebook for the complete list of excluded conditions. It pulls the same covariates as the first notebook.

## 03_pull_ICD_dates.ipynb

This notebooks allows users to pull the dates of the first date of diagnosis of selected ICD10 codings.

## 04_PREP_files.ipynb

This notebook combines the previously created files and preps the dataframe for use in a cox regression. This includes eliminating exposures that occur either before the start of the study or after NDD diagnosis.  It also creates a "tenure" column and "lag" variables for exposure endpoints.

## 05_COX_model.ipynb

This notebook uses the csv file created in step 4 and runs a lifelines Cox regression.  It also includes FDR correction.

## 06_COX_with_lags.ipynb

This notebook uses the csv file created in step 4 and looks at significant results in greater detail, runing a lifelines Cox regression for exposures with "lags": all exposures before tenure (lag 0); 0-1 years before tenure; 1 to 5 years before tenure; 5-10 years before tenure; 10-15 years before tenure; and 5-15 years before tenure.

## 07_prep_density_plots.ipynb

This notebook adds PRS scores to the csv file created in step 4.

## 08_Kaplan_Meyer.ipynb

This notebook creates Kaplan Meyer graphs using the csv file created in step 4.

## 09_PRS_density_plots.ipynb

This notebook creates density plots comparing significant exposures and the NDD PRS scores, using the csv files created in step 7.

## 10_PREP_Interaction_Files.ipynb

This notebook creates a new dataframe with an interaction varible by combining data from the csv files created in steps 4 and 7.

## 11_PRS_Interaction.ipynb

This notebook runs a glm looking at the interaction variables, using the csv file created in step 10.
