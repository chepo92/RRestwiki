The toolbox provides a range of statistics to assess the performance of RR algorithms against reference RRs:

## Traditional Statistics
Several widely used statistics are reported by the toolbox in the _stats_results_table_, including:
* Percentage error
* Mean (SD) absolute error
* Root mean square error
* Coverage Probability: the proportion of estimated RRs which are within 2 bpm of the reference [ref](http://doi.org/10.1080/10543400701376480)
* Proportion of windows for which an RR estimate is calculated
* Total number of windows used in analysis

## Limits of Agreement analysis
The toolbox also calculates the limits of agreement between an algorithm's estimated RRs and the reference RRs using the technique reported by Bland-Altman [ref](http://doi.org/10.1080/10543400701329422). This approach accounts for repeated measures from individual subjects. The results are given as the bias and limits of agreement in the _BA_results_table_.

## Sub-group analysis
The toolbox automatically produces results tables for the entire dataset, as well as for the sub-groups specified by the _group_ field in the input data.