# Project 3

## Preprocessing and data cleaning
1. **Load Data**: Read CSV and inspect structure.
2. **Initial Checks**: Identify missing values, empty fields, and duplicates.
3. **Clean Data**: Remove duplicates
4. **Train/Test Split**: Split before text processing to avoid data leakage.
5. **Text Preprocessing**: tokenize, remove stopwords/punctuation, lemmatize.
6. **Visualization**: Analyze label distribution and text lengths.

## Classical Machine learning models

| Model                | Accuracy | Precision 0 / 1 | Recall 0 / 1 | F1 0 / 1    |
|----------------------|----------|-----------------|--------------|-------------|
| Logistic Regression  | 0.904    | 0.87 / 0.95     | 0.95 / 0.86  | 0.91 / 0.90 |
| Random Forest        | 0.886    | 0.86 / 0.92     | 0.92 / 0.85  | 0.89 / 0.88 |
| Linear SVC           | 0.907    | 0.86 / 0.96     | 0.96 / 0.85  | 0.91 / 0.90 |
| Naive Bayes          | 0.878    | 0.81 / 0.98     | 0.98 / 0.78  | 0.89 / 0.87 |
| Gradient Boosting    | 0.792    | 0.84 / 0.76     | 0.71 / 0.88  | 0.77 / 0.81 |
| XGBoost              | 0.792    | 0.86 / 0.75     | 0.69 / 0.90  | 0.76 / 0.81 |

### Predictions on the "real" test data
| Model                 | Class 0 | Class 1 |
|-----------------------|---------|---------|
| Logistic Regression   | 4655    | 5329    |
| Random Forest         | 4890    | 5094    |
| Linear SVC            | 4739    | 5245    |
| Naive Bayes           | 4821    | 5163    |
| Gradient Boosting     | 3453    | 6531    |
| XGBoost               | 3237    | 6747    |


### Evaluation
Logistic Regression and Linear SVC both achieve an Accuracy of around 90.4% and 90.7% respectively and strong F1 scores of around 0.90-0.91 for both classes. They provide balanced precision (0.86-0.96) and recall (0.85-0.96), which shows that they recognize both positive and negative examples well.
<br /><br />
I suggest that the linear models capture the text patterns better.


## Deep learing with embeddigns

| Modell               | Accuracy | Precision 0 / 1 | Recall 0 / 1 | F1 0 / 1    |
|----------------------|----------|-----------------|--------------|-------------|
| Base Modell          | 0.949    | 0.949 / 0.950   | 0.948 / 0.951| 0.948 / 0.950|
| GloVe Embedding      | 0.919    | 0.942 / 0.899   | 0.890 / 0.947| 0.915 / 0.923|

### Predictions on the "real" test data

| Model         | Class 0 | Class 1 |
|---------------|---------|---------|
| Basic Model   | 7359    | 2625    |
| GloVe Model   | 9984    | 0       |


### Evaluation
The GloVe model is good on the labeled test set, but too cautious on real unlabeled data, because it does not estimate many samples strongly enough as class.

I currently have no explanation as to why the embedding models perform significantly worse than the classic machine learning models.
