
# Homomorphic Encryption with Federated Learning for NextGen wireless Network

## Overview
This repository implements a secure federated learning (FL) system for channel estimation in 5G/6G wireless networks using homomorphic encryption. The system enables collaborative model training across multiple clients while preserving data privacy through encryption.

## Key Features
- Federated learning implementation for distributed model training
- Homomorphic encryption for secure weight aggregation 
- CNN-based deep learning model for channel estimation
- Support for multiple clients with configurable federation settings
- Performance evaluation metrics and visualizations

## Prerequisites

### Required Packages
```bash
pip install pyfhel==3.1.0
pip install plot_keras_history
pip install keras-tuner
pip install tensorflow
pip install numpy
pip install matplotlib
pip install scipy
pip install pandas
pip install seaborn
```

### Dataset
The implementation uses the 6G Channel Estimation Dataset. Download using:
```bash
wget -q -O data.mat https://github.com/ocatak/6g-channel-estimation-dataset/blob/main/data.mat?raw=true
```

## Project Structure

```
├── Channel_Estimation_FL_2.ipynb   # Main implementation notebook
├── data.mat                        # Channel estimation dataset
├── README.md                       # Project documentation
└── requirements.txt                # Package dependencies
```

## Implementation Details

### Model Architecture
- Uses a CNN-based model with 3 convolutional layers
- Input shape: (612, 14, 1)
- Activation functions: SELU, Softplus
- Optimization: Adam optimizer
- Loss function: Mean Squared Error (MSE)

### Federated Learning Process
1. Model initialization
2. Client selection and data distribution
3. Local model training on clients
4. Model encryption using homomorphic encryption
5. Secure aggregation of encrypted models
6. Model decryption and global update
7. Performance evaluation

### Security Features
- Homomorphic encryption using Pyfhel library
- Secure key generation and management
- Encrypted model weight transfer
- Private aggregation protocol

## Usage

### Google Colab Setup
```python
from google.colab import drive
drive.mount("/content/gdrive")
PROJECT_FOLDER = '/content/gdrive/My Drive/ds/'
```

### Configuration
Adjust key parameters in the notebook:
```python
SECRET_LEVEL = 192        # Encryption security level
LEVEL_N = 1024           # Encryption parameter
num_of_client_list = [3,4,5,6,7,8,9]  # Number of clients
NUM_OF_EXPERIMENTS = 10   # Number of federation rounds
```

### Running the System
1. Initialize the federated learning system
2. Generate encryption keys
3. Distribute data to clients
4. Execute federated training
5. Evaluate performance

## Results
The system provides:
- Training history and loss metrics
- Model performance visualizations
- Channel estimation accuracy analysis
- Computation time measurements

## Performance Metrics
- Model MSE (Mean Squared Error)
- Training time per client
- Encryption/decryption overhead
- Communication costs



## Acknowledgments
- Original dataset from 6G Channel Estimation research
- PyFHEL library for homomorphic encryption
- TensorFlow and Keras for deep learning implementation

