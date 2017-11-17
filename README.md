<p align="left">
  <img width="212" height="166"  src="https://github.com/pskelsey/4C/blob/gh-pages/4CLogo.png">
</p>


# **_4C model_**: **C**rop Connectivity under Climate Change

## Basic overview
A desktop app for performing climate change risk assessments in real crop locations in Great Britain. 
* Build your own risk model in a few easy clicks.
* Choose a crop species distribution to apply it in, or generate your own.
* Select a climate variable, a future time-period and month, and pick your greenhouse gas emissions scenario.
* Define the level of connectivity among crop locations, if desired.
* Hit the run button, visualise your results, and save them to create your own graphics. 

## Example
A risk function is selected from the drop-down list and fitted to some data for the proportion of plants infected as a function of temperature. If you have no data you can still select a model from the drop-down list and manually adjust the parameter values to suit, or define your own function in the box provided. 

<p align="center">
  <img src="https://github.com/pskelsey/4C/blob/gh-pages/modelsTabLarge.png">
</p>
Temperature is selected as the variable of interest, for a low emissions scenario in the 2040s, and the model is applied in potato crops in the English Midlands (map shown). In order to adjust projected future values according to the connectivity of the crops (e.g., for pest dispersal), dispersal is switched on and set to a 2D Gaussian dispersal function with an average dispersal distance of 10km. The boxplots show the distribution of projected values for May through to September, which in this instance, show the percentage increase in risk compared to the current (baseline) climate. 
<p>
  
</p>
<p align="left">
  <img src="https://github.com/pskelsey/4C/blob/gh-pages/projectionsTabLarge.png">
</p>

## Motivation
This app was developed as a tool to help non-modellers perform a state-of-the-art climate change risk assessment. At your fingertips are real crop / land-use data from [IACS](https://ec.europa.eu/agriculture/direct-support/iacs_en), [JACS](http://www.gov.scot/Topics/Statistics/Browse/Agriculture-Fisheries/PubFinalResultsJuneCensus), and [CROME](https://data.gov.uk/data/search?q=CROME), and [UKCP09](http://ukclimateprojections.metoffice.gov.uk/21678) spatially coherent probabilistic climate change data. Building a model and defining your future scenarios is just a matter of hitting a few switches and twiddling a few knobs. I've used this framework to produce [peer-reviewed journal articles](#references), and you can too. 

### Installation and loading
NOTE: Due to the many controls and features of the app, the GUI is a fixed size (12") and not 'responsive,' i.e., it will not scale to fit the screen of your device. This means it may not be suitable for notebooks with smaller screens, and is best suited for desktop PCs. 
Use the green 'Clone or download' button near the top of the page to download the zip file containing a web-based installer. The installer will download MATLAB Runtime to your computer, which is a free standalone set of shared libraries that enables the execution of compiled MATLAB applications on computers that do not have MATLAB installed. If you have an up-to-date version of MATLAB then this step will be skipped. MATLAB Runtime requires approximately 1GB of disk space so it may take some time to install. Once installation is complete the app will load quickly using the shortcuts provided. When the app is loading a splash screen will appear then disappear, and there will be a short interval before the app loads; there is no need to try and load it again, just be patient.

### Documentation
A full guide on how to use the app to perform climate change risk assessments is provided [HERE](https://github.com/pskelsey/4C/blob/master/docs/Documentation.md)

### References
[Skelsey, P. et al. 2016. Crop connectivity under climate change: future environmental and geographic risks of potato late blight in Scotland. Global Change Biology 22:3724–3738.](http://onlinelibrary.wiley.com/doi/10.1111/gcb.13368/full)

[Skelsey, P., and Newton, A.C. 2015. Future environmental and geographic risks of Fusarium head blight of wheat in Scotland. European Journal of Plant Pathology 142:133–147.](https://link.springer.com/article/10.1007/s10658-015-0598-7)

### License
