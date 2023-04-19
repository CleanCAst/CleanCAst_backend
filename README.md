# CleanCAst_backend

Final project repository for UC Berkeley MIDS 210 Capstone. Group: Bronte Baer, Kurt Eulau, Briana Hart, Thomas Welsh.

The CleanCAst project comprises two Github repositories:

1. `CleanCAst_backend`: (this repo) which contains references to data sources and code used to produce carbon intensity model.
2. `CleanCAst_frontend`: repo containing website content made using React, Reactstrap and create-react-app.

## Data

The project was executed in an AWS cloud environment, primarily using SageMaker for computing and S3 for storage. Consequently, the data folder contains complete files when file sizes are compatible with Github file size limits. In cases where the files are too large to be storge in their entireity on Github, we include samples only. All samples are noted with a `_SAMPLE` suffix at the end of the file name.

We built CleanCAst using a data pipeline that aggregates data from the following sources:

* The U.S. [Energy Information Administration (EIA)](https://www.eia.gov/) supplied actual historical hourly generation data by source (natural gas, solar, nuclear, etc.) for the entire California grid, and total CO2 emissions for each source.
* The [National Center for Atmospheric Research (NCAR)]() Research Data Archive supplied historical hourly weather forecasts for each latitude and longitude at increments of 0.25° via the NCEP GFS 0.25 Degree Global Forecast Grids Historical Archive ds084.1, which we matched to centroids of CEC resource regions below.
* [California Energy Commission](https://www.energy.ca.gov/) supplied maps of [Solar Resource Areas and Wind Resource Areas](https://cecgis-caenergy.opendata.arcgis.com/maps/CAEnergy::solar-resource-areas-2022), as well as generating capacity of those regions. The geographic centroids of each solar region were calculated from shapefiles and capacity-weighted weather and solar radiation forecasts were incorporated into the pipeline.

## Notebooks

All code configured to run on Amazon SageMaker Data Science 3.0 instance.

* __PLACEHOLDER FOR PREPROCESSING NOTEBOOK__

* `EDA_co2_intensity.ipynb`: exporatory data analysis of carbon intensity and covariates

* __PLACEHOLDER FOR TOM'S SOLAR RADIATION NOTEBOOK__

* `LightGBM_co2_96_hr_final_model.ipynb`: takes pre-processed data to produce 96 hour carbon intensity forecast

* `LightGBM_co2_post_processing.ipynb`: various tasks including error analysis, writing post-hoc data to file, etc.

* `LightGBM_co2_96_hr_ablation.ipynb`: ablation study using 24 hour carbon intensity forecast
