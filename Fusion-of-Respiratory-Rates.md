The third fundamental stage of the RR algorithms is 'Fusion of Respiratory Rate Estimates', in which multiple RR estimates are fused to provide one single output. This stage is optional.

## Specify the interchangeable technique(s) for Fusion of RR Estimates
The techniques to be used for fusion of RR estimates must be specified. A brief description of each technique is provided in [this publication](http://peterhcharlton.github.io/RRest/yhvs_assessment.html). Use the following to specify all implemented techniques for use on both ECG and PPG signals:
<p> `up.al.options.fuse_rr = {'fus_mod', 'fus_temp'};`
<p> `up.al.sub_components.fus_mod = {'SFu', 'SPA', 'PMC', 'PRC'};`
<p> `up.al.sub_components.fus_temp = {'TFu'};`

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