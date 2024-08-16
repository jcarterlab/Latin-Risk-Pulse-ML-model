# Latin-Risk-Pulse-ML-model

Latin Risk Pulse is a project seeking to better understand Latin American political, security and economic risks. This repository trains a machine learning model to determine whether or not Latin American headlines (in Spanish & Portuguese) represent a potential risk in any of these domains. To date there are approximately 100 thousand headlines.

## The data 🛢
The data was collected by scraping the headlines of online news sources in Latin America. The texts were then put through a keyword matching process before being fed to Google Gemini for labelling. The risk labels include political stability risks, security and violence risks, and economic and regulatory risks.

<br>

## 01: Data exploration 🔍
The data shows a few imbalances, most notably in the risk vs non-risk classes.  
[See notebook.](Notebooks/01_data_exploration.ipynb)


![Data exploration](Images/data_exploration_1_risk_vs_non_risk.png)

<br>

## 02: Baseline model 🏁
A TF-IDF logistic regression baseline model shows extremely low performance on risk headline recall, the main objective of this model. This is likely the result of false negatives in the data.  
[See notebook.](Notebooks/02_tfidf_baseline.ipynb)

#### Spanish

<pre>
               precision    recall  f1-score   support

           0       0.92      0.99     0.95     13235
           1       0.84      0.44     0.58      2039

    accuracy                           0.91     15274
   macro avg       0.88      0.71      0.76     15274
weighted avg       0.91      0.91      0.90     15274
</pre>

#### Portuguese

<pre>
               precision    recall  f1-score   support

           0       0.84      0.98      0.91      2558
           1       0.83      0.38      0.52       751

    accuracy                           0.84      3309
   macro avg       0.84      0.68      0.71      3309
weighted avg       0.84      0.84      0.82      3309
</pre>

<br>

## 03: Improve labels 🏷️
By training a model an half of the data at a time and using it to predict the other half's non-risk headlines, many false negatives can be removed, dramatically improving risk headline recall.  
[See notebook.](Notebooks/03_improve_label_quality.ipynb)

#### Spanish

<pre>
               precision    recall  f1-score   support

           0       0.98      0.75      0.85      5291
           1       0.36      0.92      0.52       818

    accuracy                           0.77      6109
   macro avg       0.67      0.84      0.69      6109
weighted avg       0.90      0.77      0.81      6109
</pre>

#### Portuguese

<pre>
               precision    recall  f1-score   support

           0       0.95      0.65      0.77      1032
           1       0.42      0.88      0.56       291

    accuracy                           0.70      1323
   macro avg       0.68      0.77      0.67      1323
weighted avg       0.83      0.70      0.73      1323
</pre>

<br>

## 04: Balance risk types ⚖️
Balancing the risk types in the risk headline class leads to...

