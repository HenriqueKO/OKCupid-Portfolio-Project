# OKCupid Profile Matching & Clustering

## Project Overview
This project explores the OKCupid dating profiles dataset with the goal of:
- Understanding user attributes and preferences
- Building meaningful profile representations
- Clustering similar users
- Finding the most similar profiles for a given user

The project combines **tabular data**, **text embeddings**, and **unsupervised learning** techniques.

---

## Dataset
- Source: OKCupid public dataset
- Size: ~60k profiles
- Data types:
  - Categorical features (e.g. gender, orientation, lifestyle habits)
  - Text data (user essays)
  - Missing values and noisy real-world inputs

> The original dataset is not included due to size limitations.

---

## Methodology

### 1. Data Cleaning & Feature Engineering
- Handled missing values
- Created flags for missing information
- Normalized categorical data
- Cleaned and preprocessed text essays

### 2. Text Representation
- Combined all essay fields into a single text input
- Generated sentence embeddings using:
  - **Sentence Transformers (all-MiniLM-L6-v2)**

### 3. Tabular Encoding
- Categorical features encoded using `LabelEncoder`
- Ensured support for unseen categories using an `unknown` fallback
- Scaled tabular features with `StandardScaler`

### 4. Feature Fusion
- Concatenated:
  - Scaled tabular features
  - Text embeddings
- Final vector used for clustering and similarity search

### 5. Clustering
- Applied **KMeans clustering**
- Used cluster assignment to narrow similarity search

### 6. Similarity Matching
- Used **cosine similarity**
- Returned top-N most similar profiles within the same cluster

---

## Results
- Meaningful clusters with shared lifestyle and preference traits
- High-quality similarity matches
- Robust handling of missing or unseen categorical values

---

## Tech Stack
- Python
- Pandas, NumPy
- Scikit-learn
- Sentence-Transformers
- Matplotlib / Seaborn

---

## How to Run

1. Clone this repository
2. Download the OKCupid dataset (`profiles.csv`)
   - The dataset is not included due to GitHub file size limits
   - It can be obtained from the original Codecademy project or Kaggle
3. Place `profiles.csv` in the root project directory
4. Install dependencies
5. Open and run `date-a-scientist.ipynb`
---

## Notes
- This project focuses on **unsupervised learning**, so traditional metrics like accuracy or F1-score are not applicable.
- Emphasis was placed on feature engineering and real-world robustness.

---

## Author
Henrique Kuhl Oliveira
