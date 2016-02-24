If you are new to RRest it is recommended that you follow these steps to gain familiarity with the toolbox:

## Download a sample dataset
Several datasets are compatible with the toolbox (as listed [here](http://peterhcharlton.github.io/RRest/datasets.html)). Of these, the 'MIMICII' dataset is perhaps the easiest one to start with. To download the dataset use the Matlab script which is provided [here](blob/master/Data_Import/MIMICII_data_importer.m). This downloads the dataset and formats it appropriately for use with the toolbox (further details are given [here](https://github.com/peterhcharlton/RRest/wiki/Input-Data)).

## Amend the Universal Parameters
The _Universal Parameters_ are a set of parameters which are used throughout the toolbox. In particular, the File Paths must be set for your own computer. Apart from these, all other parameters can be left alone to get started.

## Run your first analysis
_RRest_ is the main script which runs the analysis. It takes a single input specifying the dataset to be analysed. Use a command such as this to run _RRest_:

`RRest('mimic')`