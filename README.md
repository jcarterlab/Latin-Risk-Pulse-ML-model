# Latin-Risk-Pulse-ML-model

Latin Risk Pulse is a project seeking to better understand Latin American political, security and economic risks. This repository takes the first step in that direction by training a machine learning model to determine whether or not Latin American headlines (in Spanish & Portuguese) represent a potential risk.

## The data 🛢
The data was collected by scraping the headlines of online news sources in Latin America. The texts were then put through a keyword matching process before being fed to Google Gemini for labelling. The risk labels include political stability risks, security and violence risks, and economic and regulatory risks.

## 01: Data exploration 🔍
The data shows a few imbalances, most notably in the risk vs non-risk classes.  
[See notebook.](Notebooks/01_data_exploration.ipynb)


![Data exploration](Images/data_exploration_1_risk_vs_non_risk.png)

## 02: Baseline model 🏁
A TF-IDF logistic regression baseline model shows extremely low performance on risk headline recall, the main objective of this repository. This is likely the result of false negatives in the data.  
[See notebook.](Notebooks/02_tfidf_baseline.ipynb)

## 03: Improve labels 🏷️
By training a model an half of the data at a time and using it to predict the other half's non-risk headlines, many false negatives can be removed from the data and the risk headline recall improved.  
[See notebook.](Notebooks/03_improve_label_quality.ipynb)
