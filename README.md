# Detecting Deception: Machine Learning Approaches to Credit Card Fraud Identification

## Overview

Credit card fraud is a major global challenge that affects individuals and financial 
institutions worldwide, costing billions of dollars annually and posing significant security 
risks to the public. Credit card fraud occurs when an attacker uses a victim’s existing credit 
card information and personal data to create fraudulent accounts or perform unauthorized 
transactions. Using stolen information, perpetrators can open multiple new accounts, 
further contributing to large-scale data breaches. Although fraudulent transactions 
represent only a small fraction of overall credit card activity, they are difficult to detect due 
to their evolving nature. As fraud techniques continue to advance, detection models must 
be regularly updated to remain effective. 

Download Dataset here!: https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud?utm_source=chatgpt.com&select=creditcard.csv


## Dataset

The dataset used in this project is the **Credit Card Fraud Detection** dataset available on Kaggle. It consists of **284,807 transactions** with **31 features**, including:

* `Time`: Time elapsed between transactions
* `Amount`: Transaction amount
* `Class`: Target variable (0 = legitimate, 1 = fraudulent)
* 28 anonymized numerical features generated using PCA

Only a small percentage of transactions (approximately 2%) are fraudulent, making this a severely imbalanced classification problem.



## Methods

### Logistic Regression

Logistic regression is a supervised learning algorithm commonly used for binary classification problems. It estimates the probability that a transaction belongs to a particular class using the sigmoid function. In this project, logistic regression serves as a baseline model for fraud detection.

### Random Forest

Random forest is an ensemble learning algorithm that combines multiple decision trees to improve predictive performance and reduce overfitting. Due to its ability to model non-linear relationships and handle high-dimensional data, random forest is well-suited for fraud detection tasks. However, careful evaluation is required when working with imbalanced data.



## Preprocessing

* Checked for missing and duplicate values (none found)
* Applied standard scaling to `Time` and `Amount` features
* Preserved class imbalance during an 80/20 train-test split



## Evaluation Metrics

Because standard accuracy can be misleading for imbalanced datasets, the following metrics were used:

* Precision
* Recall
* F1-score
* ROC-AUC
* Precision–Recall AUC

Precision–Recall curves were used to better evaluate model performance on the minority (fraudulent) class.



## Results

* **Logistic Regression** achieved high overall accuracy but struggled with recall for fraudulent transactions.
* **Random Forest** demonstrated improved recall and precision, making it more effective at detecting fraud in an imbalanced dataset.

### Precision–Recall Curve

The precision–recall curve shows that the random forest model maintains higher precision across a larger range of recall values compared to logistic regression, reinforcing its superiority in identifying fraudulent transactions.



## Conclusion

This project demonstrates the importance of proper preprocessing, metric selection, and model choice when addressing imbalanced classification problems. Ensemble-based models such as random forest outperform simpler linear models in capturing complex fraud patterns. The findings highlight real-world best practices for applying machine learning to financial fraud detection.



## References 

Experian. “Credit Card Fraud: What to Do If You Are a Victim.” *Experian*, n.d., [www.experian.com/blogs/ask-experian/credit-education/preventing-fraud/credit-card-fraud-what-to-do-if-you-are-a-victim/](http://www.experian.com/blogs/ask-experian/credit-education/preventing-fraud/credit-card-fraud-what-to-do-if-you-are-a-victim/). Accessed 7 Dec. 2025.

GeeksforGeeks. “Random Forest Regression in Python.” *GeeksforGeeks*, n.d., [www.geeksforgeeks.org/machine-learning/random-forest-regression-in-python/](http://www.geeksforgeeks.org/machine-learning/random-forest-regression-in-python/). Accessed 7 Dec. 2025.

GeeksforGeeks. “Understanding Logistic Regression.” *GeeksforGeeks*, n.d., [www.geeksforgeeks.org/machine-learning/understanding-logistic-regression/](http://www.geeksforgeeks.org/machine-learning/understanding-logistic-regression/). Accessed 7 Dec. 2025.
