# Text Summarization System

An NLP project focused on building a text summarization system using deep learning. The project explores news article datasets, performs data cleaning and preprocessing, prepares training and evaluation splits, and analyzes token lengths for the T5 model.

**Project Status:** 🚧 In Progress

## Overview

The goal of this project is to develop a system that can generate concise summaries from long text documents while preserving their important information.

The current development phase focuses on preparing reliable datasets for abstractive text summarization using the BBC News Summary and CNN/DailyMail datasets.

## Objectives

- Explore and understand text summarization datasets.
- Perform exploratory data analysis (EDA).
- Clean and preprocess article-summary pairs.
- Remove empty records and duplicate articles.
- Analyze article and summary length distributions.
- Prepare training, validation, and testing datasets.
- Analyze token lengths using the T5 tokenizer.
- Prepare the datasets for future model training and evaluation.

## Datasets

This project uses two news summarization datasets:

| Dataset | Original Records | Cleaned Records |
|---|---:|---:|
| BBC News Summary | 2,224 | 2,126 |
| CNN/DailyMail | 11,490 | 11,488 |

### BBC News Summary
Used as the primary dataset for model development.

### CNN/DailyMail
Used as an external dataset for evaluating the generalization of the future summarization model.

**Note:** The dataset files are not included in this repository. You need to obtain the datasets separately and place them in the expected directories.

## Current Implementation

### 1. Exploratory Data Analysis
- Dataset structure and column inspection.
- Missing-value analysis.
- Duplicate-record analysis.
- Article and summary length statistics.
- Word-count distribution visualization.
- Dataset compression-ratio analysis.

### 2. Data Cleaning and Preprocessing
- Standardization of article and summary column names.
- Whitespace normalization.
- Removal of empty records.
- Removal of duplicate article-summary pairs.
- Removal of repeated articles.
- Export of cleaned datasets.

### 3. Dataset Preparation
The cleaned BBC dataset is divided into three subsets:

| Split | Percentage | Records |
|---|---:|---:|
| Training | 80% | 1,700 |
| Validation | 10% | 213 |
| Testing | 10% | 213 |

The split uses `random_state=42` for reproducibility.

The CNN/DailyMail dataset is retained separately for external evaluation.

### 4. T5 Tokenization Analysis
The project uses the `t5-small` tokenizer to:

- Convert articles and summaries into token IDs.
- Calculate token lengths.
- Analyze token-length distributions.
- Examine token-length percentiles.
- Prepare for selecting suitable input and output sequence lengths.

## Technology Stack

| Category | Technologies |
|---|---|
| Programming Language | Python |
| Data Processing | Pandas, NumPy |
| Data Visualization | Matplotlib, Seaborn |
| Machine Learning | Scikit-learn |
| Deep Learning | PyTorch |
| NLP | Hugging Face Transformers, T5 Tokenizer |
| Development Environment | JupyterLab, Jupyter Notebook |
| Version Control | Git, GitHub |

## Repository Structure

```text
text-summarization-system/
│
├── notebooks/
│   ├── 01_data_exploration.ipynb
│   └── 02_dataset_preparation.ipynb
│
├── data/
│   ├── raw/
│   │   ├── bbc-news-summary.csv
│   │   └── cnn_dailymail_test_dataset.csv
│   │
│   ├── processed/
│   │   ├── bbc_clean.csv
│   │   └── cnn_clean.csv
│   │
│   └── splits/
│       ├── train.csv
│       ├── validation.csv
│       ├── test.csv
│       └── cnn_external_test.csv
│
├── .gitignore
├── LICENSE
├── requirements.txt
└── README.md
```

*The data directories and generated CSV files are created locally by the notebooks and are not currently tracked in Git.*

## Installation and Setup

### 1. Clone the Repository

```bash
git clone https://github.com/Kowshik7007/text-summarization-system.git
```

```bash
cd text-summarization-system
```

### 2. Create a Virtual Environment

```bash
python -m venv .venv
```

Activate it on Windows:

```bash
.venv\Scripts\activate
```

On Linux or macOS:

```bash
source .venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

Install the additional dependencies used by the T5 tokenizer notebook:

```bash
pip install transformers sentencepiece
```

### 4. Prepare the Dataset

Place the downloaded dataset files in the following directory:

```text
data/raw/
```

Expected filenames:

```text
bbc-news-summary.csv
cnn_dailymail_test_dataset.csv
```

### 5. Launch JupyterLab

```bash
jupyter lab
```

Open the notebooks in the following order:

1. `01_data_exploration.ipynb`
2. `02_dataset_preparation.ipynb`

Run the notebook cells sequentially.

## Current Progress

- [x] Repository initialization
- [x] Development environment setup
- [x] Dataset exploration
- [x] Missing-value and duplicate analysis
- [x] Text cleaning and preprocessing
- [x] Dataset standardization
- [x] Training, validation, and testing split
- [x] Dataset overlap verification
- [x] T5 tokenizer integration
- [x] Token-length analysis
- [ ] Model training and fine-tuning
- [ ] Model evaluation
- [ ] Summary generation pipeline
- [ ] Inference interface

## Future Development

The next development phases will focus on:

- Fine-tuning a T5-based sequence-to-sequence model.
- Experimenting with input and output sequence lengths.
- Evaluating generated summaries using ROUGE metrics.
- Performing qualitative error analysis.
- Testing model generalization on the CNN/DailyMail dataset.
- Building an interface for interactive text summarization.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Author

**Kowshik Kormokar**

- GitHub: [@Kowshik7007](https://github.com/Kowshik7007)

---

⭐ If you find this project interesting, feel free to explore the repository and follow its development.
