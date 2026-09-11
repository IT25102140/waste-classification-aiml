# Waste Classification AIML Project

Six-member preprocessing pipeline:

1. **Member 01**: Data Cleaning
2. **Member 02**: Duplicate Detection
3. **Member 03**: Label Validation
4. **Member 04**: Image Standardization
5. **Member 05 (Ifaza M.D.U — IT25102486)**: Pixel Normalization
6. **Member 06**: Training-only Augmentation

---

## Member 05 — Pixel Normalization Documentation

### Overview & Theoretical Justification
Pixel Normalization transforms input raw pixel values (RGB channels in range $[0, 255]$ or $[0.0, 1.0]$) into a standardized distribution zero-centered with unit variance. 

### Why ImageNet Normalization?
Pretrained deep learning models (such as ResNet, MobileNet, EfficientNet) trained on the ImageNet benchmark expect input features normalized using the dataset-wide mean ($\mu$) and standard deviation ($\sigma$):
- **Mean ($\mu$)**: `[0.485, 0.456, 0.406]`
- **Std ($\sigma$)**: `[0.229, 0.224, 0.225]`

This prevents gradient explosion/vanishing, accelerates backpropagation convergence, and aligns input feature distributions with transfer-learning weights.

### Pipeline Input & Output Specifications
- **Input Stage**: `data/processed/stage4_standardized` (2,622 images)
- **Output Stage**: `data/processed/stage5_normalized` (2,622 images)
- **Image Size**: $224 \times 224$ pixels (RGB)
- **PyTorch Tensor Shape**: `(3, 224, 224)`

### Verification Results
| Class | Stage 4 Input | Stage 5 Output | Status |
| :--- | :---: | :---: | :---: |
| **Hazardous** | 672 | 672 | Verified Match (100%) |
| **Non-Recyclable** | 637 | 637 | Verified Match (100%) |
| **Organic** | 663 | 663 | Verified Match (100%) |
| **Recyclable** | 650 | 650 | Verified Match (100%) |
| **TOTAL** | **2,622** | **2,622** | **0 Errors / 0 Lost** |

### Output Artifacts
- **Notebook**: `notebooks/IT25102486_PixelNormalization.ipynb`
- **Reusable Transform Module**: `results/outputs/member5_normalization_transform.py`
- **Specification JSON**: `results/outputs/member5_normalization_spec.json`
- **Stage 5 Manifest CSV**: `results/outputs/member5_stage5_manifest.csv`
- **EDA Visualization**: `results/eda_visualizations/member5_normalization_histogram.png`
- **Completion Record**: `results/outputs/IT25102486_completion_record.json`

---

*Final integration occurs in `group_pipeline.ipynb` after all 6 preprocessing stages are completed.*
