<p align="left">
  <img width="212" height="166"  src="https://github.com/pskelsey/4C/blob/gh-pages/4CLogo.png">
</p>


# Crop Connectivity under Climate Change

## Basic overview
A desktop app for performing climate change risk assessments in real crop locations in Great Britain. 
* Build your own risk model in a few easy clicks.
* Choose a crop species distribution to apply it in, or generate your own.
* Select a climate variable, a future time-period and month, and pick your greenhouse gas emissions scenario.
* Define the level of connectivity among crop locations, if desired.
* Hit the run button, visualise your results, and save them to create your own graphics. 

## Example
A risk function is selected from the drop-down menu and fit to some data for disease severity as a function of temperature. You could just as easily recreate the same risk function without any data. 

<p align="center">
  <img src="https://github.com/pskelsey/4C/blob/gh-pages/4CAppModelTab.png">
</p>
Temperature is selected as the variable of interest, for a low emissions scenario in the 2040s, and the model is applied in potato crops in the English Midlands (map shown). In order to weight the final results by the connectivity of the crops (e.g., for pest dispersal), dispersal is switched on and set to a 2D Gaussian dispersal function with an average dispersal distance of 10km. The boxplots show the distribution of projected values for May through to September, which in this instance, show the percentage increase in risk compared to the current (baseline) climate. 

<p align="left">
  <img src="https://github.com/pskelsey/4C/blob/gh-pages/4CAppProjectionsTab.png">
</p>

## Motivation
This app was developed so that anybody can perform a state-of-the-art climate change risk assessment. Many scientists have no modelling experience but want to realise the future implications of their experimental results. Many people working in, e.g., planning and development, the agriculture sector, environment agenices have no data and no modelling experience, but still have questions regarding the likelihood of climate change impacts in GB. The app brings together real crop / land-use data from IACS, JACS, and [CROME](https://data.gov.uk/data/search?q=CROME), and UKCP09 spatially coherent probabilistic climate change data, all under one roof. Selecting what you want is just a matter of hitting a few switches and twiddling a few knobs. I've used this framework to produce several peer-reviewed journal articles, and you can too. 

### Installation


### Documentation


### License
