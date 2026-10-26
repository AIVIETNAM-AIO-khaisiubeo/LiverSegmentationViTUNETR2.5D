# Liver Segmentation with a Vision Transformer (ViT-UNETR 2.5D)
### A simulated AIO2025 Kaggle competition, run on Google Colab

This notebook imitates the rules of the liver-segmentation competition **without joining it**. The data is the public LiTS dataset (abdominal CT scans + liver masks, NIfTI `.nii`). Below is the table summarizing the contents of each section:

| Section | Goal |
|---|---|
| **I. Setup** | Install, imports, settings (`CFG`). |
| **II. Dataset** | Download LiTS, pair CT + mask, make the 80-train / test split. |
| **III. Preprocessing** | HU windowing, keep the slices around the liver, resize to 256 × 256. |
| **IV. Dataset, 2.5D Input, Augmentation** | 3-slice input, flips, rotations, brightness changes. |
| **V. Model** | ViT-UNETR: pretrained ViT encoder + U-Net decoder. |
| **VI. Loss & Training** | Dice + Cross-Entropy loss, AdamW, cosine LR, mixed precision. |
| **VII. Predicting Whole Volumes** | Predict full CT volumes at the original size, check Dice on the validation cases. |
| **VIII. Test Prediction & Submission** | Predict the test CTs, RLE-encode every slice, write `submission.csv`. |
| **IX. Scoring** | Decode `submission.csv` and score it against the hidden test masks (Public / Private Dice). |
