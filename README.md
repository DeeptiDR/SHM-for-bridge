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
Firstly, I remove outliers from the vibration data.
ii) I'm using Local outlier Factor algorithm using scikit-learn library. LOF is an outlier detection technique for unsupervised machine learning problems. I tried a couple of other algorithms like Isolation forest but among all, LOF gave me a better performance on my data.
iii) After outlier removal, I linearly interpolate my data to fill missing values.
iii) Then, I plot the frequency spectrum of the data.

## Clustering <- Part-II of our analysis (coming soon)
iv) Finally, I find patterns in the frequencies by forming clusters.
The python code is available in the repository.

Cheers!
