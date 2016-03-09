## Fundamental stages of algorithms

The algorithm toolbox is based on the assumption that all RR algorithms can be separated into three fundamental stages:<p> 

1. extraction of a respiratory signal (a time series dominated by respiratory modulation),

2. estimation of RR from that respiratory signal, and

3. fusion of multiple RRs to provide one output (optional).

## Specifying the structure of algorithms

The structure of the algorithms is specified by the `up.al.key_components` variable, under the "Algorithms" section in the _setup_universal_params.m_ script. Specification of the first two stages is compulsory, _extract_resp_sig_ and _estimate_rr_. The third stage, _fuse_rr_, is optional. For instance, to specify the simplest possible algorithms, without fusion, use:<p>
`up.al.key_components = {'extract_resp_sig', 'estimate_rr'};` <p>
Alternatively, the additonal fusion stage can be added using:<p>
`up.al.key_components = {'extract_resp_sig', 'estimate_rr', 'fuse_rr'};` <p>

Further details on the stages of the algorithms are provided in [this publication](http://peterhcharlton.github.io/RRest/yhvs_assessment.html).