# Speech Emotion Recognition

**Date**: May 9, 2025  

## Summary

This project compares time-domain and frequency-domain approaches for speech emotion recognition using CNN models on the CREMA-D dataset.

### Dataset
- **CREMA-D**: 6 emotion classes (Angry, Disgust, Fear, Happy, Neutral, Sad)  
- **Preprocessing**: All audio clipped or padded to 3 seconds; 70/30 train-test split  

### Frequency-Domain (Mel-Spectrogram)
- Extracted 128-band log-Mel spectrograms (130 frames)  
- Data augmentation: pitch shift, time stretch, Gaussian noise (training only)  
- **Model**: 2D CNN with 3 Conv blocks (64→128→256), dense layers, softmax output  
- **Accuracy**: ~58%

### Time-Domain (ZCR + Energy)
- Extracted Zero Crossing Rate and signal energy features  
- **Model**: 1D CNN with 3 Conv1D blocks (64→128→256), dense layers, softmax  
- **Accuracy**: ~47%

### Frequency-Domain (MFCCs)
- Extracted 40 MFCCs over 109 time steps  
- **Model**: 2 Conv1D layers (64 and 128 filters) with MaxPooling, followed by Global Average Pooling, dense layers, and softmax  
- **Accuracy**: ~52%

## Goal
Evaluate and compare CNN-based emotion classification performance using time vs frequency-domain audio features.
