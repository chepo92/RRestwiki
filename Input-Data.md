RRest requires a dataset on which to perform RR estimation. Several datasets are publicly available for use with RRest, as detailed [here](http://peterhcharlton.github.io/RRest/datasets.html). You may also wish to use your own dataset. This page provides an overview of how to provide Input Data to RRest.

## Using Publicly Available Datasets
[Publicly available datasets](http://peterhcharlton.github.io/RRest/datasets.html) are either provided in the required format for use with the RRest toolbox (such as the Vortal Dataset), or a 'data_importer' script is provided to download and re-format the data to prepare it for use with RRest (such as with the MIMICII Dataset). 'data_importer' scripts can be found 
[here](https://github.com/peterhcharlton/RRest/tree/master/Data_Import).

Once you have downloaded a dataset, you are ready to use RRest. You should specify its location to RRest in the _up.paths.root_folder_ variable, in the _setup_universal_params.m_ script.

## Using Your Own Datasets
_insert summary of how to format data_