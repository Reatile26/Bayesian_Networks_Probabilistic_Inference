# Bayesian Networks for Heart Disease Prediction

**EDAB6808 · Assignment 3 · University of the Free State**

## Project overview

This project compares an expert-designed Bayesian network with a network learned from data. It examines how network structure affects heart-disease classification, posterior probabilities and interpretation under different evidence profiles.

## Data and preparation

The analysis uses the Cleveland heart-disease dataset, with **303 observations and 13 predictive variables**. The original diagnostic outcome is converted to a binary target: disease absent or disease present.

The data are split into **242 training observations and 61 held-out test observations**. Imputation and discretisation are learned from the training data before being applied to the test data.

## Analytical approach

1. Inspect variable coding, missing values and the target distribution.
2. Specify an expert network containing **16 directed edges**.
3. Learn an alternative structure using **Hill Climbing and the Bayesian Information Criterion (BIC)**, producing **11 edges**.
4. Estimate conditional probability tables and inspect their implications.
5. Compare posterior probabilities across **5,184 evidence profiles** per network.
6. Evaluate both networks on the same held-out observations and compare them with a majority-class baseline.

## Key findings

| Held-out measure | Expert network | Learned network | Majority baseline |
| --- | --- | --- | --- |
| Accuracy | **90.2%** | **85.3%** | **54.1%** |
| F1-score | **0.893** | **0.836** | **0.000** |
| ROC-AUC | **0.961** | **0.915** | **0.500** |

The expert network performed better on this test split. The learned network was structurally sparser, while both networks resolved all 5,184 inference profiles. Posterior rankings had a Spearman correlation of approximately **0.766**, showing broad agreement alongside meaningful differences in estimated probabilities.

## Repository materials

| Material | Contents |
| --- | --- |
| Jupyter notebook (`.ipynb`) | Preprocessing, network construction, parameter estimation, inference, evaluation and saved outputs. |
| Executive report (`.pdf`) | Network diagrams, probability comparisons, predictive results and discussion. |

## Tools and skills

Python, pandas, NumPy, bnlearn, scikit-learn and data visualisation tools. The project develops probabilistic reasoning, graphical modelling, conditional probability interpretation and comparative model evaluation.

## Interpretation and limitations

Network arrows encode the chosen probabilistic dependencies; they do not establish medical causation. The expert structure represents analytical assumptions rather than an independently validated clinical model. Performance reflects a small dataset and one held-out split, so the results do not establish universal model superiority or clinical suitability.

The main lesson is that a network's structure influences both its predictive performance and the probability estimates used to explain individual evidence profiles.

## Credits

Collaborative coursework by **Reatile Seekoei and Mamello Malape** for EDAB6808 at the University of the Free State. The executive report documents the dataset source, references and modelling assumptions.
