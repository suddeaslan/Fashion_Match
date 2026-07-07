
# FashionMatch: Multi-Task Deep Learning Fashion Recommendation System

## Overview

FashionMatch is a deep learning-based recommendation system developed using the H&M Personalized Fashion Recommendations dataset. The project combines computer vision, multi-task learning, and recommendation techniques to help users discover visually similar fashion products.

The system simultaneously predicts:

* Product Category
* Color Group

and generates personalized recommendations based on visual similarity between clothing items.

---

## Project Objectives

Online fashion platforms contain thousands of products, making it difficult for customers to quickly find items matching their preferences.

This project aims to:

* Classify clothing products from images
* Predict product categories and colors simultaneously
* Learn meaningful visual representations using deep learning
* Recommend visually similar products through content-based filtering

---

## Dataset

Source:

* H&M Personalized Fashion Recommendations Dataset (Kaggle)
* * **Data Storage (Google Drive):** [GOOGLE_DRIVE_LINK_HERE](https://drive.google.com/drive/folders/1gt0zCNxzuxTolYEmGhLogrzrXRAilh96?usp=drive_link)]



Dataset characteristics:

* 105,000+ product images
* 25 metadata features per product
* Originally over 28 GB of image data

To improve computational efficiency:

* Missing images were removed
* Rare classes were filtered out
* Categories and colors were grouped into broader classes
* Global Random Sampling was applied
* Final training dataset contained 10,000 balanced samples

---

## Data Preprocessing

### Category Mapping

Original dataset:

* 130 product types
* 52 color groups

These were consolidated into:

* 14 product categories
* 14 color categories

Examples:

| Original Product | Mapped Category  |
| ---------------- | ---------------- |
| Shirt            | Shirts & Blouses |
| Blouse           | Shirts & Blouses |

| Original Color | Mapped Color |
| -------------- | ------------ |
| Light Grey     | Grey         |
| Dark Grey      | Grey         |

### Image Processing

All images were:

* Verified using file existence checks
* Resized to 224×224 pixels
* Converted to RGB format
* Processed through ResNet50

---

## Model Architecture

### Feature Extraction

A pre-trained ResNet50 network was used as a backbone feature extractor.

The original classification head was removed and replaced with a custom Multi-Task Learning architecture.

### Multi-Task Neural Network

Shared hidden layers learn common visual representations while two output branches predict:

1. Product Category
2. Color Group

Techniques used:

* Dense Layers
* Dropout
* L2 Regularization
* ReLU / PReLU Activations
* Adam Optimizer
* Early Stopping

---

## Hyperparameter Optimization

Keras Tuner Random Search was used to optimize:

* Number of hidden layers
* Number of neurons
* Activation functions
* Dropout rates
* Learning rate
* Regularization strength
* Embedding dimensions

The tuning process evaluated multiple architectures and selected the model with the best validation performance.

---

## Results

### Classification Performance

| Metric                          | Score  |
| ------------------------------- | ------ |
| Product Category Accuracy       | 80.55% |
| Color Classification Accuracy   | 71.85% |
| Overall Recommendation Accuracy | 61%    |

The model demonstrated strong performance in recognizing fashion categories while maintaining reliable color prediction capability.

---

## Recommendation Engine

After training:

1. Feature embeddings were extracted from the learned embedding layer.
2. Cosine Similarity was calculated between products.
3. Top-N visually similar products were retrieved.

Recommendations are generated based on:

* Shape
* Texture
* Visual Style
* Color Patterns

rather than product metadata alone.

---

## Technologies Used

* Python
* TensorFlow
* Keras
* ResNet50
* Keras Tuner
* NumPy
* Pandas
* Scikit-Learn
* Google Colab
* Kaggle API

---

## Project Structure

```text
FashionMatch/
│
├── data/
├── notebooks/
│   └── CNN_coding_RENK_v33.ipynb
│
├── models/
│
├── results/
│
├── images/
│
├── README.md
└── requirements.txt
```

---

## Key Learnings

* Multi-Task Learning for Computer Vision
* Transfer Learning using ResNet50
* Feature Embedding Generation
* Hyperparameter Optimization
* Content-Based Recommendation Systems
* Deep Learning Model Evaluation
* Fashion Image Classification

---

## Future Improvements

* Larger training dataset
* Fine-tuning the ResNet backbone
* User-personalized recommendations
* Hybrid recommendation systems
* Integration with real-time fashion e-commerce platforms

---
## Authors

Sude Aslan
Güldeniz Güzelay
---





