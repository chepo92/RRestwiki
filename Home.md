1. <a href="#what_is">What Is RRest?</a>
2. <a href="#what_does">What does RRest do?</a>
3. <a href="#why">Why is RRest helpful?
4. <a href="#how_design">How is RRest designed?
5. <a href="#how_more">How can I find out more?
6. <a href="#what_not">What does RRest not do?

<a name="what_is" />
# What is RRest
RRest is a toolbox of algorithms for estimation of respiratory rate from physiological signals. It is written in Matlab format, and contains a wide range of algorithms previously reported in the literature. It is one part of a larger, [Respiratory Rate Estimation](http://peterhcharlton.github.io/RRest/) project. The project also contains additional material such as [data](http://peterhcharlton.github.io/RRest/datasets.html) to use with the algorithms, [publications](http://peterhcharlton.github.io/RRest/publications.html) arising from the project, and details of how to [contribute](http://peterhcharlton.github.io/RRest/contributions.html).

<a name="what_does" />
# What does RRest do?
RRest estimates respiratory rate from windows of electrocardiogram (ECG) and pulse oximetry (photoplethysmogram, PPG) signals. It also estimates a reference respiratory rate from a simultaneous respiratory signal, such as an Impedance Pneumography signal.

<a name="why" />
# Why is RRest helpful?
RRest is a helpful resource for researchers in the field of respiratory rate estimation. It provides a set of RR algorithms for use with the ECG and PPG. This is helpful for:

1. **Comparing algorithms**: Perhaps you have developed a novel RR algorithm, and now you want to compare it to an existing algorithm. RRest provides many algorithms which have been implemented, verified, and published (for further details see [this publication](http://peterhcharlton.github.io/RRest/yhvs_assessment.html)).

2. **Evaluating algorithms**: RRest also facilitates statistical analysis of the performance of algorithms. Many of the statistics which have previously been used to evaluate the performance of algorithms are calculated by the code.

3. **Developing algorithms**: When developing algorithms for estimation of respiratory rate it is often prudent to begin with an existing algorithm, and tweak it to make improvements, rather than to start from scratch. RRest provides many of the fundamental algorithms described in the literature, allowing researchers to take existing algorithms and develop them further.

<a name="how_design" />
# How is RRest designed?

<a name="how_more" />
# How can I find out more?

<a name="what_not" />
# What does RRest not do?
As stated in the licence accompanying the source code, the algorithms are not intended to be fit for any purpose. Please see the [licence](https://github.com/peterhcharlton/RRest/blob/master/LICENSE) for further details. RRest will also not fly you to the moon and back. However, it may be reasonable to presume that similar algorithms were used to monitor the respiratory rate of the parachutist in the [Red Bull Stratos project](http://www.ncbi.nlm.nih.gov/pubmed/24597163), albeit applied to a strain gauge rather than the ECG or PPG.


***