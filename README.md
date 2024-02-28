#  3D human pose estimation from 2D joint poses using Generative Adversarial Networks (GAN)
The provided Python script is an implementation of 3D human pose estimation from 2D joint poses using Generative Adversarial Networks (GANs). The approach is inspired by the research paper titled "Unsupervised adversarial learning of 3d human pose from 2d joint locations" (https://arxiv.org/pdf/1803.08244.pdf). The script is structured to perform training and testing of the GAN-based 3D pose estimation model.



## Major Components:

### Data Loading and Preprocessing:

The script loads a 2D pose dataset from a specified path, normalizes the data, and splits it into training and validation sets.
The dataset is then prepared for training using PyTorch's DataLoader.
Model Architecture:

Two neural network models are defined: MLP_Generator and MLP_Discriminator. These models constitute the generator and discriminator components of the GAN.
The generator takes 2D joint poses as input and outputs 3D joint poses.
The discriminator is designed to distinguish between real and generated 2D poses.

### Training:

The script provides functionality for training the GAN models.
Adversarial training involves optimizing the discriminator to correctly classify real and generated 2D poses, while simultaneously optimizing the generator to produce 3D poses that fool the discriminator.
The training loop involves alternating optimization steps for the discriminator and generator, with additional steps in the generator to ensure the 3D poses are realistic.

### Loss Functions:

Binary Cross-Entropy Loss (BCE Loss) is used for training the discriminator.
A custom loss function L_angle is defined to avoid inverted 3D poses.

### Rotation and Projection:

The rotate_project function simulates the projection of 3D poses onto 2D space after a random theta rotation.

### Visualization:

Functions for visualizing 2D and 3D poses are provided, utilizing Matplotlib and Plotly.

### Testing:

The script includes a testing section where the trained model is applied to a test dataset.
Visualization of the 2D and 3D poses for a sample image from the test dataset is demonstrated.


### Usage:

The script provides a modular structure for training and testing 3D pose estimation models using GANs.
Users can customize hyperparameters, dataset paths, and model paths.
Detailed visualizations are available for assessing the quality of 3D pose estimations.

### Note:

The script is designed to run in a Google Colab environment as indicated by the presence of Colab-specific commands (from google.colab import drive).
This script serves as a comprehensive implementation for GAN-based 3D pose estimation, with options for training and testing on a given dataset. The code is well-documented, making it suitable for use in research or educational projects related to human pose estimation.
