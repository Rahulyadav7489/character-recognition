# Character Recognition Project

## Overview
This project implements a handwritten character recognition system using convolutional neural networks (CNNs). It combines digits from the MNIST dataset with letters from the A-Z handwritten alphabet dataset to recognize 36 classes: A-Z and 0-9.

The repository contains:
- `Data Preprocessing.ipynb` — builds and prepares the dataset, creates grayscale 28x28 images, performs train/test split, and saves processed NumPy arrays.
- `CNN Architecture.ipynb` — defines a CNN model, trains it on the prepared dataset, evaluates performance, and saves the best model weights.
- `dataset.npz` — compressed dataset file with preprocessed train/test data and labels.
- `models/` — stored trained model weights.
- `numpy/` — saved NumPy arrays for train/test data and labels.
- `sample images/` — sample image outputs from the preprocessing step.

## Features
- Preprocesses handwritten letters and digits into a unified dataset
- Builds and trains a CNN for 36-class classification
- Saves model weights for the best training and validation results
- Includes data visualization of sample inputs and label distribution

## Dataset
The preprocessing notebook combines:
- MNIST digits dataset (`tensorflow.keras.datasets.mnist`)
- A-Z handwritten alphabet dataset from Kaggle

The combined dataset is normalized to `[0, 1]`, reshaped to `(28, 28, 1)`, and one-hot encoded into 36 classes.

## Requirements
- Python 3.8+ (recommended)
- TensorFlow
- OpenCV (`opencv-python`)
- NumPy
- pandas
- matplotlib
- seaborn
- scikit-learn

Optional for Colab usage:
- Kaggle API credentials if downloading the A-Z dataset directly

## Setup
1. Create a Python virtual environment:
   ```bash
   python -m venv venv
   .\venv\Scripts\activate
   ```
2. Install dependencies:
   ```bash
   pip install tensorflow opencv-python numpy pandas matplotlib seaborn scikit-learn
   ```
3. Open the notebooks in Jupyter or Colab.

## Usage
### Data preprocessing
Open and run `Data Preprocessing.ipynb` to:
- download and load the A-Z handwritten alphabet dataset
- merge digits and letters into one dataset
- normalize and reshape images
- split data into training and test sets
- save processed arrays in `dataset.npz` and `numpy/`

### Model training
Open and run `CNN Architecture.ipynb` to:
- define the CNN model architecture
- train the model on the processed data
- save the best weights in `models/`
- evaluate model accuracy and plot training history

## Notes
- The notebooks are currently configured for Google Colab paths. Update file paths if running locally.
- `dataset.npz` and model files are included for convenience, but you can recreate them by running the preprocessing and training notebooks.

## Folder structure
```
character recognition/
├── CNN Architecture.ipynb
├── Data Preprocessing.ipynb
├── dataset.npz
├── models/
│   ├── best_loss_model.h5
│   ├── best_loss_model.weights.h5
│   ├── best_val_loss_model.h5
│   └── best_val_loss_model.weights.h5
├── numpy/
│   ├── test_data.npy
│   ├── test_labels.npy
│   ├── train_data.npy
│   └── train_labels.npy
├── sample images/
└── README.md
```


