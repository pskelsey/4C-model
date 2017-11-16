<p align="left">
  <img width="212" height="166"  src="https://github.com/pskelsey/4C/blob/gh-pages/4CLogo.png">
</p>


# DOCUMENTATION

# Table of Contents
* [Background](#background)
  * [Climate data](#background)
  * [Crop data](#climate-data)
  * [Output data](#crop-data)
* [Model Tab](#model-tab)
  * [Fitting a model to your own data](#fitting-a-model-to-your-own-data)
  * [Creating your own model](#creating-your-own-model)
* [Projections tab](#projections-tab)
  * [Emissions panel](#emissions-panel)
  * [Landscapes panel](#landscapes-panel)
  * [Dispersal panel](#dispersal-panel)
  * [Plots panel](#plots-panel)

## Background
The app uses gridded crop distribution / land use data and gridded climate change data, and allows you to build a weather-dependent model to apply in selected grid cells under various climate change scenarios. A unique feature of the app is the ability to define spatial relationships (e.g., risk of pest or pathogen dispersal) among grid cells via various dispersal options. These spatial relationships can be used to modify projected values. 

### Climate data
The app uses raw monthly 25 km gridded climate data from the UK Met Office Climate Projections database ([UKCP09](http://ukclimateprojections.metoffice.gov.uk/)) 11-member ensemble of spatially coherent climate projections (SCPs). The SCPs provide the best estimates for modelling and summarising the potential effects of future climates on spatial processes in GB as they are fully coherent across different locations, allowing the user to consider climate change at more than one location in a way that captures the relationship between the different locations,and to average projections across user defined land areas. They include both internal modelling variability (using perturbed physics ensembles) and external modelling variability (from the use of different General Circulation Models, or GCMs), as well as information on climate variability. The SCPs provide 11 equally plausible snapshots of climate change. 

### Crop data
Data defining the spatial coverage of crops and land-use types were derived from [IACS](https://ec.europa.eu/agriculture/direct-support/iacs_en), [JACS](http://www.gov.scot/Topics/Statistics/Browse/Agriculture-Fisheries/PubFinalResultsJuneCensus), and [CROME](https://data.gov.uk/data/search?q=CROME). These data cover Scotland and England only. 

### Output data
For each future scenario you define, a 'super-ensemble' of projected values is produced (11 SCPs x *n* selected grid cells). These can be saved to an ASCII file, where a new column of data is added for each scenario defined. Results will be saved to the same location as the 

That means that for each selected grid cell there will be an ensemble or distribution of 11 results from your model.

## Model Tab


### Fitting a model to your own data
The risk model must be a function of one weather variable only, y = f(x); e.g., crop damage as a function of temperature, infection risk as a function of precipitation, etc. The ability to build models containing more than one weather variable will be included in a future release. 

### Creating your own model


## Projections Tab


### Emissions panel


### Landscapes panel


### Dispersal panel


### Plots panel



