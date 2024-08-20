# REGREEN_Paris_heat
R code for the REGREEN project funded paper "Quantifying the Health Benefits of Heat Mitigation from Urban Green Spaces". 

# Authors
Joanne K. Garrett, Neil Bird, Tim Taylor, Elizabeth McCarthy, David Fletcher, Benedict W. Wheeler, Laurence Jones

# Code description
Code is currently not reproducible as the data is not included

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
- Read in NDVI data and calculate mean value for each greenspace
- Find the distance to either the nearest other green space or water body, whichever is closest

