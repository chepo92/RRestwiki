The _Universal Parameters_ are a set of parameters which are used throughout the toolbox. They specify:

## File Paths
A subset of the file paths are the only settings which **must** be set by each user to ensure that the analysis runs smoothly on their computer. These are easily found towards the top of _setup_universal_params.m_, under the heading "PARAMETERS TO BE SPECIFIED". Additional instructions are provided in the file itself.

## Algorithms
Further down the _setup_universal_params.m_ you will find a section titled "Specify the components of RR algorithms to be tested". The settings in this section specify which algorithms will be run. The following settings are recommended to run the full set of algorithms:

**Specify the components of the algorithms:** <p>
`up.al.key_components = {'extract_resp_sig', 'estimate_rr', 'fuse_rr'};`

## Analysis Settings