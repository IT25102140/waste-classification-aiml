# Raw Dataset

## Dataset Source

The original waste image dataset used for this project was obtained from Kaggle:

https://www.kaggle.com/datasets/phenomsg/waste-classification?resource=download

## Dataset

Source platform: Kaggle

Dataset name: Waste Classification

The raw dataset contains four main waste classes used in this project:

- Hazardous
- Non-Recyclable
- Organic
- Recyclable

## Usage in This Project

The raw dataset was used as the starting point for the preprocessing pipeline.

Pipeline:

Raw Dataset
→ Dataset Cleaning
→ Exact + Visual Duplicate Detection
→ Label Validation
→ Image Standardization
→ Pixel Normalization
→ Training Augmentation
→ Final Dataset

The final processed dataset is stored separately under:

data/final_dataset/

## Important

The raw dataset is retained as the source/reference dataset and is not modified during preprocessing.
All preprocessing operations produce separate processed stages.
