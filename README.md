# On-Device AI using Qualcomm

## AI Used: Qualcomm AI Hub

## OVERVIEW
This project by DeepLearning.AI explores the use of Qualcomm AI Hub for on-device AI applications. The key areas of focus include:

1. Understanding On-Device AI
2. Applications of On-Device AI
3. Deploying Segmentation Models On-Device
4. Preparing for On-Device Deployment
5. Quantizing Models

## OBJECTIVE
The primary objective of this project is to study and implement On-Device AI, specifically:

1. On-device AI applications in various domains
2. Deployment of segmentation models on devices
3. Preparation steps for on-device deployment
4. Model quantization techniques

## ON-DEVICE AI
On-device AI integrates artificial intelligence capabilities directly into devices, enabling real-time processing and decision-making. It has widespread applications including:
1. Drones, Robots, Mobile Phones, IoTs
2. Image and Video: Photo Classification, QR Code Detection
3. Audio and Speech: Text to Speech, Noise Removal, Speech Recognition

<img width="511" alt="image" src="https://github.com/Lekhansh-cmd/Qualcomm-On-Device-AI/assets/78807364/b8c6b81c-7210-4fdc-8d8c-a8e4ae91d68b">

## ADVANTAGES OF ON-DEVICE AI
1. Cost Effective: Reduces data transfer and cloud processing costs.
2. Efficient: Provides faster processing speeds.
3. Privacy: Keeps data on the device, enhancing privacy.
4. Personalization: Allows for continuous model personalization on the device.

## Step 1: DEPLOYING SEGMENTATION MODELS ON-DEVICE
For our project, we are using FFNet 40s, which is a segmentation model with high performance and is extremely configurable. It has a simple encoder-decoder architecture with
ResNet-like backbone and small multi-scale head.

<img width="393" alt="image" src="https://github.com/Lekhansh-cmd/Qualcomm-On-Device-AI/assets/78807364/d949127d-db8d-4211-bcad-fc87a8c25f30">

## Step 2: PREPARING FOR ON-DEVICE DEPLOYMENT
To prepare a model for on-device deployment, follow these steps:

1. Neural Network Graph Capture: Capture the trained model.
2. Compile Model for Target: Compile the model for the specific target device.
3. Validate On-Target Numerics: Ensure that both cloud and device produce identical results.
4. Performance Profiling On-Device: Ensure the model meets the device constraints.

## Target Runtime
Three main types of runtime are available for use:

1. Qualcomm AI: Recommended for fully embedded applications.
2. TensorFlow Lite: Recommended for Android applications.
3. ONNX Runtime: Recommended for Windows applications.

## Compute Units
1. CPU: Most flexible general-purpose computation engine
2. GPU: High-Performance complex parallel computation
3. NPU: Extremely efficient for Neural Networks

## Step 3: QUANTIZING MODELS
Quantization reduces the precision of models to improve performance and efficiency.. This is done with the help of Scale and Zero Point. Quantization of models is done for several benefits:

1. Improved Performance by 4x
2. Reducing Model Size by 4x
3. Energy Efficient as lower precision uses less power
But when converting float to int, there is a value loss called "Quantization Error" during the quantization process. The goal is to have minimal quantization error.

So to fix this, there are several methods:

1. Post-Training Quantization: This is applied after training the model. This process uses a calibration dataset.
2. Quantization Aware Training: This is applied to the training process, so a training dataset is used.

For our model, we are using Post Traninng Quantization. Hence we have to follow these steps:

1. Prepare the calibration dataset
2. Prepare a model for quantization
3. Perform Post-Training Quantization
4. Validate Off-Target Frequency
