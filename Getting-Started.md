If you are new to RRest it is recommended that you follow these steps to gain familiarity with the toolbox:

## Download a sample dataset
Several datasets are compatible with the toolbox (as listed [here](http://peterhcharlton.github.io/RRest/datasets.html)). Of these, the 'VORTAL_rest' dataset is perhaps the easiest one to start with. The dataset can be downloaded from [here](http://peterhcharlton.github.io/RRest/vortal_dataset.html).

## Amend the Universal Parameters
The _Universal Parameters_ are a set of parameters which are used throughout the toolbox. In particular, the File Paths must be set for your own computer as detailed [here](https://github.com/peterhcharlton/RRest/wiki/Universal-Parameters). Apart from these, all other parameters can be left alone to get started.

## Run your first analysis
_RRest_ is the main script which runs the analysis. It takes a single input specifying the dataset to be analysed, such as the 'mimic' dataset. Use a command such as this to run _RRest_:

`RRest('VORTAL_rest')`