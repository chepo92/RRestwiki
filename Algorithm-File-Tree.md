
algorithms
│   RRest.m
│   RRest.prj
│   setup_universal_params.m
│
├───calculate_cc
│       calculate_resp_sig_cc.m
│
├───calculate_sqi
│       calculate_sqi.m
│
├───calc_stats
│       calc_stats.m
│       create_table_of_algorithms.m
│       create_table_of_algorithms_comb.m
│       find_rel_subjs.m
│       specific_vortal_plots.m
│       specific_vortal_stats.m
│
├───estimate_ref_rr
│       estimate_ref_rr.m
│
├───estimate_rr
│       ACF.m
│       ARM.m
│       ARP.m
│       ARPz.m
│       ARS.m
│       CtA.m
│       CtO.m
│       estimate_rr.m
│       find_spectral_peak.m
│       FTS.m
│       identify_subj_wins.m
│       PKS.m
│       PZX.m
│       WCH.m
│       ZeX.m
│
├───extract_resp_sig
│   │   extract_resp_sig.m
│   │   lp_filter_signal_to_remove_freqs_above_resp.m
│   │
│   ├───feat_based_extraction
│   │   │   downsample_data.m
│   │   │   EHF.m
│   │   │   ELF.m
│   │   │   FMe.m
│   │   │   FPt.m
│   │   │   LSSVMlabv1_8_R2009b_R2011a.zip
│   │   │   PDt.m
│   │   │   RDt.m
│   │   │   rpeakdetect.m
│   │   │   RS.m
│   │   │
│   │   ├───COr_peak_detector
│   │   │       co_ppg_peak_detector.m
│   │   │       parafilt.mat
│   │   │
│   │   ├───GC_qrs_detector
│   │   │       rpeakdetect.m
│   │   │
│   │   ├───IMS_peak_detector
│   │   │       adaptPulseSegment.m
│   │   │
│   │   └───LSSVMlabv1_8_R2009b_R2011a
│   │           AFEm.m
│   │           bay_errorbar.m
│   │           bay_initlssvm.m
│   │           bay_lssvm.m
│   │           bay_lssvmARD.m
│   │           bay_modoutClass.m
│   │           bay_optimize.m
│   │           bay_rr.m
│   │           bitreverse32.m
│   │           changelssvm.m
│   │           cilssvm.m
│   │           code.m
│   │           codedist_bay.m
│   │           codedist_hamming.m
│   │           codedist_loss.m
│   │           codelssvm.m
│   │           code_ECOC.m
│   │           code_MOC.m
│   │           code_OneVsAll.m
│   │           code_OneVsOne.m
│   │           crossvalidate.m
│   │           crossvalidatelssvm.m
│   │           csa.m
│   │           democlass.m
│   │           democonfint.m
│   │           demofun.m
│   │           demomodel.m
│   │           demomulticlass.m
│   │           demo_fixedclass.m
│   │           demo_fixedsize.m
│   │           demo_yinyang.m
│   │           denoise_kpca.m
│   │           eign.m
│   │           gcrossvalidate.m
│   │           gcrossvalidatelssvm.m
│   │           gridsearch.m
│   │           initlssvm.m
│   │           kentropy.m
│   │           kernel_matrix.m
│   │           kernel_matrix2.m
│   │           kpca.m
│   │           latentlssvm.m
│   │           latticeseq_b2.m
│   │           leaveoneout.m
│   │           leaveoneoutlssvm.m
│   │           linesearch.m
│   │           linf.m
│   │           lin_kernel.m
│   │           lssvm.m
│   │           lssvmMATLAB.m
│   │           mae.m
│   │           medae.m
│   │           misclass.m
│   │           MLP_kernel.m
│   │           mse.m
│   │           plotlssvm.m
│   │           poly_kernel.m
│   │           postlssvm.m
│   │           predict.m
│   │           predlssvm.m
│   │           preimage_rbf.m
│   │           prelssvm.m
│   │           progress.m
│   │           range.m
│   │           RBF_kernel.m
│   │           rcrossvalidate.m
│   │           rcrossvalidatelssvm.m
│   │           ridgeregress.m
│   │           robustlssvm.m
│   │           roc.m
│   │           rsimplex.m
│   │           simann.m
│   │           simlssvm.m
│   │           simplex.m
│   │           smootherlssvm.m
│   │           tbform.m
│   │           trainlssvm.m
│   │           trimmedmse.m
│   │           tunelssvm.m
│   │           weightingscheme.m
│   │           windowize.m
│   │           windowizeNARX.m
│   │
│   ├───filt
│   │       BFi.m
│   │       CCF.m
│   │       ekg_filt.m
│   │       ppg_filt.m
│   │       tukey_win_data.m
│   │       Wam.m
│   │       Wfm.m
│   │
│   └───filtering
│           bpf_signal_to_remove_non_resp_freqs.m
│           elim_mains.m
│           elim_sub_cardiac.m
│           elim_vhfs.m
│           elim_vlfs.m
│
├───fuse_rr
│       fuse_rr.m
│       PMC.m
│       PRC.m
│       SFu.m
│       SPA.m
│       TFu.m
│
└───universal_scripts
        check_exists.m
        iden_resp_sig_file_ending.m
        save_or_append_data.m


algorithms
│   RRest.m
│       %   Outputs (to "db_name"\Analysis_files\Component_Data): 
│       %       for each subject, N, the following files are made:
│       %           N_int_respSigs      intermediate respiratory signals,
│       %           N_respSigs          final respiratory signals
│       %           N_rrEsts            RR estimates
│       %           N_rrRef             Reference RR values
│       %           N_sqi               Signal Quality Index values
│       %       for the entire dataset, the following files are made:
│       %           alg_names           Names of RR algorithms tested
│       %           win_data            Data for every algorithm tested, every
│       %           up                  universal parameters configuration
│       %           win_data_imp        Table of Impedance Results for each window window, and every subject.
│   RRest.prj
│   setup_universal_params.m
├───calculate_cc
│       calculate_resp_sig_cc.m
│           %CALCULATE_RESP_SIG_CC calculates correlation coefficients (CCs) between the
│           % extracted respiratory signals and reference respiratory signal
│           %	            calculate_resp_sig_cc(up)
│           %
│           %	Inputs:
│           %		data            data files should be stored in the specified format
│           %       up              universal parameters structure
│           %
│           %	Outputs:
│           %       	for each subject, n:
│           %       N_cc.m          - a file of CC values
│
├───calculate_sqi
│       calculate_sqi.m
│
├───calc_stats
│       calc_stats.m
│            %CALC_STATS calculates statistics based on the estimated and ref RRs
│            %	            calc_stats(up)
│            %
│            %	Inputs:
│            %		data             data files should be stored in the specified format
│            %       up              universal parameters structure
│            %
│            %	Outputs:
│            %       win_data        files containing a summary of each window analysed
│            %       BA_global           Limits of Agreement analysis files containing Bland-Altman analysis results 
│            %       BA_imp              Limits of Agreement analysis files containing Bland-Altman analysis results for impedance
│            %       study_stats     file containing other statistical analysis results
│            %       alg_names       file containing algorithm names
│            %
│
│
│       create_table_of_algorithms.m
│       create_table_of_algorithms_comb.m
│       find_rel_subjs.m
│       specific_vortal_plots.m
│       specific_vortal_stats.m
│
├───estimate_ref_rr
│       estimate_ref_rr.m
│
├───estimate_rr
│       ACF.m
│       ARM.m
│       ARP.m
│       ARPz.m
│       ARS.m
│       CtA.m
│       CtO.m
│       estimate_rr.m
│       find_spectral_peak.m
│       FTS.m
│       identify_subj_wins.m
│            %IDENTIFY_SUBJ_WINS Identifies windows in the respiratory signals on which
│            %to perform RR estimation. 
│            %
│            %   inputs -    subj        - the number of the subject (according to up.paramSet.subj_list)
│            %               up          .paramSet.winLeng - the duration of each window in secs
│            %               up          .paramSet.buffer_period - the number of secs to ignore at the start of each resp sig (since the filters might not have stabilised).
│            %               up          .paramSet.winStep - the number of secs between each consecutive window
│            %   outputs -   wins        .t_start .t_end - vector of start and end times of each win
│            %               N_wins      saved file of windows in the respiratory signals on which to perform RR estimation, expressed as start and end time 
│            %
│       PKS.m
│       PZX.m
│       WCH.m
│       ZeX.m
│
├───extract_resp_sig
│   │   extract_resp_sig.m
│   │   lp_filter_signal_to_remove_freqs_above_resp.m
│   │
│   ├───feat_based_extraction
│   │   │   downsample_data.m
│   │   │   EHF.m
│   │   │   ELF.m
│   │   │   FMe.m
│   │   │   FPt.m
│   │   │   LSSVMlabv1_8_R2009b_R2011a.zip
│   │   │   PDt.m
│   │   │   RDt.m
│   │   │   rpeakdetect.m
│   │   │   RS.m
│   │   │
│   │   ├───COr_peak_detector
│   │   │       co_ppg_peak_detector.m
│   │   │       parafilt.mat
│   │   │
│   │   ├───GC_qrs_detector
│   │   │       rpeakdetect.m
│   │   │
│   │   ├───IMS_peak_detector
│   │   │       adaptPulseSegment.m
│   │   │
│   │   └───LSSVMlabv1_8_R2009b_R2011a
│   │           AFEm.m
│   │           bay_errorbar.m
│   │           bay_initlssvm.m
│   │           bay_lssvm.m
│   │           bay_lssvmARD.m
│   │           bay_modoutClass.m
│   │           bay_optimize.m
│   │           bay_rr.m
│   │           bitreverse32.m
│   │           changelssvm.m
│   │           cilssvm.m
│   │           code.m
│   │           codedist_bay.m
│   │           codedist_hamming.m
│   │           codedist_loss.m
│   │           codelssvm.m
│   │           code_ECOC.m
│   │           code_MOC.m
│   │           code_OneVsAll.m
│   │           code_OneVsOne.m
│   │           crossvalidate.m
│   │           crossvalidatelssvm.m
│   │           csa.m
│   │           democlass.m
│   │           democonfint.m
│   │           demofun.m
│   │           demomodel.m
│   │           demomulticlass.m
│   │           demo_fixedclass.m
│   │           demo_fixedsize.m
│   │           demo_yinyang.m
│   │           denoise_kpca.m
│   │           eign.m
│   │           gcrossvalidate.m
│   │           gcrossvalidatelssvm.m
│   │           gridsearch.m
│   │           initlssvm.m
│   │           kentropy.m
│   │           kernel_matrix.m
│   │           kernel_matrix2.m
│   │           kpca.m
│   │           latentlssvm.m
│   │           latticeseq_b2.m
│   │           leaveoneout.m
│   │           leaveoneoutlssvm.m
│   │           linesearch.m
│   │           linf.m
│   │           lin_kernel.m
│   │           lssvm.m
│   │           lssvmMATLAB.m
│   │           mae.m
│   │           medae.m
│   │           misclass.m
│   │           MLP_kernel.m
│   │           mse.m
│   │           plotlssvm.m
│   │           poly_kernel.m
│   │           postlssvm.m
│   │           predict.m
│   │           predlssvm.m
│   │           preimage_rbf.m
│   │           prelssvm.m
│   │           progress.m
│   │           range.m
│   │           RBF_kernel.m
│   │           rcrossvalidate.m
│   │           rcrossvalidatelssvm.m
│   │           ridgeregress.m
│   │           robustlssvm.m
│   │           roc.m
│   │           rsimplex.m
│   │           simann.m
│   │           simlssvm.m
│   │           simplex.m
│   │           smootherlssvm.m
│   │           tbform.m
│   │           trainlssvm.m
│   │           trimmedmse.m
│   │           tunelssvm.m
│   │           weightingscheme.m
│   │           windowize.m
│   │           windowizeNARX.m
│   │
│   ├───filt
│   │       BFi.m
│   │       CCF.m
│   │       ekg_filt.m
│   │       ppg_filt.m
│   │       tukey_win_data.m
│   │       Wam.m
│   │       Wfm.m
│   │
│   └───filtering
│           bpf_signal_to_remove_non_resp_freqs.m
│           elim_mains.m
│           elim_sub_cardiac.m
│           elim_vhfs.m
│           elim_vlfs.m
│
├───fuse_rr
│       fuse_rr.m
│       PMC.m
│       PRC.m
│       SFu.m
│       SPA.m
│       TFu.m
│
└───universal_scripts
        check_exists.m
        iden_resp_sig_file_ending.m
        save_or_append_data.m