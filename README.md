# ASVspoof-audio-prediction-

The project works on the ASVspoof 2017 dataset with the aim of classifying a audio file as Genuine os Spoof.

Downloading Dataset: The dataset can be downloaded from the link specified in the dataset folder in data file. You will be able to make sense of the data after downloading the data and experiments conducted once data is downloaded.

In order to achieve the aim, we have used 2 approaches which are discussed below

# Method 1:
In this method, we have extracted the static, velocity, acceleration attributes of MFCC, RFCC, LFCC and IMFCC features using the bob library which is however, limited to LINUX AND MAC operating system. For windows users, you can use the python-speech-features library.
Apply Normalization to the data after extracting features.

After extracting the features, four different experiments were conducted.

Experiment 1: Input static,velocity, acceleration features or combinations of these attribiutes for each of MFCC, LFCC, RFCC ad IMFCC features to the Artificial Neural Network and their accuracy and EER was calculated.
		
Scenario	Features	                No. of coefficients
A	        Static only	                13
B	        Velocity (Δ) only	          13
C	        Acceleration (ΔΔ) only	    13
AB	      Static + Δ	                26
AC	      Static + ΔΔ	                26
BC	      Δ + ΔΔ                      26
ABC	      Static + Δ + ΔΔ	            39


The results with lowest Equal Error Rate(eer) were selected for each feature(MFCC,IMFCC,RFCC,LFCC) and used in the next experiment

Experiment 2: The best results obtained from previous experiment alone and their combinations were taken as input to the Artificial Nueral Network. 

Experiment 3: The dataset contains of files recorded in different environments and different recording devices. So seperate the extracted features based on environment and train and test the features on same environment as input to the Artificial Neural Network.

Experiment 4: Using the data seperated in Experiment 3, train and test on different environment and obtain the results.


# Method 2
In this case, create spectograms of audio files and input them to a Convolutional Nueral Network. You can either create your own CNN or use predefined models like ResNet to train.






