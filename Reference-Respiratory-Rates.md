The toolbox of algorithms is designed to evaluate the performance of RR algorithms. Reference RRs are required to compare to the RRs estimated by the RR algorithms. The toolbox provides several methods for obtaining reference RRs. These are, in order of preference:

## Extracting RRs from a simultaneous respiratory signal
### Using a breath detection technique
RRs can be extracted from a simultaneous respiratory signal using a threshold breath-detection technique; _i.e._ when the signal rises above a specified threshold value, this is marked as a breath. Optimal thresholds have been derived for both thoracic impedance signals and oral-nasal pressure signals, using the methodology described in [this publication](http://peterhcharlton.github.io/RRest/yhvs_assessment.html). The disadvantage of this approach is that it requires a validated threshold for breath detection, which is not always available.

### Using independent techniques for RR estimation
An alternative, more generalisable approach, is to estimate RRs for each window using two independent signal processing techniques, and to only report RRs for those windows for which both techniques agree to within a certain tolerance. For instance, in [this publication](http://doi.org/10.1007/978-3-319-18191-2_10) the approach taken was to estimate RRs for each window using a time-domain breath detection technique, where each peak in the signal was identified as a breath, and a frequency-domain spectral analysis technique, using the fast Fourier Transform. This approach has been adapted in [this publication](http://peterhcharlton.github.io/RRest/waveform_analysis.html) and implemented in the toolbox.

## Extracting RRs from breath timings
If a dataset contains annotations of breath timings then the toolbox can use these to estimate Reference RRs.

## Extracting RRs from monitor readouts
If a dataset contains monitor readouts of RR then the toolbox can use these to estimate Reference RRs.