RRest.m
% RRest runs RR algorithms on ECG and PPG signals using each possible
% combination of options, as specified in "setup_universal_params.m".

0 Sets universal parameters
1 Estimate RRs from ECG and PPG: Carry out processing for each stage of the algorithms
- Depending on the options and algorithms, evaluates each function/script with the dataset {'extract_resp_sig', 'estimate_rr', 'fuse_rr'}
  - extract_resp_sig: extracts respiratory signals from ECG and/or PPG signals using each of the chosen techniques.
        Inputs:
            up      - universal parameters structure
    
        Outputs:
            for each subject, n:
        n_int_respSigs.m     - a file of intermediate respiratory signals
        n_respSigs.m         - a file of respiratory signals for analysis            
  - estimate_rr:  estimates RR from respiratory signals using each possible set of RR estimation options
        Inputs:
            data            data files should be stored in the specified format
            up              universal parameters structure
    
        Outputs:
            for each subject, n:
        n_rrEsts.m      - a file of RR estimates  
  - fuse_rr
2 Conduct Signal Quality Assessment of Signals: Each window of ECG and PPG is quality assessed, 
  - calculate_sqi: calculates SQIs from the filtered ECG and PPG signals, evaluated for eachs signal window with 10s sub windows
  
  
3 Estimate Reference RRs

4 Calculate resp signal correlation coefficients

%% Statistical Analysis