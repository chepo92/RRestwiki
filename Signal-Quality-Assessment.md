The toolbox contains a signal quality algorithm which is used to determine the quality of segments of ECG and PPG signals.
This allows for automated detection of low quality segments, perhaps caused by motion artifact or poor sensor contact, which can then be eliminated from the analysis.

##Signal Quality Indices##

The algorithms, or Signal Quality Indices (SQIs), used in this toolbox are those published by Orphanidou _et al._ [here](http://doi.org/10.1109/JBHI.2014.2338351).
A summary of the algorithms is provided in Section 3.5 of [this publication](http://iopscience.iop.org/article/10.1088/0967-3334/37/4/610#pmeaaa1942s3).
Briefly, individual heart beats are detected in a segment of the original signal.
The physiological plausibility of this set of heart beats is tested (_e.g._ by checking the calculated heart rate).
If the signal passes this set of checks, then template matching is used to quantify the similarity of the morphologies of each beat in the signal. 
If the similarity of the morphologies exceeds an empirical threshold, then this segment of signal is deemed to be of high quality.
If the segment fails any of these tests then it is deemed to be of low quality.

##The use of SQIs in _RRest_##

SQIs are used in _RRest_ to determine the quality of ECG and PPG signals.
The quality of each window is deemed to be either high or low.
Any windows deemed to be of low quality are excluded from the statistical analyses, ensuring that conclusions are only based on high quality signal segments.