# D7084E_XAI_Lab4

This project explores phishing detection with explainable AI methods. The notebook compares several model families, including a decision tree, logistic regression, random forest, semi-supervised learning, and a self-supervised feature-learning approach. The focus is on understanding which URL and website features drive the phishing prediction and how the explanations change depending on the learning setup.

## Notebook structure

The main notebook is:
- Lab4_1_Explaining_Phishing_Detectors.ipynb

It contains the following stages:
- Part A: model training and evaluation
- Part B: explainability with SHAP and LIME
- Part C: robustness check without external lookup features
- Part D: rule-based explanation stage

## Main results from the completed sections

### Part A
The supervised models show that the full random forest performs best on the test set, with Macro-F1 around 0.965 and FAR around 0.037. The semi-supervised Random Forest does not improve over the 5% labelled forest, with Macro-F1 decreasing from 0.940 to 0.934 and FAR increasing from 0.062 to 0.071. The self-supervised model slightly improves over the low-label logistic regression, with Macro-F1 increasing from 0.912 to 0.918.

### Part B
The explainability analysis highlights features such as google_index, page_rank, and nb_www as consistently important. These findings are consistent with the idea that suspicious domains often have weaker search visibility and less reputable web presence. SHAP and LIME both identify the same general patterns, although their local rankings can differ slightly for individual URLs.

### Part C
The robustness check removes seven external lookup features and trains the same Random Forest again without them. The model performance drops from Macro-F1 0.965 to 0.943 and FAR increases from 0.037 to 0.054, showing that the external features contribute meaningfully to prediction quality. Even without those features, the model still relies on URL-based indicators such as nb_hyperlinks, nb_www, phish_hints, safe_anchor, and ratio_extHyperlinks.

## Part D
To be completed...

## How to run the notebook

1. Open the project folder in Jupyter Notebook or VS Code.
2. Make sure the dataset is available in the project folder:
   - data/dataset_phishing.csv
3. Open the notebook:
   - Lab4_1_Explaining_Phishing_Detectors.ipynb
4. Run the cells in order from top to bottom.
5. The notebook loads the dataset, trains the models, prints evaluation metrics, and generates SHAP/LIME explanation plots.

## Requirements

The notebook uses the following Python libraries:
- pandas
- numpy
- scikit-learn
- matplotlib
- shap
- lime

A standard Python environment with these packages installed is sufficient to run the notebook.
