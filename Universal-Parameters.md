The _Universal Parameters_ are a set of parameters which are used throughout the toolbox. The File Paths are the only settings which **must** be set by each user to ensure that the analysis runs smoothly on their computer. All other settings can be left alone unless you want to alter the analysis configurations:

# File Paths
These are easily found towards the top of _setup_universal_params.m_, and should be specified for your specific computer.

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

## Specify the interchangeable technique(s) to be used for each component of feature-based extraction of respiratory signals:
Now that the components of feature-based extraction have been specified, you can specify which technique(s) you would like to use for each component. If you specify multiple techniques for any component, then the code will run all possible combinations of the specified techniques. At least one techniques should be specified for each of the following components:

### Beat detection
One PPG Pulse peak detector has been implemented: the Incremental-Merge Segmentation algorithm presented in [this publication](http://doi.org/10.1109/EMBC.2012.6346628).<p>
`up.al.options.PDt = {'IMS'};`

One ECG Beat detector has been used with the toolbox: the _rpeakdetect.m_ function written by Prof G. Clifford, which is available [here](http://www.mit.edu/~gari/CODE/ECGtools/ecgBag/rpeakdetect.m).<p>
`up.al.options.RDt = {'GC'};`

### Feature Measurement
Several techniques for measurement of features in ECG and/or PPG signals have been implemented. A brief description of each technique is provided in [this publication](http://peterhcharlton.github.io/RRest/yhvs_assessment.html). Use the following to specify all implemented techniques:<p>
`up.al.options.FMe = {'am', 'fm', 'bw', 'bwm', 'pk', 'on', 'qrsW', 'qrsA', 'pca', 'pulW'};`

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

### Re-sampling

Next the irregularly-sampled feature-based respiratory signals are resampled at a constant sampling rate using linear, interpolation, cubic spline interpolation, or [Berger's method](doi.org/10.1109/TBME.1986.325789). These techniques can be optionally followed by band-pass filtering if desired, by adding _B_ to the end of the name. The possible options are:

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

## Specify the interchangeable technique(s) for RR Estimation
The techniques to be used for estimation of RRs from respiratory signals must be specified. A brief description of each technique is provided in [this publication](http://peterhcharlton.github.io/RRest/yhvs_assessment.html). Use the following to specify all implemented techniques for use on both ECG and PPG signals:<p>
`up.al.options.estimate_rr = {'FTS', 'ARS', 'ARM', 'ARP', 'ARPz', 'ACF', 'WCH', 'PKS', 'ZeX', 'PZX', 'CtO', 'CtA'};`

The techniques can be split into frequency- and time-domain techniques. The frequency-domain techniques are as follows:

1. Fourier Transform (_FTS_ , [ref](http://doi.org/10.1109/TBME.2013.2246160))

2. Auto-regressive spectral analysis (_ARS_, [ref](http://doi.org/10.1109/MEMB.2002.1032638))

3. Auto-regressive spectral analysis using the median spectrum for orders 2-20 (_ARM_, [ref](http://doi.org/10.3109/03091902.2015.1105316))

4. Auto-regressive all-pole modelling (_ARP_, [ref](http://doi.org/10.1109/IEMBS.2008.4649554))

5. Auto-regressive all-pole modelling with the lowest frequency pole corresponding to RR (_ARPz_, [ref](http://www.waset.org/publications/13323))

6. Autocorrelation Function (_ACF_, [ref](http://doi.org/10.1007/s10439-007-9428-1))

7. Welch Periodogram (_WCH_, [ref](https://zaguan.unizar.es/record/31895?ln=en))

The time-domain techniques are as follows:

1. Peak detection (_PKS_)

2. Zero-crossing breath detection (_ZeX_, [ref](http://doi.org/10.1007/BF02348427))

3. Combined breath detection using both peak detection and zero-crossings (_PZX_, [ref](http://www.ibme.ox.ac.uk/research/biomedical-signal-processing-instrumentation/prof-l-tarassenko/publications/pdf/s_fleming_thesis.pdf)

4. Count-orig (_CtO_, [ref](http://doi.org/10.1007/s10439-007-9428-1))

5. Count-adv (_CtA_, [ref](http://doi.org/10.1007/s10439-007-9428-1))