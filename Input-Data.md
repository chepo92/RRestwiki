_RRest_ requires a dataset on which to perform RR estimation. Several datasets are publicly available for use with _RRest_, as detailed [here](http://peterhcharlton.github.io/RRest/datasets.html). You may also wish to use your own dataset. This page provides an overview of how to provide Input Data to RRest.

## Using Publicly Available Datasets
[Publicly available datasets](http://peterhcharlton.github.io/RRest/datasets.html) are either provided in the required format for use with the RRest toolbox (such as the Vortal Dataset), or a 'data_importer' script is provided to download and re-format the data to prepare it for use with RRest (such as with the MIMICII Dataset). 'data_importer' scripts can be found 
[here](https://github.com/peterhcharlton/RRest/tree/master/Data_Import).

Once you have downloaded a dataset, you are ready to use RRest. You should specify its location to _RRest_ in the _up.paths.root_data_folder_ variable, in the _setup_universal_params.m_ script.

## Using Your Own Datasets
You may alternatively wish to analyse your own dataset with _RRest_. There are three steps to doing so: formatting the your dataset correctly, saving it in the appropriate location, and calling _RRest_ appropriately. These are now explained:

### Formatting your dataset
The easiest way to understand how to format your dataset for use with _RRest_ is to look at an example, such as the synthetic dataset presented [here](http://peterhcharlton.github.io/RRest/synthetic_dataset.html).

A dataset must be stored in a Matlab structure array called _data_ to be used with _RRest_. The structure array should be of dimension [1, n], where n is the number of recordings. The structure array should contain the following fields:

* _id_ : _e.g._ `data(1).id = '001'` , `data(2).id = '002'` , _etc._
* _pleth_ : _e.g._ `data(1).pleth.fs = 125` , specifying the sampling rate in Hz, and `data(1).pleth.signal_e_vlf.y.v = [1,2,3,2,1]` , where [1,2,3,2,1] is the row vector of PPG values for this recording.


### Saving your dataset in the appropriate location
Take the following steps to ensure that your data is saved in an appropriate location for _RRest_ to be able to find it:

1. Create a directory called _MYDATA_

2. Specify _up.paths.root_folder_ as the directory which contains the newly created _MYDATA_ directory. This variable is set in the _setup_universal_params.m_ script.

3. Save your dataset as _mydata.mat_, in the _MYDATA_ directory.

### Calling _RRest_ to analyse your dataset
Use the following command to call _RRest_ When using your own dataset:

`RRest('mydata')`