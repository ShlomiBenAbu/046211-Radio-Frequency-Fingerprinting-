# 046211-Radio-Frequency-Fingerprinting
# Introduction
In the domain of wireless communications, the identification of devices based on their unique Radio Frequency (RF) fingerprints has emerged as a critical tool for enhancing network security, device authentication, and spectrum management. RF fingerprints arise due to hardware imperfections inherent in the manufacturing process of wireless devices. These imperfections introduce subtle, device-specific variations in transmitted signals, which can be leveraged for identification purposes.

However, detecting and classifying RF fingerprints becomes significantly challenging in low Signal-to-Noise Ratio (SNR) environments. Low SNR conditions often arise due to factors such as distance, interference, or environmental noise, which obscure the distinctive features of RF signals and complicate the identification process.

This task explores the application of transformer models to the identification of RF fingerprints in low SNR environments. By leveraging the ability of transformers to extract robust and meaningful features from complex data, this approach aims to improve the reliability and accuracy of RF fingerprinting in adverse scenarios. The work also highlights the potential of combining advanced signal processing techniques with deep learning frameworks to address practical challenges in wireless communications.

# Goals
<img src="https://github.com/alexivaner/Deep-Learning-Based-Radio-Signal-Classification/raw/main/Submission/Final/Kinds%20of%20Signal.png" width="500"><br>

* Classify 24 kinds of signal and get higher accuracy in lower SNR value.
* Design a new deep learning architecture and try to get the comparable results in terms of accuracy with state of the art or even better.
* Create End-to-end Deep Learning Model System (using only RAW signal).

**24 Kinds of signals** <br>
'32PSK', '16APSK', '32QAM', 'FM', 'GMSK', '32APSK', 'OQPSK', '8ASK', 'BPSK', '8PSK', 'AM-SSB-SC', '4ASK', '16PSK', '64APSK', '128QAM', '128APSK','AM-DSB-SC', 'AM-SSB-WC', '64QAM', 'QPSK', '256QAM', 'AM-DSB-WC', 'OOK', '16QAM'

# Model architecture
- Fully Connected
- Transformer Block
- Average Pooling 
- Batch Normalization
- Dropout Layer
- Fully Connected 
- Dropout Layer
- Fully Connected Layer
- Dropout Layer
- fully connected + Softmax
  
# Results


# Run the Model
1. Download the dataset **DEEPSIG DATASET: RADIOML 2018.01A (NEW)**, specifically the file **`GOLD_XYZ_OSC.0001_1024.hdf5`**, which can be found [here](https://www.kaggle.com/datasets/pinxau1000/radioml2018).
2. Run `data_preprocessing.py`, located in the `data_set_preprocessing` directory.
3. Run `RF_fingerprints.ipynb`.


# Prerequisites
|Library         | Version |
|--------------------|----|
|`Python`| `3.13.1`|
|`matplotlib`| `3.10.0`|
|`numpy`| `2.2.2`|
|`torch`| `2.1.0+cu121`|
|`scikit-learn`| `1.6.1`|
|`h5py`| `3.12.1`|
|`seaborn`| `0.13.2` |



