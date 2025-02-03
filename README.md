<h1 align="center"> 046211-Radio-Frequency-Fingerprinting</h1> 

## Table of Contents
1. [Introduction](#introduction)
2. [Goals](#goals)
3. [Model architecture](#model-architecture) <br>
4. [Wavelets](#wavelets)
5. [Dataset](#dataset)
6. [Experimental Setup](#experimental-setup) <br>
7. [Results](#results)
8. [Conclusions](#conclusions)
9. [Prerequisites](#prerequisites) 
10. [References](#references)


## Introduction

In the domain of wireless communications, the identification of devices based on their unique Radio Frequency (RF) fingerprints has emerged as a critical tool for enhancing network security, device authentication, and spectrum management. RF fingerprints arise due to hardware imperfections inherent in the manufacturing process of wireless devices. These imperfections introduce subtle, device-specific variations in transmitted signals, which can be leveraged for identification purposes.

However, detecting and classifying RF fingerprints becomes significantly challenging in low Signal-to-Noise Ratio (SNR) environments. Low SNR conditions often arise due to factors such as distance, interference, or environmental noise, which obscure the distinctive features of RF signals and complicate the identification process.

This task explores the application of transformer models to the identification of RF fingerprints in low SNR environments. By leveraging the ability of transformers to extract robust and meaningful features from complex data, this approach aims to improve the reliability and accuracy of RF fingerprinting in adverse scenarios. The work also highlights the potential of combining advanced signal processing techniques with deep learning frameworks to address practical challenges in wireless communications.

## Goals

<img src="https://github.com/alexivaner/Deep-Learning-Based-Radio-Signal-Classification/raw/main/Submission/Final/Kinds%20of%20Signal.png" width="500"><br>

* Achieve well performance for low SNR. 
* Get comparable results in terms of accuracy with state of the art or even better.
* End-to-end Deep Learning Model System.

**24 Kinds of signals** <br>
'32PSK', '16APSK', '32QAM', 'FM', 'GMSK', '32APSK', 'OQPSK', '8ASK', 'BPSK', '8PSK', 'AM-SSB-SC', '4ASK', '16PSK', '64APSK', '128QAM', '128APSK','AM-DSB-SC', 'AM-SSB-WC', '64QAM', 'QPSK', '256QAM', 'AM-DSB-WC', 'OOK', '16QAM'

## Model architecture

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

![image](https://github.com/user-attachments/assets/05292164-a4de-4492-8d77-b21b39fdecbb)

## Wavelets
Wavelets are mathematical functions used to analyze and process signals at different scales and resolutions. They are particularly useful for decomposing a signal into different frequency components while preserving spatial (or temporal) information.

Unlike Fourier transforms, which break signals into sine and cosine components (which have infinite support), wavelet transforms use localized basis functions that adapt to the signal’s structure. This makes wavelets particularly effective in analyzing non-stationary signals, such as images, audio, or time-series data.

There are some advantages using wavelets

1. Feature Extraction
   - Wavelets help in extracting multi-scale features, capturing both fine details and coarse structures in images, audio,        time-series data.
2. Noise Reduction
   - applying a wavelet transform, high-frequency noise can be separated from useful features.
3. Improved Generalization
   - Models trained on wavelet-transformed data often generalize better as wavelets help in reducing overfitting by focusing      on essential features.
![image](https://github.com/user-attachments/assets/3f4b51ff-6042-42ba-a361-cf73e4bcfc9e)

## Dataset

The experiments were conducted using the RADIOML 2018.01A dataset [1], which contains 24 different RF signal modulations. 
The dataset exhibits the following structure:
*	24 modulations: OOK, ASK4, ASK8, BPSK, QPSK, PSK8, PSK16, PSK32, APSK16, APSK32, APSK64, APSK128, QAM16, QAM32, QAM64, QAM128, QAM256, AM_SSB_WC, AM_SSB_SC, AM_DSB_WC, AM_DSB_SC, FM, GMSK and OQPS.
*	26 SNRs per modulation (-20 dB to +30 dB in steps of 2dB).
*	4096 frames per modulation-SNR combination.
*	1024 complex time-series samples per frame.
*	Samples as floating point in-phase and quadrature (I/Q) components, resulting in a (1024,2) frame shape.

2,555,904 frames in total.

## Experimental Setup

The model wasn't trained on the entire dataset due to hardware limitations. The dataset the model was trained on:
- Training Dataset Size: 112,000 frames
- Validation Dataset Size: 28,000 frames
- Batch Size: 4096
- Learning Rate: 1e-4 (decay during running) 
 
## Results
![image](https://github.com/user-attachments/assets/d05086c8-373c-4fe8-baa3-b414d1dabbe0)

### Modulation accuracy
![image](https://github.com/user-attachments/assets/31adf0e4-1cbb-42b4-9621-4c6e4be41709)

### SNR accuracy
![image](https://github.com/user-attachments/assets/164ebeb2-30c3-45fa-8d5d-ce2136408e60)


## Conclusions
- Transformer-based RF fingerprinting 	enhances 	accuracy in low SNR.
- Wavelet's transform can improve the accuracy in low SNR.
- Transform can get better accuracy for both low and high SNR.

## Run the Model

1. Download the dataset **DEEPSIG DATASET: RADIOML 2018.01A (NEW)**, specifically the file **`GOLD_XYZ_OSC.0001_1024.hdf5`**, which can be found [here](https://www.kaggle.com/datasets/pinxau1000/radioml2018).
2. Run `data_preprocessing.py`, located in the `data_set_preprocessing` directory.
3. Run `RF_fingerprints.ipynb`.


## Prerequisites

|Library         | Version |
|--------------------|----|
|`Python`| `3.13.1`|
|`matplotlib`| `3.10.0`|
|`numpy`| `2.2.2`|
|`torch`| `2.1.0+cu121`|
|`scikit-learn`| `1.6.1`|
|`h5py`| `3.12.1`|
|`seaborn`| `0.13.2` |
|`pywt`| `2.2.2` |

## References

* Farhan Tandia, Ivan Surya Hutomo: https://github.com/alexivaner/Deep-Learning-Based-Radio-Signal-Classification

* Lu, Q., Yang, Z., Zhang, H., Chen, F., Xian, H.: Mrfe: a deep learning based multidimensional radio frequency fingerprinting enhancement approach for iot device identification. IEEE Internet Things J. (2024). https://doi.org/10.1109/JIOT.2024.3414195 <br>


