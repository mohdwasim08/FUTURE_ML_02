# Support Ticket Classification & Prioritization
### Future Interns — Machine Learning Internship 2026 | Task 2

![Python](https://img.shields.io/badge/Python-3.8+-blue?style=flat&logo=python)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-ML-orange?style=flat&logo=scikit-learn)
![NLTK](https://img.shields.io/badge/NLTK-NLP-green?style=flat)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=flat)
![Internship](https://img.shields.io/badge/Future%20Interns-ML%20Track-purple?style=flat)

---

## Overview

In real companies, support teams receive hundreds to thousands of tickets every day — billing complaints, technical issues, refund requests, and more. Without automation, agents waste hours just sorting tickets instead of solving them.

This project builds a Machine Learning system that:
- Automatically classifies support tickets into categories
- Predicts priority levels (Critical / High / Medium / Low)
- Provides live predictions with confidence scores on new tickets

This is the kind of system used in real SaaS companies, IT helpdesks, and service platforms.

---

## Repository Structure

```
FUTURE_ML_02/
│
├── FUTURE_ML_02.ipynb                  # Main Jupyter Notebook (full pipeline)
├── customer_support_tickets.csv        # Dataset
├── README.md                           # This file
│
└── outputs/                            # Generated visualizations
    ├── target_distribution.png
    ├── subject_distribution.png
    ├── type_priority_heatmap.png
    ├── wordcloud.png
    ├── model_comparison_type.png
    ├── confusion_matrix_type.png
    ├── model_comparison_priority.png
    ├── confusion_matrix_priority.png
    └── summary_dashboard.png
```

---

## Dataset

| Property | Details |
|----------|---------|
| **Source** | [Customer Support Ticket Dataset — Kaggle](https://www.kaggle.com/datasets/suraj520/customer-support-ticket-dataset) |
| **Total Records** | 8,469 tickets |
| **Total Columns** | 17 |
| **Key Text Feature** | `Ticket Description` + `Ticket Subject` |
| **Target 1** | `Ticket Type` (Category) |
| **Target 2** | `Ticket Priority` |

### Ticket Type Distribution

| Category | Count |
|----------|-------|
| Refund Request | 1,752 |
| Technical Issue | 1,747 |
| Cancellation Request | 1,695 |
| Product Inquiry | 1,641 |
| Billing Inquiry | 1,634 |

### Ticket Priority Distribution

| Priority | Count |
|----------|-------|
| Medium | 2,192 |
| Critical | 2,129 |
| High | 2,085 |
| Low | 2,063 |

---

## Tech Stack

| Tool | Purpose |
|------|---------|
| **Python 3.8+** | Core language |
| **Pandas & NumPy** | Data manipulation |
| **NLTK** | Text preprocessing (stopwords, lemmatization) |
| **Scikit-learn** | TF-IDF vectorization & ML models |
| **Matplotlib & Seaborn** | Visualizations |
| **WordCloud** | Text frequency visualization |
| **Jupyter Notebook** | Development environment |

---

## Project Pipeline

```
Raw CSV Data
     |
     v
Exploratory Data Analysis
     |  - Class distributions
     |  - Subject frequency
     |  - Type vs Priority heatmap
     v
Text Preprocessing
     |  - Lowercase conversion
     |  - Remove template placeholders {product_purchased}
     |  - Remove URLs, emails, numbers
     |  - Stopword removal
     |  - Lemmatization
     |  - Combine Subject + Description
     v
Feature Extraction
     |  - TF-IDF Vectorizer
     |  - max_features = 5,000
     |  - ngram_range = (1, 2)
     v
Model Training (3 models compared)
     |  - Logistic Regression
     |  - Naive Bayes
     |  - Random Forest
     v
Evaluation
     |  - Accuracy, Precision, Recall, F1-Score
     |  - Confusion Matrix
     |  - Per-class performance
     v
Live Prediction System
        - Input any new ticket
        - Get Category + Priority + Confidence scores
```

---

## Key Features Implemented

- Text cleaning with regex (removes placeholders, URLs, emails, numbers)
- Stopword removal using NLTK
- Word lemmatization for better token normalization
- TF-IDF feature extraction with bigrams
- Ticket category classification (5 classes)
- Ticket priority prediction (4 levels)
- Model comparison across 3 algorithms
- Detailed evaluation — accuracy, precision, recall, F1
- Confusion matrix for both tasks
- WordCloud visualization
- Live prediction function with per-class confidence bars
- Business insights and summary dashboard

---

## How to Run

### 1. Clone the repository
```bash
git clone https://github.com/YOUR_USERNAME/FUTURE_ML_02.git
cd FUTURE_ML_02
```

### 2. Install dependencies
```bash
pip install pandas numpy scikit-learn nltk matplotlib seaborn wordcloud jupyter
```

### 3. Launch the notebook
```bash
jupyter notebook FUTURE_ML_02.ipynb
```

### 4. Run all cells top to bottom
Make sure `customer_support_tickets.csv` is in the same folder as the notebook. The first cell auto-installs all required libraries.

---

## Live Prediction Example

```python
predict_ticket(
    ticket_subject="Payment Issue",
    ticket_description="I was charged twice for my last order. I need a refund for the duplicate payment."
)
```

Output:
```
=======================================================
TICKET ANALYSIS RESULT
=======================================================
Subject    : Payment Issue
Description: I was charged twice for my last order...
-------------------------------------------------------
Category   : Billing Inquiry
Priority   : High
-------------------------------------------------------
Category Confidence:
   Billing Inquiry           ████████████████ 78.3%
   Refund Request            ████ 14.1%
Priority Confidence:
   High                      ████████████ 61.2%
   Critical                  ██████ 28.4%
=======================================================
```

---

## Business Value

| Problem | Solution |
|---------|----------|
| Agents waste time manually sorting tickets | Auto-classification in milliseconds |
| Critical issues get buried in the queue | Priority prediction flags urgent tickets instantly |
| Inconsistent ticket routing | ML model applies consistent logic every time |
| Support backlog grows during peak hours | System scales to thousands of tickets/day |
| Poor customer satisfaction due to delayed responses | Faster routing = faster resolution |

---

## Results Summary

| Task | Best Model | Accuracy |
|------|-----------|----------|
| Ticket Type Classification | *(run notebook to see)* | — |
| Ticket Priority Prediction | *(run notebook to see)* | — |

Results depend on your local run. All 3 models are compared and the best is automatically selected.

---

## Skills Demonstrated

- Natural Language Processing (NLP)
- Text preprocessing and feature engineering
- Multi-class text classification
- Model evaluation and comparison
- Business-oriented ML problem framing
- Data visualization and storytelling

---

## Resources

- [Dataset — Kaggle](https://www.kaggle.com/datasets/suraj520/customer-support-ticket-dataset)
- [Scikit-learn Docs](https://scikit-learn.org)
- [NLTK Docs](https://www.nltk.org)
- [Future Interns](https://futureinterns.com)
- [Future Interns LinkedIn](https://www.linkedin.com/company/future-interns/)

---

## Author

**Mohammad Wasim**
- GitHub: [mohdwasim08](https://github.com/your-username)

---

*Built as part of the [Future Interns](https://futureinterns.com) Machine Learning Internship 2026*  
*Repository: `FUTURE_ML_02`*
