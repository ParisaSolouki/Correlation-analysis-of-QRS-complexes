# Calculating the correlation between one QRS complex and other QRS complexes(N,S,F,V,U)
This code processes ECG signals from the MIT-BIH Arrhythmia Database, focusing on beat segmentation and correlation analysis of QRS complexes. After reading the ECG data files and applying necessary filtering, it segments the beats based on annotations and calculates the correlation between selected QRS complexes and a template derived from normal heartbeats (N type).


## Code Breakdown
### 1. Imports: The necessary libraries are imported at the beginning of the code.

### 2. Constants and Parameters:
- Sampling frequency (fs): Set to 360 Hz.
- Filter cutoff frequencies (fl, fh): Low and high cutoffs for bandpass filtering.
- Filter coefficients: Butterworth filter coefficients are computed for both high-pass and low-pass filtering.

### 3. File Loading:
The code uses glob to load .dat files from the specified directory and initializes lists to store the segmented data.

### 4. Data Processing:
#### For each ECG file:
- The signal is read, and filtering is applied.
- Annotations are read to identify R-peak positions and beat types.
- Beats are segmented based on the annotations and categorized into different types (N, S, F, V, U).

### 5. Correlation Analysis of QRS Complexes:
- Template Creation: The template for normal heartbeats is created by averaging the QRS complexes identified as type 'N'.
- QRS Selection: Specific QRS complexes (e.g., qrs0 and qrs1) are selected for correlation analysis.
- Calculating Correlation: The code calculates the Pearson correlation coefficient between the selected QRS complex and the template. The correlation provides insight into how similar the selected QRS complexes are to the template.


## Conclusion
This code offers a comprehensive approach to ECG signal analysis, focusing on beat segmentation and correlation analysis. The correlation between QRS complexes allows for evaluating the consistency of heartbeats, which can be particularly useful for arrhythmia detection or quality assessment of ECG signals.
