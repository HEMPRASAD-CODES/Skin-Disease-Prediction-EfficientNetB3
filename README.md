# Skin-Disease-Prediction-EfficientNetB3
# Skin Disease Detection Using Deep Learning

## Project Overview

This project implements a complete deep learning pipeline for automated skin disease classification using the HAM10000 dataset. The goal is to accurately identify seven types of skin lesions from dermoscopic images, supporting clinical diagnosis and research in dermatology[1].

## Dataset

- **HAM10000**: Over 10,000 dermoscopic images, each labeled as one of seven skin disease categories:
  - Melanocytic nevi (nv)
  - Melanoma (mel)
  - Benign keratosis-like lesions (bkl)
  - Basal cell carcinoma (bcc)
  - Actinic keratoses (akiec)
  - Vascular lesions (vasc)
  - Dermatofibroma (df)
- Each image is accompanied by metadata such as patient age, sex, and lesion location[1].

## Pipeline Steps

**1. Data Loading & Exploration**
- Loads metadata and images from the HAM10000 dataset.
- Explores class distribution and visualizes sample images for each class[1].

**2. Data Preprocessing**
- Images are resized to 224x224 pixels and normalized.
- Labels are encoded for model training[1].

**3. Data Augmentation**
- Applies random rotations, flips, zooms, and brightness adjustments to increase data diversity and reduce overfitting during training[1].

**4. Train-Validation-Test Split**
- Splits the dataset into training, validation, and test sets with stratification to preserve class balance.
- Computes class weights to address class imbalance[1].

**5. Model Architecture**
- Uses EfficientNetB3 as the base model with transfer learning, adding a custom classification head.
- Initially trains with the base model frozen, then fine-tunes the entire network[1].

**6. Training**
- Two-phase training:
  - Phase 1: Trains only the custom head.
  - Phase 2: Fine-tunes the full model with a lower learning rate[1].
- Utilizes callbacks for early stopping, learning rate reduction, and model checkpointing.

**7. Evaluation**
- Evaluates model performance on the test set using accuracy, confusion matrix, and classification report.
- Visualizes results and reports final test accuracy[1].

**8. Deployment**
- Saves the trained model, label encoder, and configuration for future inference.
- Provides a prediction function to classify new skin lesion images[1].

## Results

- The pipeline achieves strong classification accuracy on the HAM10000 test set.
- The model can be used to predict the type of skin disease from new dermoscopic images, aiding dermatological analysis[1].

**Keywords:** Skin disease detection, deep learning, EfficientNet, HAM10000, medical image analysis, transfer learning, classification.
