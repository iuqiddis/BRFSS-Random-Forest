# Using Random Forest Classificaiton to Predict Good or Poor Health Based on the Behavioral Risk Factor Surveillance System Survey

### Introduction

The Behavioral Risk Factor Surveillance System (BRFSS) is an annual health-related telephone survey conducted by the United States' Centers for Disease Control and Prevention (CDC) regarding their health-related risk behaviors, chronic health conditions, and use of preventive services [[CDC's BRFSS site](https://www.cdc.gov/brfss/index.html)].

The resultant public domain Real World Data (RWD) are readily avaliable via the [CDC's site](https://www.cdc.gov/brfss/data_documentation/index.htm). The datasets typically consist of appromixtely 300,000 to 400,000 surveyed individuals, with about 250 to 350 variables (mapping to asked behavioral questions or calculated variables).

**Goal**: The goal for this data project is to to use one of the annual BRFSS datasets to make a *predictive classification model* to determine whether a subject would be categorized in 'Good or Better' health or 'Fair or Poor' health based on the survey findings.

### Methods

**Data Used**: I downloaded the the BRFSS data for 2015. Instead of directly downloading the data in ASCII or SAS format from the CDC site, I used the [CSV file generated from Kaggle](https://www.kaggle.com/cdc/behavioral-risk-factor-surveillance-system). They generated the CSV file after importing the SAS data using Pandas. This seemed to be the better approach than starting from scratch as my goal for this project is to focus on the modeling rather than extraction and transformation. As the dataset consists of several hundred features with some arcane variable names, the 2015 BRFSS Codebook is essential to understand their meaning and importance ([link to Codebook PDF here](https://www.cdc.gov/brfss/annual_data/2015/pdf/codebook15_llcp.pdf)).

**Modeling**: I'll start by using a Decision Tree Classifier that fits the data into the 'Good or Better' or 'Fair or Poor' Health classes. The benefit of this is the ease of understanding and interpreting the original data. However, the disadvantage of the approach is that the a decision tree overfits to the training data, and as such is not a robust predictive model.

After developing some intuition of the data, I'll implement a Random Forest Classifier, which uses bagging and forests (ensemble of mulitple decision trees), to generate a robust model with lower variance.

Lastly, I'll use cross validation to to optimize the hyperparameters for improved prediction while further minimizing overfitting and selection bias.

**Scoring:** A number of scoring methods can be used to assess model robustness. Some of these include accuracy, precision and recall, and the reciever operator characterestic. As I'll explore the data, I'll make and explain the choices for the scoring method I used.
