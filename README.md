# Fake News NLP Classifier

End-to-end Natural Language Processing project for detecting fake news with TF-IDF features, interpretable analysis, and a reproducible scikit-learn pipeline.

## Repository Metadata

- Repository name: `fake-news-nlp-classifier`
- Description: `End-to-end NLP notebook for fake news detection using TF-IDF features, interpretable exploratory analysis, and a reproducible scikit-learn classification pipeline.`

## Project Overview

This repository contains a publication-ready notebook that explores a labeled fake news dataset and trains a baseline NLP classifier. The workflow covers data loading, exploratory analysis, model training, evaluation, feature interpretation, topic snapshots, and model export.

## Dataset

The notebook uses the public course dataset available at:

`https://proai-datasets.s3.eu-west-3.amazonaws.com/fake_news.zip`

The archive contains:

- `True.csv`: verified news articles.
- `Fake.csv`: fake news articles.

The notebook downloads the archive automatically when the CSV files are not already available locally. Data files are ignored by Git so the repository stays lightweight.

## Repository Structure

```text
.
|-- fake_news_detection_nlp.ipynb
|-- README.md
|-- REPO_METADATA.md
|-- requirements.txt
|-- .gitignore
|-- data/          # created locally, ignored by Git
|-- models/        # created locally, ignored by Git
```

## Setup

Create and activate a virtual environment, then install the dependencies:

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

On Windows, activate the environment with:

```bash
.venv\Scripts\activate
```

## Run the Notebook

Start Jupyter and open the notebook:

```bash
jupyter notebook fake_news_detection_nlp.ipynb
```

For a faster local smoke test, set a sample size before running the notebook kernel:

```bash
SAMPLE_SIZE=5000 jupyter notebook fake_news_detection_nlp.ipynb
```

## Modeling Approach

The baseline model is a scikit-learn pipeline with:

- `TfidfVectorizer` for unigram and bigram text features.
- `LogisticRegression` for a strong, interpretable classifier.
- Standard classification metrics and a confusion matrix for evaluation.
- Feature-weight inspection to identify terms most associated with each class.
- NMF topic modeling for a lightweight snapshot of recurring fake-news themes.

## Notes

This project is intended as an NLP portfolio notebook and a deployable baseline, not as a production fact-checking system. Before real-world use, validate it on newer sources, check calibration, and monitor for data drift.
