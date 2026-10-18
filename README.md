# Undergrad Thesis on Machine Learning

**Topic:** Machine Learning Models for Detection of URL-Based Phishing Attacks

### Abstract:
```text
Phishing attacks remain a major cybersecurity threat, using fake websites to trick users into 
revealing sensitive information like passwords and credit card details. Current detection methods, 
such as blacklists of known malicious sites, struggle to keep up with new phishing tactics. This 
research tackles this problem by developing lightweight, real-time machine learning models for 
detecting phishing URLs using Logistic Regression and Multinomial Naive Bayes algorithms. 

A large dataset of 549,346 entries of legitimate and phishing URLs was collected from Kaggle, 
followed by preprocessing steps including duplicate removal, tokenization with RegexpTokenizer, 
stemming using SnowballStemmer, and conversion into a numerical feature matrix using CountVectorizer. 
Result shows that Logistic Regression performs slightly better (96.5% accuracy) than Multinomial 
Naive Bayes (95.7%), making it more reliable for real-world use. Both models were tested on Accuracy, 
Precision, Recall, and F1-score to ensure they run efficiently inside resource-constrained environments.
```

---

## Folders

| Name | Description | Link |
| :--- | :--- | :--- |
| **Documents** | Contains the full B.Sc. thesis PDF, certification pages, and literature reviews. | [Click](./Documents/) |
| **Dataset** | Curated source URLs containing 549,347 labeled web entries. | [Click](./Dataset/) |
| **Jupyter Notebooks** | Complete data preprocessing pipelines, feature engineering, and model training routines. | [Click](<./Jupyter Notebooks/>) |
| **Source Code** | Production scripts for real-time text parsing, Chi-squared selection, and inference. | [Click](<./Source Code/>) |

---

## 📈 Algorithmic Performance Summary

The systems were benchmarked over an **80/20 train-test partition** optimized via cross-validation and `RandomUnderSampler` balancing:

* **Logistic Regression (LR):** **96.5% Validation Accuracy** (Optimized via Ridge Regularization).
* **Multinomial Naive Bayes (MNB):** **95.7% Validation Accuracy** (Optimized via discrete token frequencies).

### Core Preprocessing Workflow
```python
# Real-time local inference transformation sequence
from nltk.tokenize import RegexpTokenizer
from nltk.stem.snowball import SnowballStemmer

tokenizer = RegexpTokenizer(r'[A-Za-z]+') # Extracts pure text vectors
stemmer = SnowballStemmer("english")       # Maps variations back to root forms

def clean_url(url):
    return " ".join([stemmer.stem(token) for token in tokenizer.tokenize(url.lower())])
```

---

## 📜 Academic Citation

```text
Okon, I. U. (2025). Machine Learning Models for Detection of URL-Based Phishing Attacks (B.Sc. Thesis). Department of Computer Science, Faculty of Computing, University of Uyo, Uyo, Nigeria.
```
# -url-phishing-detection-ml
