# Machine Learning Models to Predict Spam Email

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/danishjavedcodes/Ml_models_to_Predict_Spam_Email/blob/main/Email_Spam_Filter.ipynb)
[![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python&logoColor=white)](https://www.python.org/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-orange)](https://scikit-learn.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)](https://jupyter.org/)

Compare **spam email detection** classifiers built with **Python** and **scikit-learn**: **Gaussian Naive Bayes**, **Multinomial Naive Bayes**, and a **Decision Tree (J48)**. This repository includes a labeled **ham/spam email dataset**, a full **Jupyter notebook** pipeline, and reproducible **accuracy** and **confusion matrix** results for **text classification** and **email spam filtering**.

---

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Model Results](#model-results)
- [Dataset](#dataset)
- [Project Structure](#project-structure)
- [Quick Start](#quick-start)
- [How It Works](#how-it-works)
- [Requirements](#requirements)
- [Use Cases](#use-cases)
- [Contributing](#contributing)
- [License](#license)
- [Author](#author)

---

## Overview

**Spam email prediction** is a classic **supervised machine learning** problem: given the body of an email, classify it as **ham** (legitimate) or **spam** (unsolicited). This project trains and evaluates three widely used models on real email text using **bag-of-words** features from `CountVectorizer`.

| Model | Test accuracy |
|-------|---------------|
| **Multinomial Naive Bayes** | **97.74%** |
| Gaussian Naive Bayes | 95.81% |
| Decision Tree (J48) | 93.94% |

**Multinomial Naive Bayes** performs best on this dataset and is a common baseline for **NLP spam detection**.

---

## Features

- End-to-end **email spam filter** workflow in a single notebook
- **Text preprocessing** and label encoding (`ham` → 0, `spam` → 1)
- **Train/test split** (70% train / 30% test)
- **CountVectorizer** for word-frequency features
- Side-by-side comparison of **Naive Bayes** and **Decision Tree** classifiers
- **Accuracy score** and **confusion matrix** for each model
- **Google Colab** support — run without local setup

---

## Model Results

Evaluation uses a 30% hold-out test set (`random_state=0`).

### Multinomial Naive Bayes (best)

- **Accuracy:** 97.74%
- Confusion matrix: TN=1115, FP=13, FN=22, TP=402

### Gaussian Naive Bayes

- **Accuracy:** 95.81%
- Confusion matrix: TN=1107, FP=21, FN=44, TP=380

### J48 Decision Tree

- **Accuracy:** 93.94%
- Confusion matrix: TN=1082, FP=46, FN=48, TP=376

---

## Dataset

| Property | Value |
|----------|--------|
| File | `spam_ham_dataset.csv` |
| Total emails | **5,171** |
| Ham (legitimate) | 3,672 |
| Spam | 1,499 |
| Columns | `label`, `text` (after preprocessing) |

Each row contains the full **email text** and a **ham** or **spam** label. The notebook drops index and duplicate numeric label columns before training.

---

## Project Structure

```
Ml_models_to_Predict_Spam_Email/
├── Email_Spam_Filter.ipynb   # Main notebook: train & evaluate all models
├── spam_ham_dataset.csv      # Labeled ham/spam email dataset
└── README.md                 # Project documentation
```

---

## Quick Start

### Option 1: Google Colab (recommended)

1. Open the notebook in Colab:

   [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/danishjavedcodes/Ml_models_to_Predict_Spam_Email/blob/main/Email_Spam_Filter.ipynb)

2. Run all cells. The notebook clones this repo and loads `spam_ham_dataset.csv` automatically.

### Option 2: Local Jupyter

```bash
git clone https://github.com/danishjavedcodes/Ml_models_to_Predict_Spam_Email.git
cd Ml_models_to_Predict_Spam_Email
pip install pandas scikit-learn jupyter
jupyter notebook Email_Spam_Filter.ipynb
```

Update the dataset path in the notebook if you are not using Colab:

```python
data = pd.read_csv("spam_ham_dataset.csv")
```

---

## How It Works

1. **Load data** — Read `spam_ham_dataset.csv` with pandas.
2. **Preprocess** — Remove extra columns; map `ham`/`spam` to binary labels.
3. **Split** — `train_test_split` on email text and labels (30% test).
4. **Vectorize** — `CountVectorizer` converts text to word-count features.
5. **Train** — Fit Gaussian NB, Multinomial NB, and Decision Tree.
6. **Evaluate** — Report accuracy and confusion matrix per model.

Core libraries: `pandas`, `sklearn.feature_extraction.text.CountVectorizer`, `sklearn.naive_bayes`, `sklearn.tree.DecisionTreeClassifier`, `sklearn.model_selection`, `sklearn.metrics`.

---

## Requirements

```
pandas
scikit-learn
jupyter   # optional, for local notebooks
```

Python **3.8+** recommended.

---

## Use Cases

- Learning **spam classification** and **text mining** with scikit-learn
- Comparing **Naive Bayes vs decision trees** for email data
- Course projects on **machine learning**, **NLP**, or **cybersecurity**
- Baseline for building a production **spam filter** (add TF-IDF, cross-validation, or deep learning as next steps)

---

## Contributing

Contributions are welcome. To suggest improvements:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/improve-model`)
3. Commit your changes and open a pull request

Ideas: add `requirements.txt`, TF-IDF vectorization, cross-validation, or a simple prediction API.

---

## License

This project is open source. Add a `LICENSE` file (e.g. MIT) if you plan to distribute or reuse the code commercially.

Dataset and notebook code: use and modify with attribution to this repository.

---

## Author

**Danish Javed** — [github.com/danishjavedcodes](https://github.com/danishjavedcodes)

Repository: [Ml_models_to_Predict_Spam_Email](https://github.com/danishjavedcodes/Ml_models_to_Predict_Spam_Email)

---

### Suggested GitHub topics

`spam-detection` `email-classification` `machine-learning` `scikit-learn` `naive-bayes` `decision-tree` `nlp` `text-classification` `jupyter-notebook` `python` `ham-spam` `cybersecurity`
