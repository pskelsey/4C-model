<p align="left">
  <img width="212" height="166"  src="https://github.com/pskelsey/4C/blob/gh-pages/4CLogo.png">
</p>


# DOCUMENTATION

# Table of Contents
* [Background](#background)
  * [Climate data](#climate-data)
  * [Crop data](#crop-data)
* [Basic operation](#basic-operation)
* [Model Tab](#model-tab)
  * [Create your own model](#create-your-own-model)
  * [Fit a model to your own data](#fit-a-model-to-your-own-data)
  * [Plot a model](#plot-a-model)
  * [Final model selection](#final-model-selection)
* [Projections tab](#projections-tab)
  * [Emissions panel](#emissions-panel)
  * [Landscapes panel](#landscapes-panel)
    * [How to incorporate cell areas](#how-to-incorporate-cell-areas)
    * [Select a distribution of locations](#select-a-distribution-of-locations)
    * [Artificial landscape generation](#artificial-landscape-generation)
  * [Dispersal panel](#dispersal-panel)
    * [Choose the type of dispersal](#choose-the-type-of-dispersal)
    * [Create the dispersal function](#create-the-dispersal-function)
  * [Plots panel](#plots-panel)
    * [Making maps](#making-maps)
    * [Plotting projected values](#plotting-projected-values)
    * [Saving results](#saving-results)
  

# Background
The app uses gridded crop distribution / land use data and gridded climate change data, and allows you to build a weather-dependent model to apply in selected grid cells under various climate change scenarios. A unique feature of the app is the ability to define spatial relationships (e.g. risk of pest or pathogen dispersal) among grid cells via various dispersal options. These spatial relationships can be used to modify projected values. 

### Climate data
The app uses raw monthly 25 km gridded (52 x 39 cells) climate data from the UK Met Office Climate Projections database ([UKCP09](http://ukclimateprojections.metoffice.gov.uk/)) 11-member ensemble of spatially coherent climate projections (SCPs). The SCPs provide the best estimates for modelling and summarising the potential effects of future climates on spatial processes in GB as they are fully coherent across different locations, allowing the user to consider climate change at more than one location in a way that captures the relationship between the different locations,and to average projections across user defined land areas. They include both internal modelling variability (using perturbed physics ensembles) and external modelling variability (from the use of different General Circulation Models, or GCMs), as well as information on climate variability. The SCPs provide 11 equally plausible snapshots of climate change; i.e. a range of 11 future values are provided for each climate variable in each grid cell. UKCP09 1961-1991 baseline data are also included for comparison, i.e. for computing a change relative to the current climate.

### Crop data
Polygon data defining the spatial coverage of crops and land-use types were derived from [IACS](https://ec.europa.eu/agriculture/direct-support/iacs_en), [JACS](http://www.gov.scot/Topics/Statistics/Browse/Agriculture-Fisheries/PubFinalResultsJuneCensus), and [CROME](https://data.gov.uk/data/search?q=CROME). These data cover Scotland and England only. The vector data were rasterised to 25 km grids matching the resolution of the climate change data. Information on the location and area of each crop / land-use type per grid cell is available for use in the app.

# Basic operation
*Tabs*: The app has two 'tabs' - 'Model' and 'Projections.' To switch from one tab to the other just click on their name.  
*Switches*: Drag the circluar switch to the left or right, or just click in the empty space.  
*Drop down lists*: Click on the downward pointing arrow to reveal the list.  
*Numeric fields*: Click in the white box to change the numerical value. Then hit enter or click outside the box.  
*Text fields*: Click in the white box to change the text. Then click outside the box. If you can't, you're not allowed.  
*Buttons*: Click them.  
*Knobs*: Drag the control to around your selection, or click on your selection.  
*List boxes*: Use the scroll bar to the right to reveal more choices. Click on a value to select it - it will be highlighted.  
*Radio buttons*: These are little circles to the left of lists. Click one to select, and it will be highlighted with a black dot.  
*Toggle switches*: These flip up and down. 

# Model Tab
The risk models you create here must be a function of one weather variable only, y = f(x); e.g. crop damage as a function of temperature, infection risk as a function of precipitation, etc. The ability to build models containing more than one weather variable will be included in a future release.  

<p align="left">
  <img src="https://github.com/pskelsey/4C-model/blob/gh-pages/modelsTabLarge.png">
</p>

### Create your own model
Select 'Create a model' using the switch.

#### Use a pre-defined function
Select 'Use the list' using the switch. Select a function from the 'Model list' dropdown list. The equation will be displayed in the 'Model description' pane. Adjust the value of the parameters (a, b, c, d) using the numeric fields. The 'lower' and 'upper' fields will be greyed out as these are used for fitting models to data. Click the 'Run' button to visualise your model.

#### Define your own function
Select 'Define my own' using the switch. The 'Use my function f(x) = ' text field will no longer be greyed out and you can now type in the function you want to use. The following rules must be followed when defining your model: (i) do not include the dependent variable, i.e. omit the 'y = ' or 'f(x) = ' part of your equation as this is implicitly assumed; (ii) your equation should be a function of one independent variable only and you must use the letter 'x' for that variable; (iii) [MATLAB notation](https://uk.mathworks.com/help/matlab/matlab_prog/matlab-operators-and-special-characters.html) is required for your arithmetical operators and symbols. If these rules are not followed, an 'Incorrect sytax' warning will occur. Click the 'Run' button to visualise your model.

### Fit a model to your own data
Select 'Fit model to data' using the switch. This will open up a file selection dialog box. Your datafile must be an ASCII delimited text file or CSV file with the data stored in columns. The first column should contain the independent- or x-variable (i.e. the weather variable) and the second column the dependent variable. Replicate values of the dependent variable should be stored in subsequent columns. If your file does not meet these requirements then a warning will occur and the app will default back to 'Create a model.' A data file ('testData.txt') has been provided in the 'Assets' list of the release (see download instructions in the README.md) to help you get up and running with the model fitting features. Your data will be plotted in the 'Data / Predictions' plot pane once it has loaded successfully, and the x-axis limits of the plot pane will adjust according to the lower and upper values in your data. 

To fit a model, select one from the dropdown 'Model list.' The selected model will be displayed in the 'Model description' pane. The grid of 'Parameter' text fields in the top-right corner will adjust according to the model, with unnecessary fields greyed out. Default initial values for the parameters to be fitted are selected uniformly at random from the interval (0,1), or you can set these yourself using the 'initial' text field. Lower and upper bounds on the parameters to be fitted can be set using the 'lower' and 'upper' text fields. Click the 'Run' button to fit the model. The numerical fit results will be displayed in the 'Model description' pane and goodness of fit statistics in the 'GoF' pane. If the model fails to fit a warning will occur, with some suggestions to help improve the fit. The method of least squares (linear or nonlinear) is used when fitting data, or there is an option to fit a smoothing spline in the 'Model list'. Spline is a good option if your data is noisy or you are having trouble fitting other models, although this is considered a non-parametric fit and the display of numerical fit results will be limited. The value of the smoothing parameter for splines is fixed at 0.1. 

### Plot a model
Click the 'Run' button to display your user-defined or fitted model in the 'Data / Predictions' plot pane. Use the 'x-range' numeric field below the plot pane to visualise or extrapolate your model across a different range of values on the x-axis. The format required is min:step:max, e.g. to plot from 0 to 10 in steps of 0.1 you would enter 0:0.1:10. Then hit Return on your keyboard or click your mouse outside of the numeric field. Note that this is for visualisation purposes only and does not affect model fit.

### Final model selection
To use a model for projections you must select 'Use this model' with the switch in the bottom right corner of the tab, changing the lamp from red to green. You can now proceed to the Projections Tab.

# Projections Tab
<p align="left">
  <img src="https://github.com/pskelsey/4C-model/blob/gh-pages/projectionsTabLarge.png">
</p>

## Emissions panel
Select your climate variable, future time-period, and CO2 emissions scenario using the knobs. Select the month of the year or the season using the list box. For seasonal averages of the selected climate variable, Spr = spring (MAM), Sum = summmer (JJA), Aut = autumn (SON), and Win = winter (DJF). The climate change data are probabilistic, therefore a range of climate values will be provided for each grid cell (see [Climate data](#climate-data)).

## Landscapes panel
Here you define the distribution of locations (grid cells) that you want to use in your risk assessment. 

### How to incorporate cell areas
The 'Areas' radio buttons (No / Yes) are used to determine whether or not you want the area crop / land use type within each 25 km grid cell to be incoporated into risk model projections. 'No' = projections are made for every grid cell containing the crop / land use of interest. 'Yes' = projected values incorporate the area of crop / land use within each grid cell, and if required, also a cell density parameter that is set using the numeric field below the 'Yes' radio button: projected value = risk model value x area x density. The following examples demonstrate how these radio buttons and the density numeric field can be combined for a wide variety of different outcomes:
1. Your risk model describes the impact of a climate variable on any response variable (e.g. disease severity per observational unit,  crop growth rate, etc.). To project future values of the response variable in grid cells containing any amount of the land use type of interest, select 'No': projected value = risk model value.
2. Your risk model describes the impact of climate on the density of a variable per square meter of crop cover (e.g. pests per square meter of crop cover). To project the total number in each grid cell, select 'Yes' and leave the density field equal to 1 (i.e. square meters of crop per square meter of crop): projected number per cell (pests) = risk model value (pests m<sup>-2</sup>) x area of crop per cell (m<sup>2</sup>) x 1 (m<sup>2</sup> m<sup>-2</sup>).
3. Your risk model describes the impact of climate on the density of a variable per square meter of crop canopy (e.g. lesions per square meter of foliage). To project the total number in each grid cell, select 'Yes' and set the density field equal to the ratio of canopy area to ground area (i.e. the leaf area index, LAI): projected number per cell (lesions) = risk model value (lesions m<sup>-2</sup>) x area of crop per cell (m<sup>2</sup>) x LAI (m<sup>2</sup> m<sup>-2</sup>).
4. Your risk model describes the impact of climate on the density of a variable per observational unit (e.g. spores per lesion). To project the total number of spores in each grid cell, select 'Yes' and set the density field equal to the ratio of the observational unit to crop area (e.g. lesions per square meter of crop cover): projected number per cell (spores) = risk model value (spores lesion<sup>-1</sup>) x area of crop per cell (m<sup>2</sup>) x density of lesions (lesions m<sup>-2</sup>).
5. Your risk model describes the impact of climate on the per capita growth rate of a population of organisms. To obtain the future population size within the habitat / host contained in each grid cell, select 'Yes' and set the density field equal to the initial number of organisms per square meter of crop: projected number per cell (individuals) = risk model value (-) x area of crop per cell (m<sup>2</sup> crop) x initial density (individuals m<sup>-2</sup>). Note that the growth rate in your risk model should be a monthly or seasonal per capita growth rate to match the temporal resolution of the climate change data (see [Climate data](#climate-data)). 

The density parameter can be used in many other ways; just make sure you do a dimensional analysis, as above, so that the units on the left hand side of the equality operator match the units on the right hand side.

### Select a distribution of locations
Select a region of the Scotland or England using the 'Region' knob. Sco_N, Sco_E, Sco_W = Northern, Eastern and Western Scotland, respectively. Eng_N, Eng_M, Eng_SE, Eng_SW = North, Midlands, South East, and South West England, respectively. Once a region is selected, choose a spatial distribution of crop / land use locations using the  'Crop / land use' list box: P = potato, SB = spring barley, WB = winter barley, SO = spring oats, WO = winter oats, SW = spring wheat, WW = winter wheat, F = forestry, W = water bodies (ponds, lakes, rivers).

### Artifical landscape generation
The 4C model also allows you to generate your own distribution of locations. This is useful if the crop distribution desired is not available, and for adaptation scenarios involving a change in the amount and spatial distribution of crop locations. Artifical landscapes are generated using fractal geometry (the ‘inverse Fourier transform' method) to create binary landscape patterns of occupied / unoccupied cells (e.g. habitat / non-habitat). Select 'Artificial' using the switch. Set 'Seed' using the numeric field - this controls the random generation of patterns, allowing you to replicate a pattern by using the same value for seed. The 'f' numeric field (0,1) sets the fraction of GB land area that will be occupied. The 'H' numeric field (0,1) controls the degree of aggregation of occupied cells via a parameter known as the Hurst exponent. The 'r' numeric field (0.01,1) controls the texture of the pattern, or the size distribution of gaps among occupied cells, via a parameter known as the lacunarity.

## Dispersal panel
The features in this panel are used to define spatial relationships among grid cells, i.e. physical dispersal among cells, or degree of connectivity among cells (on a scale of 0 to 1). These spatial relationshps are used to modify the projected values from your risk model. For those who are interested, spatial phenomena are solved by performing a spatial convolution between the distribution of risk model values in the selected cells and a 2D radially-symmetric probability density function (dispersal kernel), implemented via fast Fourier transforms (see [Skelsey et al. 2013](http://journals.plos.org/plosone/article?id=10.1371/journal.pone.0075892)). 

### Choose the type of dispersal
The 'Dispersal' knob is used to define three different types of spatial relationship among cells: 
1. No dispersal - set 'Dispersal' to 'Off.' This means that projected values from your risk model are not modified to incorporate a spatial relationship among cells.
2. Dispersal is a physical process involving absolute numbers of dispersing agents - set 'Dispersal' to 'Std.' or 'No self.' In both cases, the projected values from your risk model are treated as a 'source' of material (an amount per cell) to be dispersed among other grid cells. When 'Std.' (standard) is selected, source values are dispersed among all grid cells *including* the cell of origin. An example would be passive dispersal of spores, whereby a proportion deposit close to the infection source (in the same grid cell). When 'No self.' (no selfing) is selected then all source material is dispersed outwith the boundaries of the source cell. An example would be active dispersal of pests away from a depleted habitat resource. When 'No self.' is selected the centre of the dispersal kernel is set to 0.   
3. Dispersal is a weighting factor, ranging from 0 to 1, that describes the degree of connectivity of each cell to all other cells - set 'Dispersal' to 'Conn.' In this case the dispersal kernel is normalized to a maximum value of unity. An example would be a risk model that projects the likelihood of pest occurrence (on a scale of 0 to 1), which is then weighted according to the connectivity of host cells (on a scale of 0 to 1) to provide projections of the risk of pest occurrence and spread (on a scale of 0 to 1). 

### Create the dispersal function
To change the dispersal function use the 'Kernel' knob:  fat = fat-tailed (square-root negative exponential kernel), thin = thin-tailed (negative exponential kernel), Gauss = Gaussian kernel. These three kernels are all derived from the exponential-power distribution and all have a different shape (see [Skelsey et al. 2013](http://journals.plos.org/plosone/article?id=10.1371/journal.pone.0075892) for a thorough explanation). Fat-tailed kernels are often used for processes that operate at broad spatial scales, such as long-distance dispersal by wind, whereas thin-tailed kernels are often used for processes that operate at fine spatial scales, such as splash dispersal. The kernel is parameterized using the 'mdd' numeric field = mean dispersal distance. Enter a number for the average distance that an individual can disperse. A 1D slice through your dispersal kernel (i.e. a dispersal gradient) is automatically displayed in the 'Dispersal gradient' plot pane.

## Plots panel

### Making maps
Click the 'Map' button to the left of the 'Map of climate variable / land use' plot pane. Switch between a map of the selected climate variable and a map of the selected crop / land use distribution using the 'Plot' radio buttons immediately beneath. 

### Plotting projected values
Once your future scenario has been defined, click the 'Project' button to the left of the 'Boxplots of projected values' plot pane. This will produce a boxplot of projected values for that scenario. Each boxplot is a 'super-ensemble' of projected values (11 SCPs x *n* selected grid cells). Boxes extend from the first to the third quartile, medians are marked in each box, and whiskers extend to 1.5 times the interquartile range. You can display multiple boxplots (i.e. multiple scenarios, such as a different month of the year / decade / emissions level / risk model / crop distribution, etc.) together in the plot pane. Click the 'Clear' button to clear the plot pane. The 'Plot' radio button 'Abs' will plot the absolute projected values from your risk model. The 'Chg' radio button will plot the projected values relative to those for the 1961-1991 baseline climatology to show the proportional response; i.e. the percentage change in the response variable relative to baseline conditions. The 'Scale' radio buttons 'Lin.' and 'Log.' will change the scale of the y-axis from linear to logarithmic.   

### Saving results
Click the 'Save' button to save your results. This will open up a file save dialog box, where you can name your results file and save to any location. Note that only the results for the boxplots displayed in the plot pane will be saved - if you click the 'Clear' button then these results will be lost. Your results will be saved to an ASCII file, and the projected values for each scenario you define (each boxplot) will be stored in a separate column. Each column will contain 22308 values (52 x 39 cells x 11 SCPs). Only a small proporition of these values will be numerical, pertaining to the grid cells you selected for your projections. The rest will be NaN (not a number), representing the grid cells (land and sea) not selected. 



