# UNet Semantic Segmentation

This project implements a UNet architecture in PyTorch for semantic segmentation of images. The model is trained and evaluated on the [Carvana Image Masking dataset](https://www.kaggle.com/c/carvana-image-masking-challenge).

## Model Architecture


![network architecture](https://i.imgur.com/jeDVpqF.png)

The UNet architecture consists of a contracting encoder path and an expanding decoder path:

- Encoder uses convolutional blocks to extract features and downsample the image
- Decoder upsamples the features and uses skip connections from the encoder
- Softmax layer at the end classifies each pixel into a segmentation mask

Key components:

- Convolutional layers, max pooling, upsampling
- Skip connections to retain spatial information 
- Adam optimizer, cross entropy loss
- Batch normalization for faster convergence

## Training

- Trained on 5000 Carvana images over 50 epochs 
- Additional data augmentation techniques like random horizontal flips
- Mixed precision training with PyTorch AMP for faster throughput  

## Evaluation

- Achieved a Dice coefficient score of 0.98 on 100k+ Carvana test images
- Model can perform well for various types of semantic segmentation tasks

## Repository Contents

- Jupyter notebooks for data analysis and visualization
- PyTorch dataset, dataloader and UNet model definition
- Train, validation and predict scripts
- Helper modules for real-time monitoring, augmentation, utilities

## References

Ronneberger et al., U-Net: Convolutional Networks for Biomedical Image Segmentation (2015)
