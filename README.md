<p align="left">
<img width="212" height="166"  src="https://github.com/pskelsey/4C/blob/gh-pages/4CLogo.png">
</p>
   
# _4C model_: Crop Connectivity under Climate Change

## Basic overview
A desktop app for performing climate change risk assessments in real crop locations in Great Britain. 
* Build your own risk model in a few easy clicks.
* Choose a raster distribution of crop species / land use locations to apply your model in, or generate your own landscape.
* Select a climate variable, a future time-period and month, and pick your greenhouse gas emissions scenario.
* Define the level of connectivity among grid cell locations, if desired.
* Hit the run button, visualise your results, and save them to create your own graphics. 

## Example
A risk function is selected from the drop-down list and fit to user-defined data for the proportion of plants infected as a function of temperature. If you have no data you can still select a model from the drop-down list and manually adjust the parameter values to suit, or define your own function in the box provided. 

<p align="left">
  <img src="https://github.com/pskelsey/4C/blob/gh-pages/modelsTabLarge.png">
</p>
Once your model is defined in the Model Tab, you can move on to the Projections Tab. Temperature is selected as the variable of interest, for a low emissions scenario in the 2040s, and potato crops are selected from the list of available crop species / land-use types. That selection is narrowed further to locations in the English Midlands (map shown). In order to adjust projected values from the model according to the connectivity of the crops (e.g. for pest dispersal), dispersal is switched on and set to a 2D Gaussian dispersal function with an average dispersal distance of 10km. The five boxplots show the distribution of projected model values in the selected potato crops for May through to September. In this example the results are presented as the percentage increase in risk compared to the current (baseline) climate, whereas you can opt to display the absolute values from the model. 
<p>
</p>
<p align="left">
  <img src="https://github.com/pskelsey/4C/blob/gh-pages/projectionsTabLarge.png">
</p>

## Motivation
This app was developed as a tool to help non-modellers perform state-of-the-art climate change risk assessments. At your fingertips are real crop / land-use data from [IACS](https://ec.europa.eu/agriculture/direct-support/iacs_en), [JACS](http://www.gov.scot/Topics/Statistics/Browse/Agriculture-Fisheries/PubFinalResultsJuneCensus), and [CROME](https://data.gov.uk/data/search?q=CROME), and [UKCP09](http://ukclimateprojections.metoffice.gov.uk/21678) spatially coherent probabilistic climate change data. Building a model and defining your future scenarios is just a matter of hitting a few switches and twiddling a few knobs. I've used this framework to produce [peer-reviewed journal articles](#references), and you can too. 

### Installation and loading
NOTE: Due to the many controls and features of the app, the GUI is a fixed size (12") and not 'responsive,' i.e. it will not scale to fit the screen of your device. This means it may not be suitable for notebooks with smaller screens, and is best suited for desktop PCs. 
To make sure you get the latest release, click on the 'release' button near the top of the page:

<p align="left">
  <img src="https://github.com/pskelsey/4C/blob/gh-pages/download.PNG">
</p>

Then click on the executable file at the top of the Assets list - _cropConnectivityUnderClimateChange.exe_. This will download a web-based installer to your computer, so you will need an internet connection to install the app. When you run the installer, it will download MATLAB Runtime to your computer (if required). MATLAB Runtime is a royalty-free standalone set of shared libraries that enables the execution of compiled MATLAB applications on computers that do not have MATLAB installed. If you have an up-to-date version of MATLAB then this step will be skipped. MATLAB Runtime requires approximately 1GB of disk space so it may take some time to install. Once installation of Runtime is complete the app will load quickly using the shortcuts provided. When the app is loading a splash screen will appear then disappear, and there will be a short interval before the app loads; there is no need to try and load it again, just be patient. 

### Documentation
A full guide on how to use the app to perform climate change risk assessments is provided in the [Documentation.md](https://github.com/pskelsey/4C/blob/master/docs/Documentation.md)

### References
[Skelsey, P. et al. 2017. Potential impacts of climate change on the threat of potato cyst nematode species in Great Britain. Plant Pathology, DOI: 10.1111/ppa12807.](http://onlinelibrary.wiley.com/doi/10.1111/ppa.12807/full)

[Skelsey, P. et al. 2016. Crop connectivity under climate change: future environmental and geographic risks of potato late blight in Scotland. Global Change Biology 22:3724–3738.](http://onlinelibrary.wiley.com/doi/10.1111/gcb.13368/full)

[Skelsey, P., and Newton, A.C. 2015. Future environmental and geographic risks of Fusarium head blight of wheat in Scotland. European Journal of Plant Pathology 142:133–147.](https://link.springer.com/article/10.1007/s10658-015-0598-7)

### License
The MIT License (MIT) 2017 - Peter Skelsey. For more details, please have a look at the [LICENSE](https://github.com/pskelsey/4C-model/blob/master/LICENSE) for more details.
