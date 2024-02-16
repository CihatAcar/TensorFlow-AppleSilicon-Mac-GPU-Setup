# TensorFlow-AppleSilicon-Mac-GPU-Setup
Unlock the power of TensorFlow with GPU on Apple Silicon. This guide provides easy steps for setting up TensorFlow and the Metal plugin on M series chips, enabling accelerated ML model training. Perfect for developers seeking efficient TensorFlow operations on Mac. Dive in for a smooth, high-performance ML setup!


# Running TensorFlow with GPU Support on Mac Devices without Miniforge



This guide explains how to set up and run TensorFlow with GPU support on Mac devices with Apple's M series chips (M1, M1 Pro, M1 Max, M2, etc.), using Conda from Anaconda and virtualenv, and leveraging the Metal API for GPU acceleration.



## Prerequisites



- macOS 11.0 (Big Sur) or later

- Python 3.9 or newer

- An Apple Mac device with an M series chip

- Anaconda or Miniconda installed (Alternatively virtual environment can be used.)



## Step 1: Install Anaconda or Miniconda



If not already installed, download and install Anaconda or Miniconda from their [official website](https://www.anaconda.com/products/individual) for the ARM64 architecture.



## Step 2: Create a Conda Environment



Create a new conda environment to isolate your TensorFlow setup:



```bash

conda create --name tf_gpu python=3.9

conda activate tf_gpu
```

# Step 3: Install TensorFlow and TensorFlow Metal Plugin

Within your conda environment, install TensorFlow for macOS and the Metal plugin for GPU acceleration:

```bash

pip install tensorflow-macos

pip install tensorflow-metal
```

# Alternative: Using Virtualenv

If you prefer not using Conda, you can use virtualenv:

```bash

# Install virtualenv if you haven't already

pip install virtualenv



# Create a virtual environment

virtualenv tf_gpu_env



# Activate the virtual environment

source tf_gpu_env/bin/activate



# Install TensorFlow and Metal plugin

pip install tensorflow-macos

pip install tensorflow-metal
```

# Step 4: Verify Installation

Check if TensorFlow can access the GPU:


```python
import tensorflow as tf

print("Num GPUs Available: ", len(tf.config.list_physical_devices('GPU')))
```

This command should return the number of GPUs available.

# Troubleshooting

If TensorFlow doesn't recognize the GPU, double-check the installation steps. Revisit the TensorFlow Metal plugin installation and ensure your environment is activated. Consult TensorFlow's official documentation and Apple's developer resources for more information.

# Conclusion

You are now ready to use TensorFlow with GPU acceleration on your Mac device. Enjoy the enhanced performance for your machine learning models. I have also included example notebook that demonstrates how to install packages and use it.