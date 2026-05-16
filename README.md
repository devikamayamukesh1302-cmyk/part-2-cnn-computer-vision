# Part 2 — Computer Vision Problem Formulation and CNN Prototype

## Project Overview

This project builds a Convolutional Neural Network (CNN) prototype for an image-based manufacturing defect classification problem.

The objective is to classify industrial product images into different defect categories using deep learning and computer vision techniques.

The project demonstrates:
- Image preprocessing
- CNN architecture design
- Model training and evaluation
- Feature learning using convolution and pooling
- Real-world industrial use case mapping

---

# Problem Identification

## Problem Type: Image Classification

This dataset represents an **Image Classification** problem.

Reason:
- Each image belongs to exactly one defect category.
- The model predicts the correct class label for an entire image.
- No bounding boxes or segmentation masks are required.

The dataset contains four manufacturing surface conditions:
- Normal
- Scratch
- Dent
- Stain

Since the task involves assigning one label to each image, image classification is the most appropriate computer vision problem type.

---

# Dataset Exploration

## Dataset Contents

The dataset contains industrial product images grouped into multiple defect categories.

### Classes Identified
- Normal
- Scratch
- Dent
- Stain

---

## Exploration Performed

The following analyses were completed:

- Number of classes
- Number of images per class
- Sample images visualization
- Image dimension inspection
- Dataset imbalance analysis

### Key Findings

- The dataset contains multiple defect categories.
- Some classes may contain fewer images than others, creating class imbalance.
- Image dimensions vary, requiring resizing before training.
- Visual inspection confirms distinct defect patterns across classes.

---

# Image Preprocessing

The following preprocessing steps were applied before CNN training:

## 1. Image Resizing
All images were resized to a fixed dimension:

128 × 128 pixels

This ensures consistent input shape for the CNN model.

---

## 2. Pixel Normalization

Pixel values were normalized from:

0–255 → 0–1

This improves neural network convergence and training stability.

---

## 3. Label Encoding

Class labels were converted into numerical format using LabelEncoder.

---

## 4. Train-Test Split

The dataset was divided into:
- Training Set: 80%
- Testing Set: 20%

A fixed random state was used for reproducibility.

---

## 5. Data Augmentation

Image augmentation was applied using:
- Rotation
- Horizontal flipping
- Zooming

This helps:
- Increase dataset diversity
- Improve model generalization
- Reduce overfitting

---

# CNN Model Architecture

A feed-forward Convolutional Neural Network (CNN) was built using TensorFlow/Keras.

## Model Layers

The CNN contains:

1. Convolution Layer
2. ReLU Activation
3. Max Pooling Layer
4. Additional Convolution + Pooling Layers
5. Flatten Layer
6. Dense Fully Connected Layer
7. Dropout Layer
8. Output Layer with Softmax Activation

---

## Model Configuration

### Optimizer
Adam

### Loss Function
Sparse Categorical Crossentropy

### Evaluation Metric
Accuracy

---

# Model Training and Evaluation

## Evaluation Metrics Used

The CNN model was evaluated using:

- Training Accuracy
- Validation Accuracy
- Training Loss
- Validation Loss
- Test Accuracy
- Confusion Matrix
- Classification Report

---

## Generated Outputs

### Accuracy & Loss Curves
Saved in:

results/accuracy_loss_curves.png

These plots show:
- Learning progression
- Convergence behavior
- Potential overfitting or underfitting

---

### Confusion Matrix
Saved in:

results/confusion_matrix.png

The confusion matrix shows:
- Correct predictions
- Misclassifications between classes

---

### Sample Predictions
Saved in:

sample_predictions/prediction_outputs.png

These visualizations display:
- Actual labels
- Predicted labels
- Model performance on unseen test images

---

# CNN Concepts Explained

## What is Convolution?

Convolution is the process of applying filters to images to detect important visual features such as:
- Edges
- Shapes
- Textures
- Patterns

CNNs automatically learn these features during training.

---

## Why is Pooling Used?

Pooling reduces image dimensions while preserving important information.

Benefits:
- Reduces computational cost
- Helps prevent overfitting
- Makes feature extraction more efficient

---

## Why is ReLU Commonly Used?

ReLU (Rectified Linear Unit) introduces non-linearity into the neural network.

Advantages:
- Faster training
- Better gradient flow
- Improved learning of complex patterns

---

## Why are CNNs Better Than Regular Feed-Forward Networks for Images?

CNNs are specifically designed for image data because they:
- Preserve spatial relationships
- Automatically learn visual features
- Require fewer parameters than fully connected networks

Regular feed-forward networks flatten images and lose important spatial information.

---

# Business Use Case Mapping

## Manufacturing Quality Inspection

This CNN-based defect classification system can be used in manufacturing industries for automated quality inspection.

### Example Applications
- Detect scratches on metal surfaces
- Identify dents in automotive parts
- Detect stains or production defects
- Separate defective products automatically

### Business Benefits
- Reduced manual inspection effort
- Faster production line monitoring
- Improved product quality
- Lower operational costs
- Higher inspection consistency

Such systems are widely used in:
- Smart factories
- Industrial automation
- AI-powered manufacturing systems

---

# Repository Structure

part-2-cnn-computer-vision/

├── README.md  
├── notebook.ipynb  
├── requirements.txt  
├── sample_predictions/  
│   └── prediction_outputs.png  
└── results/  
    ├── accuracy_loss_curves.png  
    └── confusion_matrix.png  

---

# Requirements

Install all dependencies using:

```bash
pip install -r requirements.txt