# SHM-for-bridge
For the task of structural health monitoring of a bridge, the vibration responses of the structure excited by passing vehicles, also named as events, are measured using tri-axial accelerometers.
Corresponding to each event, the measured time history of vibration responses is stored for further analysis.
For every event, raw acceleration data are transformed into a unique feature in time domain.

5 accelerometers are placed between two spans (two ceramic columns) of a long bridge. We are just doing analysis over a small portion of the bridge having 12 spans.
The vibration data is collected at a sampling rate of 200HZ (i.e. sampling interval=0.005s)

.................... In the first experiment the bridge is considered in a healthy state: ....................
        
i) The raw data is available in the file BR85_C_II. 

........................................ In the second experiment: ........................................

i) The same experiment as above, is conducted on the bridge after a year. The raw data is available in the file BR85_C_IV

# Steps for going about this:

## Data-Preprocessing (shm1.ipynb) <- Part-I of our analysis
It comprises of two broad parts:
                        * Outliers removal from the vibration data.
                        * Feature extraction (Frequency spectrum of the data).
i) DBSCAN algorithm of scikit-learn library is used for Outlier removal.
DBSCAN is a clustering algorithm that can be used as an outlier detection technique for unsupervised machine learning problems. I tried a couple of other algorithms like Local outlier Factor, Isolation forest, etc but among all, DBSCAN gave me a better performance on my data.
ii) After outlier removal, linear interpolation technique has been used to fill all the missing values in the data.
iii) Finally, FFT algorithm is used to extract frequency components to plot the frequency spectrum of the data.

## Clustering <- Part-II of our analysis (coming soon)
i) Patterns in the frequencies are found by forming clusters.
ii) It is in the file SHM2.ipynb

The python code for Part-I is available in the repository.

Cheers!
