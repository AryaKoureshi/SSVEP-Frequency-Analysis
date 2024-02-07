# SSVEP Frequency Analysis Repository

This repository contains code for analyzing Steady-State Visually Evoked Potential (SSVEP) signals recorded from EEG data. The goal of this analysis is to determine the stimulation frequency from the EEG signals recorded in each test. Two methods are employed: Frequency Content Plotting and Canonical Correlation Analysis (CCA).

## Data Description

The `SSVEP.mat` file contains the following data:

- `SSVEP_Signal`: A matrix (6x117917) containing EEG signals recorded from 6 channels (O2, P8, P7, Oz, Pz, and O1) with a sampling frequency of 250 Hz.
- `Events`: A matrix (1x15) containing stimulation frequencies.
- `Event_samples`: A matrix (1x15) containing time samples corresponding to the start of each stimulation.

## Analysis Methods

### Frequency Content Plotting (Part A)

1. **Bandpass Filtering**: Remove frequencies below 1 Hz and above 40 Hz.
2. **Trial Segmentation**: Separate trials corresponding to 15 stimuli with a window size of 5 seconds.
3. **Frequency Content Calculation**: Calculate the frequency content of each channel using the Welch method.
4. **Channel Comparison**: Analyze differences in frequency content across channels.
5. **Dominant Frequency Identification**: Determine the dominant frequency for each trial.

### Canonical Correlation Analysis (CCA) (Part B)

1. **Trial Segmentation**: Similar to Frequency Content Plotting.
2. **CCA Method**: Apply CCA to determine dominant frequencies. Compare coefficients obtained from different stimulation frequencies.
3. **Channel Subset Analysis**: Evaluate the impact of reducing the number of channels on classification accuracy.
4. **Window Length Analysis**: Assess the effect of varying the length of the time window on classification accuracy.

## Results and Interpretation

- Frequency Content Plotting reveals variations in frequency content across channels, potentially indicating differences in brain regions and functions.
- CCA accurately identifies dominant frequencies, with high classification accuracy.
- Channel subset and window length analyses demonstrate the importance of selecting an appropriate subset of channels and time window length for accurate classification.

## Usage

To use this code, ensure you have the `SSVEP.mat` file containing the EEG data. Adjust parameters such as frequency range, window size, and overlap as needed. Run the provided scripts for Frequency Content Plotting and CCA analysis.

Feel free to contribute to this repository by improving the analysis methods or adding additional features.
