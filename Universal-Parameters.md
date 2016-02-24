The _Universal Parameters_ are a set of parameters which are used throughout the toolbox. They specify:

## File Paths
A subset of the file paths are the only settings which **must** be set by each user to ensure that the analysis runs smoothly on their computer. These are easily found towards the top of _setup_universal_params.m_, under the heading "PARAMETERS TO BE SPECIFIED". Additional instructions are provided in the file itself.

## Algorithms
Further down the _setup_universal_params.m_ you will find a section titled "Specify the components of RR algorithms to be tested". The settings in this section specify which algorithms will be run. The following settings are recommended to run the full set of algorithms:

**Specify the components of the algorithms:** <p>
Here, it is important to understand that the algorithm toolbox is based on the assumption that all RR algorithms can be separated into three fundamental components: (i) extraction of a respiratory signal (a time series dominated by respiratory modulation), (ii) estimation of RR from that respiratory signal, and optionally (iii) fusion of multiple RRs to provide one output. Specification of the first two _key components_ is compulsory, _extract_resp_sig_ and _estimate_rr_. The third component, _fuse_rr_, is optional.<p>
`up.al.key_components = {'extract_resp_sig', 'estimate_rr', 'fuse_rr'};`

## Analysis Settings