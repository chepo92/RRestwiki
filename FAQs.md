Here are a few of the questions that are frequently asked about _RRest_. These are continually updated, so if you have a question of your own feel free to [get in touch](http://peterhcharlton.github.io/RRest/contributions.html).

* <a href="#running_algs">How can I get the algorithms to run?</a>

* <a href="#subset_algs">How can I run only a subset of the algorithms?</a>

* <a href="#create_synth">How can I create the synthetic dataset?</a>

* <a href="#too_long">This is taking too long!</a>


<a name="running_algs" />

## How can I get the algorithms to run?

The algorithms should be relatively straightforward to run for the [datasets](http://peterhcharlton.github.io/RRest/datasets.html) provided. If you are having difficulty getting the algorithms to run then do have a look at the instructions provided for running the algorithms with the Synthetic Dataset [here](https://github.com/peterhcharlton/RRest/wiki/Getting-Started), which include an introductory [video](https://youtu.be/J4ZG3QntTI8).

<a name="subset_algs" />

## How can I run only a subset of the algorithms?

_RRest_ can be used to run many RR algorithms (several hundred) on multiple input signals (such as ECG and PPG).
However, you may only wish to run a subset of these algorithms, on a subset of input signals.
To do so, modify the [_Universal Parameters_](https://github.com/peterhcharlton/RRest/wiki/Universal-Parameters) accordingly.

For instance, you may only wish to run algorithms using a subset of the available feature measurement techniques. Perhaps you only want to use BW, AM and FM feature measurements. In this case you would modify `up.al.options.FMe`, which can be found in the _setup_universal_params.m_ script. Further instructions are given [here](https://github.com/peterhcharlton/RRest/wiki/Universal-Parameters#feats).

You may also only wish to use a subset of the available input signals, such as just the ECG. In this case you would similarly modify `up.al.options.extract_resp_sig`, within the _setup_universal_params.m_ script. Further instructions are given [here](https://github.com/peterhcharlton/RRest/wiki/Universal-Parameters#extract_resp_sigs).

<a name="create_synth" />

## How can I create the synthetic dataset?
The [synthetic dataset](http://peterhcharlton.github.io/RRest/synthetic_dataset.html) can be created using the Matlab &reg; script available [here](https://raw.githubusercontent.com/peterhcharlton/RRest/master/RRest_v2.0/Data_Import_Scripts/RRSYNTH_data_generater.m), which is within the overall script.

This will generated simulated ECG and PPG signals, subjected to the three respiratory modulations: baseline wander (BW), amplitude modulation (AM), and frequency modulation (FM).
If you only wish to generate a subset of these signals (such as only ECG, subject to only BW and AM), then you can do so by specifying the required signals and modulations in `setup_params` function.

<a name="too_long" />

## This is taking too long!
If you find that the processing is taking too long, then it may be helpful to try conducting a smaller set of processing to begin with. There are a couple of steps you can take to speed things up in the first instance:

* **Conduct the processing on a smaller number of subjects:** You can discard subjects from a Matlab &reg; data file by editing the file in Matlab &reg;.

* **Use a subset of the available algorithms:** The toolbox is set up to run a complete analysis over all the possible algorithms. However, some of the algorithms take much longer than others to run. Therefore, you can reduce the run-time considerably by following the instructions <a href="#subset_algs">here</a>. In particular, the _pca_ technique specified in `up.al.options.FMe` takes a long time, so it would be prudent to eliminate this to begin with. Furthermore, you can eliminate the fusion step of the algorithms by removing the entry from `up.al.key_components`.