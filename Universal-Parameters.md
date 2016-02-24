The _Universal Parameters_ are a set of parameters which are used throughout the toolbox. The File Paths are the only settings which **must** be set by each user to ensure that the analysis runs smoothly on their computer. All other settings can be left alone unless you want to alter the analysis configurations:

# File Paths
These are easily found towards the top of _setup_universal_params.m_, under the heading "PARAMETERS TO BE SPECIFIED". Additional instructions are provided in the file itself.


# Algorithms
Further down the _setup_universal_params.m_ you will find a section titled "Specify the components of RR algorithms to be tested". The settings in this section specify which algorithms will be run. The following settings are recommended to run the full set of algorithms:

## Specify the stages of the algorithms:
Here, it is important to understand that the algorithm toolbox is based on the assumption that all RR algorithms can be separated into three fundamental stages:<p> 

1. extraction of a respiratory signal (a time series dominated by respiratory modulation),

2. estimation of RR from that respiratory signal, and optionally

3. fusion of multiple RRs to provide one output.

Specification of the first two is compulsory, _extract_resp_sig_ and _estimate_rr_. The third component, _fuse_rr_, is optional. For instance, to specify the simplest possible algorithms, without fusion, use:<p>
`up.al.key_components = {'extract_resp_sig', 'estimate_rr'};` <p>
Alternatively, the additonal fusion stage can be added using:<p>
`up.al.key_components = {'extract_resp_sig', 'estimate_rr', 'fuse_rr'};` <p>
Further details on the stages of the algorithms are provided in [this publication](http://peterhcharlton.github.io/RRest/yhvs_assessment.html).

## Specify the methods for extraction of respiratory signals:
Techniques for extraction of respiratory signals have been categorised into one of two methods: filter-based extraction, and feature-based extraction. Filter-based extraction includes techniques such as band-pass filtering to eliminate non-respiratory frequencies, and wavelet decomposition. Feature-based extraction consists of extracting a measurement, such as pulse wave amplitude, from each cardiac cycle. Any number of the following approaches, consisting of signal and respiratory signal extraction method, can be specified:<p>
`up.al.options.extract_resp_sig = {'ekg_filt', 'ppg_filt', 'ekg_feat', 'ppg_feat',};` <p>
Further details on the methods for extraction of respiratory signals are provided in [this publication](http://peterhcharlton.github.io/RRest/yhvs_assessment.html).

## Specify the components for feature-based extraction of respiratory signals:
If you choose to include the feature-based method for extraction of respiratory signals then you will need to specify (or leave alone) the components contained within this method for each signal:

1. Elimination of high frequencies (_EHF_);

2. PPG pulse peak or R-spike detection (_PDt_ or _RDt_);

3. Fiducial point identification (_FPt_);

4. Feature Measurement (_FMe_);

5. Re-sampling (_RS_);

6. Elimination of low frequencies (_ELF_).

These are specified for each signal using the following:
`up.al.sub_components.ppg_feat = {'EHF', 'PDt', 'FPt', 'FMe', 'RS', 'ELF'};` <p>
`up.al.sub_components.ekg_feat = {'EHF', 'RDt', 'FPt', 'FMe', 'RS', 'ELF'};` <p>
It is recommended that these are left alone. Further details on the components for feature-based extraction of respiratory signals are provided in [this publication](http://peterhcharlton.github.io/RRest/yhvs_assessment.html).

## Specify the technique(s) to be used for each component of feature-based extraction of respiratory signals:
Now that the components of feature-based extraction have been specified, you can specify which technique(s) you would like to use for each component. If you specify multiple techniques for any component, then the code will run all possible combinations of the specified techniques. At least one techniques should be specified for each of the following components:

### Beat detection
One PPG Pulse peak detector has been implemented: the Incremental-Merge Segmentation algorithm presented in [this publication](10.1109/EMBC.2012.6346628).<p>
`up.al.options.PDt = {'IMS'};`

One ECG Beat detector has been used with the toolbox: the _rpeakdetect.m_ function written by Prof G. Clifford, which is available [here](http://www.mit.edu/~gari/CODE/ECGtools/ecgBag/rpeakdetect.m).<p>
`up.al.options.RDt = {'GC'};`

### Feature Measurement
Several techniques for measurement of features in ECG and/or PPG signals have been implemented. A brief description of each technique is provided in [this publication](http://peterhcharlton.github.io/RRest/yhvs_assessment.html).

1. PPG Pulse Width (_pulW_ , [ref](https://zaguan.unizar.es/record/31895))

2. Amplitude Modulation (_am_ , [ref](doi.org/10.1109/TBME.2013.2246160))

3. Frequency Modulation (_fm_ , [ref](doi.org/10.1109/TBME.2013.2246160))

4. Baseline Wander (_bw_ , [ref](http://peterhcharlton.github.io/RRest/yhvs_assessment.html))

5. Peak Amplitude (_pk_ , [ref](doi.org/10.1109/TBME.2013.2246160))

6. Trough Amplitude (_on_ , [ref](doi.org/10.1109/ICASSP.2010.5495584))

7. Mean Baseline Wander (_bwm_ , [ref](doi.org/10.1109/ICASSP.2010.5495584))

8. QRS duration (_qrsW_ , [ref](http://medicalresearchjournal.org/index.php/GJMR/article/view/315))

9. QRS area (_qrsA_ , [ref](http://ieeexplore.ieee.org/xpls/abs_all.jsp?arnumber=5738022))

10. Principle Component Analysis (_pca_ , [ref](doi.org/10.1109/TBME.2012.2186448)): _note that for this the freely available toolbox written by the LS-SVMlab, [here](http://www.esat.kuleuven.be/sista/lssvmlab/), was used._

Use the following to specify all implemented techniques:<p>
`up.al.options.FMe = {'pulW', 'am', 'fm', 'bw', 'pk', 'on', 'bwm', 'qrsW', 'qrsA', 'pca'};`


### Re-sampling

### Elimination of low frequencies

Further details on the implemented techniques are provided in [this publication](http://peterhcharlton.github.io/RRest/yhvs_assessment.html).

## Analysis Settings