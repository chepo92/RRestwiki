The third fundamental stage of the RR algorithms is 'Fusion of Respiratory Rate Estimates', in which multiple RR estimates are fused to provide one single output. This stage is optional.

## Specify the interchangeable technique(s) for Fusion of RR Estimates
The techniques to be used for fusion of RR estimates must be specified. A brief description of each technique is provided in [this publication](http://peterhcharlton.github.io/RRest/yhvs_assessment.html). Use the following settings in _setup_universal_params.m_ to specify all implemented techniques for use on both ECG and PPG signals:
<p> `up.al.options.fuse_rr = {'fus_mod', 'fus_temp'};`
<p> `up.al.sub_components.fus_mod = {'SFu', 'SPA', 'PMC', 'PRC'};`
<p> `up.al.sub_components.fus_temp = {'TFu'};`

The techniques can be split into modulation- and temporal-fusion techniques. The modulation-fusion techniques are as follows:

1. Smart Fusion (_SFu_ , [ref](http://doi.org/10.1109/TBME.2013.2246160))

2. Spectral peak-conditioned averaging (_SPA_, [ref](https://zaguan.unizar.es/record/31895))

3. Pole magnitude criterion (_PMC_, [ref](http://doi.org/10.1016/j.bspc.2012.06.001))

4. Pole ranking criterion (_PRC_, [ref](http://doi.org/10.1109/ITAB.2009.5394435))

The temporal-fusion techniques are as follows:

1. Temporal smoothing (_TFu_, [ref](http://doi.org/10.1007/s11517-012-0954-0))