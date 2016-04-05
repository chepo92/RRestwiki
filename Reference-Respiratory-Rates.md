The toolbox of algorithms is designed to evaluate the performance of RR algorithms. Reference RRs are required to compare to the RRs estimated by the RR algorithms. The toolbox provides several methods for obtaining reference RRs. These are, in order of preference:

## Extracting RRs from a simultaneous respiratory signal
RRs are extracted from a simultaneous respiratory signal using a threshold breath-detection technique. _i.e._ when the signal rises above a specified threshold value, this is marked as a breath. Optimal thresholds have been derived for both thoracic impedance signals and oral-nasal pressure signals, using the methodology described in [this publication](http://peterhcharlton.github.io/RRest/yhvs_assessment.html).

## Extracting RRs from breath timings
If a dataset contains annotations of breath timings then the toolbox can use these to estimate Reference RRs.

## Extracting RRs from monitor readouts
If a dataset contains monitor readouts of RR then the toolbox can use these to estimate Reference RRs.