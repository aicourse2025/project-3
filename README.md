# Project 3

## Preprocessing and data cleaning
1. **Load Data**: Read CSV and inspect structure.
2. **Initial Checks**: Identify missing values, empty fields, and duplicates.
3. **Clean Data**:
   - Remove duplicates and empty texts.
   - Encode `subject` and combine `title` + `text`.
4. **Date Handling**: Parse dates, extract year/month/day, and remove invalid entries.
5. **Feature Selection**: Drop `subject` due to label correlation; keep data from 2016–2017.
6. **Train/Test Split**: Split before text processing to avoid data leakage.
7. **Text Preprocessing**:
   - Lowercase, tokenize, remove stopwords/punctuation, lemmatize.
8. **Visualization**: Analyze label distribution and text lengths.

## Classical Machine learning models

| Modell               | Accuracy | Precision 0 / 1 | Recall 0 / 1 | F1 0 / 1    |
|----------------------|----------|-----------------|--------------|-------------|
| Logistic Regression  | 0.46     | 0.45 / 0.99     | 1.00 / 0.05  | 0.62 / 0.09 |
| Random Forest        | 0.71     | 0.60 / 1.00     | 1.00 / 0.48  | 0.75 / 0.65 |
| Naive Bayes          | 0.57     | 0.00 / 0.57     | 0.00 / 1.00  | 0.00 / 0.72 |
| Gradient Boosting    | 0.91     | 0.84 / 1.00     | 1.00 / 0.85  | 0.91 / 0.92 |
| XGBoost              | 0.99     | 0.97 / 1.00     | 1.00 / 0.98  | 0.98 / 0.99 |



### Evaluation
Simple models like **Logistic Regression** and **Naive Bayes** show very high precision for one class but very low recall for the other. This means they mostly predict one class well but miss many instances of the other, often due to class imbalance or limited complexity.

**Random Forest** improves recall and overall balance but with moderate accuracy.

**Gradient Boosting** significantly boosts accuracy and balances precision and recall better.

**XGBoost** achieves near-perfect accuracy and well-balanced metrics, making it the best model for this task.