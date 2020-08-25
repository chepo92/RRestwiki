## Analysis_files


## Outputs to: Analysis_files\Component_Data

for each subject, N, the following files are made:
- N_int_respSigs      intermediate respiratory signals,
- N_respSigs          final respiratory signals
- N_rrEsts            RR estimates
- N_rrRef             Reference RR values
- N_sqi               Signal Quality Index values
- N_cc                resp signal correlation coefficients     
- N_wins              windows in the respiratory signals on which to perform RR estimation, expressed as start and end time 
    
for the entire dataset, the following files are made:
- alg_names           Names of RR algorithms tested
- win_data            Data for every algorithm tested, every window, and every subject.
- BA_global           Limits of Agreement analysis files containing Bland-Altman analysis results 
- BA_imp              Limits of Agreement analysis files containing Bland-Altman analysis results for impedance
- study_stats         file containing other statistical analysis results
- up                  universal parameters configuration
- win_data_imp        Table of Impedance Results for each window                        



## Outputs to: Analysis_files\Data_for_Analysis

- The dataset


## Outputs to: Analysis_files\Results\Figures
- Optional figures


## Outputs to: Analysis_files\Results\Tables

for each group, G, the following files are made:
- BA_results_table_G.xls
- results_table_G.xls
- stats_results_table_G.xls

for the entire dataset, the following files are made:
- BA_results_table_entire.xls
- results_table_entire.xls
- stats_results_table_entire.xls

### Above files have the following columns in common
- alg_no	
- m_xa	
- m_xb	
- m_ef	
- m_et	
- m_fm	
- m_ft	
- alg_name
- signal	

### BA_results_table_XX also has the following columns: 
- bias	
- two_sd	
- prop_wins_est	
- prop_wins_ref_and_good_sqi

### results_table_XX also has the following columns: 
- two_sd	
- bias	
- cp2	
- percerr: Percentage error	    
- mae: Mean (SD) absolute error
- sdae	
- rmse: Root mean square error	
- prop_wins_ref_and_good_sqi	
- prop_wins_est	
- total_wins_all


### stats_results_table_XX also has the following columns: 
- percerr: Percentage error	 	
- mae: Mean (SD) absolute error	
- sdae	
- rmse: Root mean square error		
- cp2: Coverage Probability: the proportion of estimated RRs which are within 2 bpm of the reference (ref)
- prop_wins_est: Proportion of windows for which an RR estimate is calculated
- total_wins_all: Total number of windows used in analysis

