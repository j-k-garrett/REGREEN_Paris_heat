# REGREEN_Paris_heat
R code for the REGREEN project funded paper "Quantifying the Health Benefits of Heat Mitigation from Urban Green Spaces". 

# Authors
Joanne K. Garrett, Neil Bird, Tim Taylor, Elizabeth McCarthy, David Fletcher, Benedict W. Wheeler, Laurence Jones

# Code description
Code is currently not reproducible as the data is not included.

Knit each script in order, at the beginning of each script, make sure all the required libraries are installed and set own locations for data and figure folders. 

`greenspace_processing.rmd` 
- Reads in the greenspace data
- Excludes spaces which are planned
- Joins together spaces that are <30 m apart
- Find the distance to the nearest green space and water body
- Select green spaces that are within the four central departments of Paris
- Saves file of all public green spaces in the four central departments of Paris 

`step_1_subset.rmd` 
- Subsets green spaces to those >1,000m2
- Read in temperature rasters for three hot days and resample to every 5 m
- Read in NDVI data, resample to every 5 m and calculate mean value for each greenspace
- Selects greenspaces which are at least 150 m from other green spaces or water bodies (distances calculated using NNJoin in QGIS). 
- Finds maximum cooling distance and temperature difference between the greenspace boundary and maximum cooling distance for all green spaces in this subset
- Saves results

`step_1_modelling.rmd`
- Reads in results from step_1_subset
- Presents descriptives for model variables
- Runs Generalised Additive Model (GAM) to explore nature of relationship between predictors (area and NDVI) and cooling outcomes (maximum cooling distance and temperature difference)
- Run linear modelling predicting cooling outcomes by predictors
- Present figures of the data and modelling outcome
Step 2
- Calculate cooling effect for all green spaces in Paris >1,000m2 from the model coefficients
- Calculate the population benefiting from the cooling of all green spaces

`step_3_upscaling.rmd`
- Calculates the boundary temperatures (-15m - greenspace boundary) for all green spaces >1,000m2 for three hot days
- Calculates the expected lives saved and associated economic value for all green spaces >1,000m2 for three hot days
- Calculates the expected lives saved and associated economic value for all green spaces >1,000m2 for all hot days
- Plot results

