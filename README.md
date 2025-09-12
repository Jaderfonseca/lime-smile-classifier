# Interpreting Toy Neural Networks with LIME
*Mini-project: Can we trust a smiley-face classifier?*

📄[Mini-report PDF](Mini-Report_LIME_Based_Analysis_of_Smile_vs._Not_Smile.pdf)

The mini-report PDF is included for quick reference in portfolio submissions. It provides a concise overview of methods, results, and key figures, without requiring readers to open the full notebook.

## Objective
This mini-project explores how a simple neural network can classify toy "smiley face" images, and applies LIME to interpret what the model is really learning.
The goal is to investigate trust, reliability, and bias in small-scale AI systems — and connect these insights to real-world applications such as facial recognition and justice.
___

## Ethical Note

The interpretability patterns uncovered in this toy study raise broader concerns when extrapolated to real-world domains such as facial recognition and justice systems. 

___

## How to Run

1. **Open** this notebook in [Open in Colab](https://colab.research.google.com/github/Jaderfonseca/lime-smile-classifier/blob/main/neural_network_with_LIME.ipynb) or a local Jupyter environment.  
2. **Run the Setup cell** to install required dependencies.  
3. **Execute the notebook cells in order**:
   - **Data generation** → creates synthetic images under `data/raw/` with labels.  
   - **Preprocessing** → builds preprocessed arrays (`data/processed/`).  
   - **Model training** → trains the neural network classifier.  
   - **Evaluation** → computes accuracy, loss curves, and confusion matrix.  
   - **Interpretability (LIME)** → produces explanations highlighting image regions that drive predictions.  
4. **Outputs** (datasets, models, metrics, and figures) are automatically saved into their respective folders.

**Environment**
- Python 3.10+  
- TensorFlow/Keras 2.15+  
- NumPy, scikit-learn, matplotlib, pillow, scikit-image, lime

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
___

## Repository Structure

```text
data/
├── processed/
│   ├── X_test.npy
│   ├── X_train.npy
│   ├── y_test.npy
│   ├── y_train.npy
│   └── preprocess_meta.json
├── raw/
│   ├── labels.csv
│   ├── not_smile/ # synthetic images (≈499)
│   └── smile/     # synthetic images (≈499)
│   └── .gitkeep

figures/
├── accuracy.png
├── confusion_matrix.png
├── exp_error1.png
├── exp_grid_not_smile.png
├── exp_grid_smile.png
├── exp_sample1.png … exp_sample10.png
├── lime_sample_smile.png
├── lime_sample_not_smile.png
├── mlp_accuracy.png
├── mlp_confusion_matrix.png
├── mlp_loss.png
└── raw_idx132.png

models/
├── mlp_smile_classifier.h5
├── mlp_smile_final.keras
├── mlp_smile_best.keras
├── mlp_smile_classifier.keras
└── mlp_smile_history.json

results/
├── classification_report.txt
├── history.npy
└── mlp_history.json

notebooks/
└── .gitkeep

```
___

## Key Figures  

- **Training accuracy curve** → `figures/mlp_accuracy.png`  
- **Training loss curve** → `figures/mlp_loss.png`  
- **Confusion matrix** → `figures/mlp_confusion_matrix.png`  
- **Smile Grid (LIME)** → `figures/exp_grid_smile.png`  
- **Not Smile Grid (LIME)** → `figures/exp_grid_not_smile.png`  
- **Error Case (idx 132)** → `figures/exp_error1.png`  


## ⚠️ Limitations

- Synthetic dataset with limited variation.
- Small subset of cases inspected (5 Smile, 5 Not Smile, +1 error).
- Ambiguity in some labels (e.g., idx 132: misclassified by the model and unclear even for humans).
- LIME may highlight irrelevant borders/eyes, and explanations vary with perturbations.
___

## License
For academic/portfolio use only.
