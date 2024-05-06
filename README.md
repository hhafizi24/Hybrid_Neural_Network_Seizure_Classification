Hybrid CNN-RNN Neural Network Model for Epileptic Seizure Classification

Overview:
This repository contains code for classifying different types of epileptic seizures from human EEG (Electroencephalography) data. The project aims to develop a neural network model that can accurately classify EEG signals into one of four categories: Complex Partial Seizures, Electrographic Seizures, Video-detected Seizures with no visual change over EEG, and Normal Data.

Dataset:
This project uses an open dataset collected and uploaded by Dr. Wassim Nasreddine of the American University of Beirut Medical Center. His data followed the 10-20 electrode system and was sampled at 500 Hz. Additionally, he applied a bandpass filter between 1/1.6 Hz and 70 Hz while filtering out the 50 Hz line noise. The EEG data was collected from patients with epilepsy, each EEG recording is a multi-dimensional time series with 19 electrodes and 500 time points per sample. The total data size was (7790,19,500), which includes both seizure and normal data. The data was split into train (90%) and test (10%) sets, I further allocated 10% of the train data to the validation set.

The shapes of the datasets are as follows:

Train Data:

•	x_train shape: (6310, 19, 500)

•	y_train shape: (6310, 1)

Validation Data:

•	x_val shape: (701, 19, 500)

•	y_val shape: (701, 1)

Test Data:

•	x_test shape: (779, 19, 500)

•	y_test shape: (779, 1)

Model Architecture:

The neural network model architecture consists of a combination of Convolutional Neural Network (CNN) and Recurrent Neural Network (RNN) layers. The CNN layers are used to extract spatial features from the EEG data, while the RNN layers capture temporal dependencies.
The model architecture is as follows:

•	Input Layer: EEG data with dimensions (electrodes, time points, channels)

•	Conv2D layers with Batch Normalization, Average Pooling, and Dropout 

•	Reshape layer to prepare for LSTM layer

•	LSTM layer for capturing temporal dependencies

•	Dense layer for classification

The model is compiled with the Adamax optimizer and Sparse Categorical Crossentropy loss function.

Model Training:

The model is trained with the following configurations:

•	Number of Epochs: 20

•	Batch Size: Default

•	Validation Set: 10% of the train data

The training progress is monitored using accuracy as the evaluation metric.

Results:

The model achieved the following performance metrics:

Train Data Results:

•	Accuracy: 97.94%

•	Precision: 98.61%

•	Recall: 98.60%

•	F1 Score: 98.60%

Test Data Results:

•	Accuracy: 92.43%

•	Precision: 94.06%

•	Recall: 93.08%

•	F1 Score: 93.55%

The dataset can be downloaded from the following link:

https://data.mendeley.com/datasets/5pc2j46cbc/1

References:

Nasreddine, Wassim (2021), “Epileptic EEG Dataset”, Mendeley Data, V1, doi: 10.17632/5pc2j46cbc.1
