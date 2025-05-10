# Project Summary

## Goal
Build an efficient CIFAR-10 classifier by leveraging a pre-trained ResNet50V2 backbone.

## Data Preparation
- Resize CIFAR-10 images from 32×32 to 224×224 and normalize pixel values to [0,1].  
- Split 10 % of the training set for validation; keep the test set separate.

## Model Architecture
- **Backbone:**  
  ResNet50V2 pre-trained on ImageNet, with top layers removed and initially frozen.  
- **Classification Head:**  
  - Dense layer (256 units, ReLU)  
  - Dropout (rate=0.3)  
  - Softmax output layer (10 classes)

## Training Process
1. **Head-Only Training**  
   Train only the new head layers for 10 epochs while keeping the backbone frozen.
2. **Fine-Tuning**  
   Unfreeze the last 20 layers of the backbone and continue training for 10 more epochs with a reduced learning rate.


