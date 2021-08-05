# PrivacyHistos

Welcome to the PrivacyHistos repository.  This repo contains five differential privacy functions for combining features into privatized histograms.  The five functions are contained in the **privacy.py** file located in the **src directory**.  In order to use the functions the following input is required:

### Input

1) Formatted Ground Truth Data (ground_truth)
    * All data must be encoded as positive integers with no Nans
    * The column names must be appended as follows:
        - _c – indicates a categorical feature
        - _n – indicates a numeric feature
        - _i – One, and only one, column must be the individual identifier
        - _x – indicates a feature to include but not used as a combination feature
2) Sensitivity and Epsilon (sensitivity, epsilon)
    * Sensitivity = (number of histograms * sample size) + population queries
        - Number of histograms – the total number of histograms which may include other histograms not using the combined column approach.
        - Sample size – the number of individual records to use for building the histograms (if smapling is used).
        - Population queries – the total number of population queries used in the overall approach.
    * Epsilon - The epslion value to use
3) Combination Dictionary (combo_dict)
4) Number Dictionary (num_dict)

### Functions

1) check_input(ground_truth, combo_dict, num_dict)
2) pre_process(ground_truth, combo_dict, num_dict)
3) histo_test(df, combo_dict)
4) create_private_histo(df, column, sample, sample_size, sensitivity, epsilon)
5) col_decoder(num_dict, num_decode, col_decode, value, column)



