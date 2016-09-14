The _RRest_ toolbox is a continually evolving resource, with new versions made available from time to time. This page is designed to answer the questions _Which version should I use?_, and _What's the difference between versions?_.

The answers to these questions depend on whether you want to use _RRest_ to perform new studies, or to replicate existing studies:

## Performing new studies

If you are using _RRest_ to perform new studies then you should use the most recent version (_i.e._ the highest-numbered version). This is because over time the toolbox evolves to provide increased functionality, and to incorporate suggested changes from the research community. Therefore, if you use an older version, then your analysis will be based on at best an incomplete understanding of the state-of-the-art, and at worst an incorrect understanding of the state-of-the-art.

## Replicating published studies

If you are using _RRest_ to replicate a study from the literature, then you should use the same version as was used for that study. The studies which used each version of the toolbox are listed below. For instance, those gaining familiarity with the toolbox may wish to reproduce the study presented as a tutorial in [this publication](http://peterhcharlton.github.io/RRest/waveform_analysis.html). Version 1 of the toolbox should give an almost exact replication of this study.

### Version 1
* **[Waveform analysis to estimate respiratory rate](http://peterhcharlton.github.io/RRest/waveform_analysis.html)**: In this tutorial Version 1 of the toolbox was used to assess a few RR algorithms on ECG and PPG data from the [MIMIC II dataset](http://peterhcharlton.github.io/RRest/mimicii_dataset.html).

### Version 2
* **[An assessment of algorithms to estimate respiratory rate from the electrocardiogram and photoplethysmogram](http://peterhcharlton.github.io/RRest/yhvs_assessment.html)**: In this article Version 2 of the toolbox was introduced by assessing a wide range of existing RR algorithms on ECG and PPG data. Algorithm implementations were verified using the [Synthetic dataset](http://peterhcharlton.github.io/RRest/synthetic_dataset.html). Following this algorithms were applied to both the ECG and the PPG on the [Vortal dataset](http://peterhcharlton.github.io/RRest/vortal_dataset.html) (young subjects).

### Version 3
* **[Extraction of Respiratory Signals from the Electrocardiogram and Photoplethysmogram: Technical and Physiological Determinants](http://peterhcharlton.github.io/RRest/factors_assessment.html)**: 
In this article Version 3 of the toolbox was used to assess the influences of a range of technical and physiological factors on the quality of respiratory signals extracted from the ECG and PPG. Respiratory signals were extracted from the [Vortal dataset](http://peterhcharlton.github.io/RRest/vortal_dataset.html) (young and elderly subjects) using a wide range of techniques. The correlations of each extracted respiratory signal with a reference respiratory signal were calculated. This allowed us to investigate the effect of several technical factors (including site of PPG measurement, type of recording equipment, input signal (ECG or PPG) and sampling frequency), and physiological factors (including age, gender and respiratory rate) on the respiratory signals.


One should note that there are two potential reasons for discrepancies between the results provided by the toolbox, and those reported in the literature. Firstly, minor changes may be made to a version of the toolbox to ensure that it is easily accessible. This should only have a minor affect on results. Secondly, some publications use only part of the toolbox for their analysis, and fill in the gaps with their own analysis methods. In this instance, the results can be expected to be broadly similar, but not the same.