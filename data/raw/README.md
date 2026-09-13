# Raw Dataset

The raw waste-image dataset is maintained separately from the Git repository
because the complete image collection is approximately 1 GB and is not
appropriate for storage in ordinary Git history.

The dataset used for the preprocessing pipeline contains 2,935 images
across four classes:

- Hazardous
- Non-Recyclable
- Organic
- Recyclable

The preprocessing workflow and dataset manifests in this repository document
the transformations applied to the dataset.

The final frozen dataset contains 2,622 images after cleaning, duplicate
removal, and label validation.
