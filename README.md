([![DOI](https://joss.theoj.org/papers/10.21105/joss.06325/status.svg)](https://doi.org/10.21105/joss.06325)

## **Flash Drought indicators at catchment scale for CONUS**

Gabriela Gesualdo<sup>1\*</sup> and Antonia Hadjimichael<sup>1</sup>

<sup>1 </sup> Department of Geosciences, The Pennsylvania State University, 116 Deike Building, University Park, PA 16801, USA

#### corresponding author: gabriela.gesualdo@psu.edu
---
## Data references
### Input data
|       Dataset       |               Description                    |               Reference/DOI          |
|:-------------------:|:--------------------------------------------:|:--------------------------------:|
|Original ERA-5 Land dataset | Hydroclimatic inputs: potential evaporation, total evaporation, volumetric soil water, precipitation flux, and 2m air temperature| Muñoz Sabater, J. (2019): ERA5-Land hourly data from 1950 to present. Copernicus Climate Change Service (C3S) Climate Data Store (CDS). DOI: 10.24381/cds.e2161bac (Accessed on 20-March-2024); Boogaard, H., Schubert, J., De Wit, A., Lazebnik, J., Hutjes, R., Van der Grijn, G., (2020): Agrometeorological indicators from 1979 to present derived from reanalysis. Copernicus Climate Change Service (C3S) Climate Data Store (CDS). DOI: 10.24381/cds.6c68c9bb (Accessed on 20-March-2024)|
|National Hydrography Dataset - 4 digit Hydrologic Unit (HUC4)| Shapefile of 4-digit Hydrologic Unit Codes (HUC4) for CONUS| U.S. Geological Survey, 2019, National Hydrography Dataset (ver. 20191002). https://www.usgs.gov/national-hydrography/access-national-hydrography-products (Accessed on 20-March-2024)|
|Hydroclimatic Data by Catchment (HUC4)| ERA5-Land hydroclimatic data averaged over each HUC4 unit|[![DOI](https://data.msdlive.org/badge/DOI/10.57931/2568767.svg)](https://doi.org/10.57931/2568767)
|Total Crops Production - Montana| Crop production (excluding horticulture) in USD for Montana, 2007–2023| U.S. Department of Agriculture, 2025, National Agricultural Statistics Service. https://quickstats.nass.usda.gov (Accessed on 05-May-2025)|


## Output data
|       Dataset       |              Description                    |           Repository Link        |                   DOI                   |
|:-------------------:|:-------------------------------------------:|:--------------------------------:|:---------------------------------------:|
|Flash drought indicators by catchment (HUC4)| Flash drought classifications from 1983 to 2023 for each catchment |[Link](https://doi.org/10.57931/2568767)|[![DOI](https://data.msdlive.org/badge/DOI/10.57931/2568767.svg)](https://doi.org/10.57931/2568767)|
|Correlation Matrix |Mean pairwise agreement between indicators across all catchments |[Link](https://doi.org/10.57931/2568767)|[![DOI](https://data.msdlive.org/badge/DOI/10.57931/2568767.svg)](https://doi.org/10.57931/2568767)|
|Number of events per catchment (HUC4) |CCount and duration of events by indicator and catchment|[Link](https://doi.org/10.57931/2568767)|[![DOI](https://data.msdlive.org/badge/DOI/10.57931/2568767.svg)](https://doi.org/10.57931/2568767)|
|Events per Indicators Agreement |Count and duration of events based on indicator agreement |[Link](https://doi.org/10.57931/2568767)|[![DOI](https://data.msdlive.org/badge/DOI/10.57931/2568767.svg)](https://doi.org/10.57931/2568767)|

## Reproduce our experiment
Download the hydroclimatic input data at catchment scale (HUC4) from the data [repository](https://doi.org/10.57931/2568767). Once you have the input datasets downloaded, you can use the R package [fdClassify](https://github.com/pedroalencar1/fdClassify/tree/master) to identify the flash drought with different indicators. You can also directly download the output fdClassify (i.e., “Flash Drought Indicators by catchment (HUC4)”) from the data [repository](https://doi.org/10.57931/2568767). The "Flash Drought Indicators by catchment (HUC4)" is used as input to compute the pairwise agreement between flash drought indicators and the event-level agreement between flash drought indicators, using the following analysis scripts:

|Script Name | Description |
|:-------------------:|:-------------------------------------------:|
|[FDCorrelationMatrix.ipynb](./Codes/FDCorrelationMatrix.ipynb)| Computes the pairwise agreement between flash drought indicators|
|[FDIndicatorAgreement.ipynb](./Codes/FDIndicatorAgreement.ipynb)| Assesses event-level agreement between multiple flash drought indicators|


## Reproduce our figures
To reproduce the figures,  download the necessary input files and use the scripts below:

| Figure Name |                Script Name                 |                                  Description                                   | 
|:--------------:|:------------------------------------------:|:------------------------------------------------------------------------------:|
|Detected flash drought events |[FDNumberEvents_Figure1.ipynb](./FiguresCodes/FDNumberEvents_Figure1.ipynb) | Plots the number of detected flash drought events per indicator and catchment (HUC4)|
|Flash drought indicator agreement matrix|[FDAgreements_Figure2.ipynb](./FiguresCodes/FDAgreements_Figure2.ipynb)|Visualizes the correlation matrix of flash drought detection methods|
|Montana 2017 Case study |[MontanaPlot.ipynb](./FiguresCodes/MontanaPlot.ipynb)| Plots indicators and hydroclimatic variables during a 2017 event in a Montana HUC4 code 0105|
|Connecticut 2022 Case study|[ConnecticutPlot.ipynb](./FiguresCodes/ConnecticutPlot.ipynb)|Plots indicators and hydroclimatic variables during a 2022 event in a Connecticut HUC4 code 0110|
|Flash drought mean event duration |[FDMeanDuration_Supplement_01.ipynb](./FiguresCodes/FDMeanDuration_Supplement_01.ipynb)| Calculates and visualizes the average duration of events by method|
