# Interpreting Toy Neural Networks with LIME
*Mini-project: Can we trust a smiley-face classifier?*

📄[Mini-report PDF](Mini-Report_LIME_Based_Analysis_of_Smile_vs._Not_Smile)
The mini-report PDF is included for quick reference in portfolio submissions. It provides a concise overview of methods, results, and key figures, without requiring readers to open the full notebook.

## Objective
This mini-project explores how a simple neural network can classify toy "smiley face" images, and applies LIME to interpret what the model is really learning.
The goal is to investigate trust, reliability, and bias in small-scale AI systems — and connect these insights to real-world applications such as facial recognition, medicine, and justice.
___

## Ethical Note

The interpretability patterns uncovered in this toy study raise broader concerns when extrapolated to real-world domains such as facial recognition and justice systems. 

___

## How to Run

The notebook and scripts are structured to ensure both automation and reproducibility.

- **Batch LIME explanations**:  
  A helper function (`run_lime_batch`) is included to automatically generate and save multiple LIME explanations.  
  - Inputs: a list of indices (e.g., 5 *smile* and 5 *not smile* examples).  
  - Outputs: corresponding `.png` files saved in `figures/` (`exp_sample*.png`, `exp_grid_smile.png`, `exp_grid_not_smile.png`, etc.).  
  - These images are the ones reported and discussed in the mini-report.

- **Reproducibility**:  
  To keep experiments consistent, seeds are fixed for NumPy, Python, and TensorFlow/Keras. Running the notebook from top to bottom (`Restart & Run All`) regenerates the same metrics and explanations without drift.

- **Outputs**:  
  The pipeline reproduces:  
  1. Model training metrics (`accuracy`, `loss`, `confusion matrix`).  
  2. Batch LIME explanations for both classes.  
  3. Error case analysis (idx 132).  
  4. Figures saved automatically under `figures/`.  

This ensures that results presented in the **Mini-Report** can be fully reproduced by rerunning the notebook.
___

## Repository Structure

```text
data/
├── raw/
│   └── labels.csv
├── processed/
│   ├── X_train.npy
│   ├── y_train.npy
│   ├── X_test.npy
│   └── y_test.npy

models/
├── mlp_smile_classifier.h5
├── mlp_smile_final.keras
├── mlp_smile_best.keras
├── mlp_smile_classifier.keras
└── mlp_smile_history.json

figures/
├── mlp_accuracy.png
├── mlp_loss.png
├── mlp_confusion_matrix.png
├── lime_sample_smile.png
├── lime_sample_not_smile.png
├── exp_sample1.png … exp_sample10.png
├── exp_grid_smile.png
├── exp_grid_not_smile.png
├── exp_error1.png
└── raw_idx132.png

results/
├── classification_report.txt
├── history.npy
└── mlp_history.json

```
___

## License
For academic/portfolio use only.
