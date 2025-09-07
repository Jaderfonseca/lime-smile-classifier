# Interpreting Toy Neural Networks with LIME
*Mini-project: Can we trust a smiley-face classifier?*

## Objective
This mini-project explores how a simple neural network can classify toy "smiley face" images, and applies LIME to interpret what the model is really learning.
The goal is to investigate trust, reliability, and bias in small-scale AI systems — and connect these insights to real-world applications such as facial recognition, medicine, and justice.
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

docs/
├── mini-report.md
└── notes.md
```
___

## How to Run
Instructions will be provided once the first notebook is complete.
For now:
1. Clone this repository.
2. Open the `notebooks/` folder in Google Colab.
3. Dependencies will be listed in `requirements.txt`.
___

## Ethical Note
Beyond code and graphs, this project highlights a central ethical concern:
Can we trust simple models to make decisions? What patterns are they actually learning, and how does this connect to real-world systems that affect people’s lives?
___

## License
For academic/portfolio use only.
