# 046211-Radio-Frequency-Fingerprinting-
# Introduction
In the domain of wireless communications, the identification of devices based on their unique Radio Frequency (RF) fingerprints has emerged as a critical tool for enhancing network security, device authentication, and spectrum management. RF fingerprints arise due to hardware imperfections inherent in the manufacturing process of wireless devices. These imperfections introduce subtle, device-specific variations in transmitted signals, which can be leveraged for identification purposes.

However, detecting and classifying RF fingerprints becomes significantly challenging in low Signal-to-Noise Ratio (SNR) environments. Low SNR conditions often arise due to factors such as distance, interference, or environmental noise, which obscure the distinctive features of RF signals and complicate the identification process.

This task explores the application of transformer models to the identification of RF fingerprints in low SNR environments. By leveraging the ability of transformers to extract robust and meaningful features from complex data, this approach aims to improve the reliability and accuracy of RF fingerprinting in adverse scenarios. The work also highlights the potential of combining advanced signal processing techniques with deep learning frameworks to address practical challenges in wireless communications.

# Model architecture
## 1. Input Layer
- A fully connected (linear) layer expands the feature space.
- Transformation: 1024 → 2048

## 2. Transformer Block
-  Multi-Head Self-Attention (MHA)
- Feed-Forward Network (FFN)
- Layer Normalization & Residual Connections
  
## 3.  Average Pooling
- A downsampling layer that reduces dimensionality while preserving the most useful information.
 
## 4. Batch Normalization
- Normalizes feature distributions across different samples in a batch.

## 5. Dropout Layer
- Dropout Probability: 30%
- Randomly deactivates neurons during training.
- 
## 6. Fully Connected 
- Transformation: 1024 → 128
- A dense (fully connected) layer that compresses features from 1024 dimensions to 128

## 7. Dropout Layer
- Dropout Probability: 20%
- Randomly deactivates neurons during training.

## 8. Fully Connected Layer
- Transformation: 128 → 128
- Another dense layer that maintains the 128-dimensional feature space.

## 9. Dropout Layer
- Dropout Probability: 20%
- Randomly deactivates neurons during training.

## 10. Output Layer
- Transformation: 128 → Num_Classes
- A fully connected (linear) layer that maps learned representations to the number of classes.
- Activation Function:
- Softmax (for multi-class classification)

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



