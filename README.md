# Latin-Risk-Pulse-ML-model

The Latin Risk Pulse is project seeking to better understand Latin American political, security and economic risks. This repository takes the first step on that journey by training a machine learning model to determine whether or not Latin American headlines represent one of these potential risks.

## The data 🛢
The data was collected by scraping the headlines of online news sources in Latin America. The texts were then put through a keyword matching process before being fed to Google Gemini for labelling. The risk labels include political stability risks, security and violence risks, and economic and regulatory risks.


## 01: Data exploration 🔍
The data shows a few imbalances, most notably in the class labels of risk vs non-risk. 


![Data exploration](Images/data_exploration_1_risk_vs_non_risk.png)


## 02: Baseline model - TF-IDF 
