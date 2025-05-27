
**Beyond One-Size-Fits-All: A Path Toward Region-Specific Flash Drought Monitoring and Management**

Gabriela Gesualdo<sup>1\*</sup> and Antonia Hadjimichael<sup>1</sup>

<sup>1 </sup> Department of Geosciences, The Pennsylvania State University, 116 Deike Building, University Park, PA 16801, USA

\* corresponding author: gabriela.gesualdo@psu.edu

## Abstract
Flash droughts are defined by the rapid onset and intensification of drought conditions- a feature common across various proposed indicators. However, the lack of a standardized definition and detection method makes them particularly difficult to anticipate and manage. This study compares six flash drought indicators across U.S. catchments over a 40-year period to assess detection conditions and potential management implications. We find significant inconsistencies in detection, with substantial variation in the number of events identified and limited agreement between indicators, even among those based on similar variables. A multi-indicator approach can improve robustness but risks underdetection if overly strict, while single-indicator reliance may inflate false positives. Two case studies (Montana 2017; Connecticut 2022) highlight the importance of aligning indicators with regional climate conditions and water-use sectors. Our results emphasize that flash drought monitoring must move beyond one-size-fits-all definitions and adopt region- and sector-specific strategies- validated against observed impacts- to improve early warnings and adaptation.

---
## Data references
### Input data
|       Dataset       |               Description                    |               Reference/DOI          |
|:-------------------:|:--------------------------------------------:|:--------------------------------:|
|Original ERA-5 Land dataset | Hydroclimatic inputs: potential evaporation, total evaporation, volumetric soil water, precipitation flux, and 2m air temperature| Muñoz Sabater, J. (2019): ERA5-Land hourly data from 1950 to present. Copernicus Climate Change Service (C3S) Climate Data Store (CDS). DOI: 10.24381/cds.e2161bac (Accessed on 20-March-2024); Boogaard, H., Schubert, J., De Wit, A., Lazebnik, J., Hutjes, R., Van der Grijn, G., (2020): Agrometeorological indicators from 1979 to present derived from reanalysis. Copernicus Climate Change Service (C3S) Climate Data Store (CDS). DOI: 10.24381/cds.6c68c9bb (Accessed on 20-March-2024)|
|National Hydrography Dataset - 4 digit Hydrologic Unit (HUC4)| Shapefile of 4-digit Hydrologic Unit Codes (HUC4) for CONUS| U.S. Geological Survey, 2019, National Hydrography Dataset (ver. 20191002). https://www.usgs.gov/national-hydrography/access-national-hydrography-products (Accessed on 20-March-2024)|
|Hydroclimatic data by HUC4| Hydroclimatic inputs from ERA5-Land averaged over each HUC4 unit|[![DOI]()]()
|Total Crops Production - Montana| Crop production (excluding horticulture) in USD for Montana, 2007–2023| U.S. Department of Agriculture, 2025, National Agricultural Statistics Service. https://quickstats.nass.usda.gov (Accessed on 05-May-2025)|


## Output data
|       Dataset       |              Description                    |           Repository Link        |                   DOI                   |
|:-------------------:|:-------------------------------------------:|:--------------------------------:|:---------------------------------------:|
|Flash drought indicators by catchment (HUC4)| Flash drought classifications from 1983 to 2023 for each HUC4 |[Link]()|[![DOI]()]()|
|Correlation Matrix |Mean correlation between indicators across all catchment (HUC4)|[Link]()|[![DOI]()]()|
|Number of events per catchment |Count and duration of events by indicator and HUC4 unit|[Link]()|[![DOI]()]()|
|Events per Indicators Combination |Number and duration of events by indicator combinations for each catchment|[Link]()|[![DOI]()]()|

## Reproduce our experiment
Download the hydroclimatic input data at catchment scale (HUC4) from the repository [![DOI]()]. Once you have the input datasets downloaded, you can use the use the R package [fdClassify](https://github.com/pedroalencar1/fdClassify/tree/master) to identify the flash drought with different methods. You can also directly download the output fdClassify (i.e., “Flash Drought Indicators by catchment (HUC4)”) from the repository [![DOI]()].The "Flash Drought Indicators by catchment (HUC4)" is used as input to compute the pairwise agreement between flash drought indicators and the event-level agreement between flash drought indicators, using the following analysis scripts:

|Script Name | Description | 
|FDCorrelationMatrix.ipynb | Computes the pairwise agreement between flash drought indicators|
|FDIndicatorAgreement | Assesses event-level agreement between multiple flash drought indicators|


## Reproduce our figures
To reproduce the figures,  download the necessary input files and use the scripts below:

| Figure Name |                Script Name                 |                                  Description                                   | 
|:--------------:|:------------------------------------------:|:------------------------------------------------------------------------------:|
|Detected flash drought events |FDNumberEvents_Figure1.ipynb | Plots the number of detected flash drought events per indicator and catchment (HUC4)|
|Flash drought indicator agreement matrix|FDAgreements_Figure2.ipynb|Visualizes the correlation matrix of flash drought detection methods|
|Montana 2017 Case study | MontanaPlot.ipynb| Plots indicators and hydroclimatic variables during a 2017 event in a Montana HUC4 code 0105|
|Connecticut 2022 Case study|ConnecticutPlot.ipynb|Plots indicators and hydroclimatic variables during a 2022 event in a Connecticut HUC4 code 0110|
|Flash drought mean event duration |FDMeanDuration_Supplement_01.ipynb| Calculates and visualizes the average duration of events by method|
