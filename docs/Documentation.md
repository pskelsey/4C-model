<p align="left">
  <img width="212" height="166"  src="https://github.com/pskelsey/4C/blob/gh-pages/4CLogo.png">
</p>


# DOCUMENTATION

# Table of Contents
* [Background](#background)
  * [Climate data](#background)
  * [Crop data](#climate-data)
  * [Output data](#crop-data)
* [Basic operation](#basic-operation)
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
The app uses raw monthly 25 km gridded (52 x 39 cells) climate data from the UK Met Office Climate Projections database ([UKCP09](http://ukclimateprojections.metoffice.gov.uk/)) 11-member ensemble of spatially coherent climate projections (SCPs). The SCPs provide the best estimates for modelling and summarising the potential effects of future climates on spatial processes in GB as they are fully coherent across different locations, allowing the user to consider climate change at more than one location in a way that captures the relationship between the different locations,and to average projections across user defined land areas. They include both internal modelling variability (using perturbed physics ensembles) and external modelling variability (from the use of different General Circulation Models, or GCMs), as well as information on climate variability. The SCPs provide 11 equally plausible snapshots of climate change. 

### Crop data
Data defining the spatial coverage of crops and land-use types were derived from [IACS](https://ec.europa.eu/agriculture/direct-support/iacs_en), [JACS](http://www.gov.scot/Topics/Statistics/Browse/Agriculture-Fisheries/PubFinalResultsJuneCensus), and [CROME](https://data.gov.uk/data/search?q=CROME). These data cover Scotland and England only. 

## Basic operation
Tabs The app has two 'tabs' - 'Model' and 'Projections.' To switch from one tab to the other just click on their name.
Switches Drag the circluar switch to the left or right, or just click in the empty space.
Drop down lists: Click on the downward pointing arrow to reveal the list.
Numeric fields: Click in the white box to change the numerical value. Then hit enter or click outside the box.
Text fields: Click in the white box to change the text. Then hit enter or click outside the box. If

## Model Tab
<p align="left">
  <img src="https://github.com/pskelsey/4C/blob/gh-pages/modelTabLarge.png">
</p>
The risk models you create here must be a function of one weather variable only, y = f(x); e.g., crop damage as a function of temperature, infection risk as a function of precipitation, etc. The ability to build models containing more than one weather variable will be included in a future release. 

### Create your own model
Slide the 'Create a model / Fit model to data' switch to the left.

#### Use a pre-defined function
Slide the 'Use the list / Define my own' switch to the left. Select a function from the 'Model list' dropdown list. The equation will be displayed in the 'Model description' pane. Adjust the value of the parameters by clicking in the white boxes to the right of each parameter (a, b, c, d). The 'lower' and 'upper' fields will be greyed out as these are used for fitting models to data. To visualise your function, adjust the range of your x-variable (minimum and maximum values) and the increment (affects the smoothness of the curve) using the 'x-range' edit field. The format required is min:step:max, e.g., to plot from 0 to 10 in steps of 0.1 you would enter 0:0.1:10. Click the 'Run' button. To use this model for projections you must slide the 'Use this model' switch to the right and the lamp will change to green. You can now proceed to the Projections Tab by clicking on 'Projections' in the top-left of the app window.

#### Define your own function
Slide the 'Use the list / Define my own' switch to the right. The 'Use my function f(x) = ' box will no longer be greyed out and you can now type in the function you want to use. 


### Fitting a model to your own data
Slide the 'Create a model / Fit model to data' switch to the left. 

### Creating your own model


## Projections Tab

### Output data
For each future scenario you define, a 'super-ensemble' of projected values is produced (11 SCPs x *n* selected grid cells). These can be saved to an ASCII file, where a new column of data is added for each scenario defined. Each column will contain 22308 values (52 x 39 cells x 11 SCPs). Only a small proporition of these values will be numerical, pertaining to the grid cells you selected for your projections. The rest will be NaN (not a number). These results can be saved to any location you like.


## Emissions panel


## Landscapes panel


## Dispersal panel


## Plots panel



