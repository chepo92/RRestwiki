The first fundamental stage of the RR algorithms is 'Extraction of Respiratory Signals', in which a time series dominated by respiratory modulation is extracted from the original physiological signal. For example, in this figure respiratory signals extracted from the ECG (upper plot) and PPG (lower plot) are shown alongside breaths (dots):

![Extraction of respiratory signals](https://cloud.githubusercontent.com/assets/9865941/13639447/af2e7a54-e608-11e5-8f26-58ba0aab83e0.png)

Techniques for extraction of respiratory signals have been categorised into one of two methods: filter-based extraction, and feature-based extraction. Filter-based extraction includes techniques such as band-pass filtering to eliminate non-respiratory frequencies, and wavelet decomposition. Feature-based extraction consists of extracting a measurement, such as pulse wave amplitude, from each cardiac cycle. Feature-based extraction is performed using several components, as shown below:

![The processes for extraction of respiratory signals](https://cloud.githubusercontent.com/assets/9865941/13639157/55122166-e607-11e5-9ed5-e56bac1d5c4c.png)

## Specify the approaches for extraction of respiratory signals:

Any number of the following approaches, consisting of signal and respiratory signal extraction method, can be specified under the 'Algorithms' section in the _setup_universal_params.m_ script:<p>
`up.al.options.extract_resp_sig = {'ekg_filt', 'ppg_filt', 'ekg_feat', 'ppg_feat',};` <p>

Further details on the methods for extraction of respiratory signals are provided in [this publication](http://peterhcharlton.github.io/RRest/yhvs_assessment.html).

## Specify the components for feature-based extraction of respiratory signals:
If you choose to include the feature-based method for extraction of respiratory signals then the components contained within this method are specified as:

1. Elimination of very high frequencies (_EHF_);

2. Beat detection: PPG pulse peak or R-spike detection (_PDt_ or _RDt_);

3. Fiducial point identification (_FPt_);

4. Extraction of Feature Measurements (_FMe_);

5. Re-sampling at a regular sampling frequency (_RS_);

6. Elimination of very low frequencies (_ELF_).

These are specified for each signal using the following:

`up.al.sub_components.ppg_feat = {'EHF', 'PDt', 'FPt', 'FMe', 'RS', 'ELF'};` <p>
`up.al.sub_components.ekg_feat = {'EHF', 'RDt', 'FPt', 'FMe', 'RS', 'ELF'};` <p>

It is recommended that these are left alone. Further details on the components for feature-based extraction of respiratory signals are provided in [this publication](http://peterhcharlton.github.io/RRest/yhvs_assessment.html).

## Specify the interchangeable technique(s) to be used for each component of feature-based extraction of respiratory signals:
Now that the components of feature-based extraction have been specified, you can specify which technique(s) you would like to use for each component. If you specify multiple techniques for any component, then the code will run all possible combinations of the specified techniques. At least one techniques should be specified for each of the following components:

### Beat detection
PPG Pulse peak detection, Available methods: 
1. 'DCl'

2. 'COr'

3. 'IMS', the Incremental-Merge Segmentation algorithm presented in [this publication](http://doi.org/10.1109/EMBC.2012.6346628).<p>

These are specified for PPG signal using the following:
`up.al.options.PDt = {'DCl', 'COr', 'IMS'};`

ECG Beat detection
1. 'GC' the _rpeakdetect.m_ function written by Prof G. Clifford, which is available [here](http://www.mit.edu/~gari/CODE/ECGtools/ecgBag/rpeakdetect.m).<p>
2. 'ME'

These are specified for EKG signal using the following:
`up.al.options.RDt = {'GC', 'ME'};`

### Feature Measurement
Several techniques for measurement of features in ECG and/or PPG signals have been implemented. A brief description of each technique is provided in [this publication](http://peterhcharlton.github.io/RRest/yhvs_assessment.html). Use the following to specify all implemented techniques:<p>
`up.al.options.FMe = {'am', 'fm', 'bw', 'bwm', 'pk', 'on', 'qrsW', 'qrsA', 'pca', 'pulW', 'qrS', 'rsS', 'Rang'};`

The techniques are as follows:

1. Amplitude Modulation (_am_ , [ref](http://doi.org/10.1109/TBME.2013.2246160))

2. Frequency Modulation (_fm_ , [ref](http://doi.org/10.1109/TBME.2013.2246160))

3. Baseline Wander (_bw_ , [ref](http://peterhcharlton.github.io/RRest/yhvs_assessment.html))

4. Mean Baseline Wander (_bwm_ , [ref](http://doi.org/10.1109/ICASSP.2010.5495584))

5. Peak Amplitude (_pk_ , [ref](http://doi.org/10.1109/TBME.2013.2246160))

6. Trough Amplitude (_on_ , [ref](http://doi.org/10.1109/ICASSP.2010.5495584))

7. QRS duration (_qrsW_ , [ref](http://medicalresearchjournal.org/index.php/GJMR/article/view/315))

8. QRS area (_qrsA_ , [ref](http://ieeexplore.ieee.org/xpls/abs_all.jsp?arnumber=5738022))

9. Principle Component Analysis (_pca_ , [ref](http://doi.org/10.1109/TBME.2012.2186448)): _note that for this the freely available toolbox written by the LS-SVMlab, [here](http://www.esat.kuleuven.be/sista/lssvmlab/), was used._

10. PPG Pulse Width (_pulW_ , [ref](https://zaguan.unizar.es/record/31895))

11. (_qrS_)

12. (_rsS_)

13. (_Rang_)

### Re-sampling

Next the irregularly-sampled feature-based respiratory signals are resampled at a constant sampling rate using linear interpolation (_lin_), cubic spline interpolation (_cub_), or [Berger's method](doi.org/10.1109/TBME.1986.325789) (_brg_). 

These techniques can be optionally followed by band-pass filtering if desired, by adding _B_ to the end of the name. 

The possible options are:

`up.al.options.RS = {'lin', 'linB', 'cub', 'cubB', 'brg', 'brgB'};`

## Specify the interchangeable techniques for filter-based extraction of respiratory signals:
Similarly, the techniques to be used for filter-based extraction of respiratory signals must be specified. A brief description of each technique is provided in [this publication](http://peterhcharlton.github.io/RRest/yhvs_assessment.html). Use the following to specify all implemented techniques for use on both ECG and PPG signals:<p>
`up.al.options.ekg_filt = {'Wfm', 'Wam', 'CCF', 'BFi'};`<p>
`up.al.options.ppg_filt = {'Wfm', 'Wam', 'CCF', 'BFi'};`<p>

The techniques are as follows:

1. Band-pass filtering (_BFi_ , [ref](http://www.ncbi.nlm.nih.gov/pubmed/1293445))

2. Filtering using the centred-correntropy function (_CCF_ , [ref](http://doi.org/10.1371/journal.pone.0086427))

3. Wavelet extraction of frequency modulation (_Wfm_ , [ref](http://www.worldscientific.com/doi/abs/10.1142/S0219691304000329))

4. Wavelet extraction of amplitude modulation (_Wam_ , [ref](http://www.worldscientific.com/doi/abs/10.1142/S0219691304000329))
