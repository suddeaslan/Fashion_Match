
# Fashion Match: Image-Based Recommendation System Using Multi-Task Learning

An image-based personalized fashion recommendation system built on top of the **H&M Personalized Fashion Recommendations** dataset. This project extracts deep visual features using a pre-trained backbone and applies a custom Multi-Task Convolutional Neural Network (CNN) to simultaneously classify clothing categories and colors, using the learned embeddings to suggest visually similar alternatives.

## 📌 Project Overview
* **Objective:** Address product discovery challenges in e-commerce by providing instant, visually consistent alternative recommendations.
* **Architecture:** Multi-Task Learning CNN with a pre-trained ResNet50 backbone and custom shared dense layers.
* **Tasks:** Simultaneous classification of 14 Product Categories and 14 Color Groups.
*  **Recommendation Strategy:** Isulating the model's 64-feature bottleneck layer to calculate Cosine Similarity between items.

---

## 💾 Dataset & Subsampling Strategy
The project uses the **H&M Personalized Fashion Recommendations** dataset from Kaggle. 

* **Total Dataset Size:** ~28 GB (Images & Metadata)
* **Subsampling & Cleaning:** To optimize performance, the dataset was cleaned of missing values, rare classes (fewer than 80 examples) were filtered out, and a stratified random sample of **10,000 images** was extracted to preserve the native class distribution.

---

## 🗂️ Project Directory & Data Setup
Since the dataset exceeds GitHub's size limitations, the raw data files are stored externally.

* **Data Storage (Google Drive):** [[YOUR_GOOGLE_DRIVE_LINK_HERE](https://drive.google.com/drive/folders/1gt0zCNxzuxTolYEmGhLogrzrXRAilh96?usp=drive_link)]

To run the codebase locally, please follow this structure:
```text
├── CNN_coding_RENK_v33.ipynb      # Main development and training notebook
├── README.md                      # Project documentation
└── data/                          # <--- Create this folder (Git ignored)
    ├── articles.csv               # Downloaded from Google Drive
    └── images/                    # Extracted image folders (010/, 011/, etc.)










