# Work in progress 🚧
# Bank Marketing Analysis

The data is related with direct marketing campaigns (phone calls) of a Portuguese banking institution. The classification goal is to predict if the client will subscribe to a term deposit.

## Credit
S. Moro, P. Rita, and P. Cortez. "Bank Marketing," UCI Machine Learning Repository, 2014. [Online]. Available: https://doi.org/10.24432/C5K306.


## Analysis 

#todo
discuss variable names

---

Handling Class Imbalance in subscribed

The target variable (subscribed) is highly imbalanced, with 89% no and 11% yes. This imbalance can lead to biased model performance, as the model may simply predict no for all cases to achieve high accuracy.

- Oversampling: Increase the number of minority class samples (yes) using techniques like SMOTE (Synthetic Minority Oversampling Technique).
- Undersampling: Reduce the number of majority class samples (no) to balance the dataset.
- Combination: Use a combination of oversampling and undersampling.
- Assign higher weights to the minority class during model training to penalize misclassifications of the minority class more heavily.

Use metrics like precision, recall, F1-score, and ROC-AUC instead of accuracy, as they are more informative for imbalanced datasets.

---

Economic and Social Context

- emp.var.rate (Employment Variation Rate):
  - Description: This is the employment variation rate, which measures the quarterly change in employment. It reflects the stability or volatility of the job market.
  - Interpretation: A higher value indicates more volatility in employment, while a lower value suggests stability.
- cons.price.idx (Consumer Price Index):
  - Description: This is the consumer price index (CPI), which measures the average change in prices over time that consumers pay for a basket of goods and services.
  - Interpretation: A higher CPI indicates inflation (rising prices), while a lower CPI suggests deflation (falling prices).
- cons.conf.idx (Consumer Confidence Index):
  - Description: This is the consumer confidence index, which measures the degree of optimism or pessimism that consumers feel about the overall state of the economy and their personal financial situation.
  - Interpretation: A higher value indicates greater consumer confidence, while a lower value suggests lower confidence.
- euribor3m (3-Month Euribor Rate):
  - Description: This is the 3-month Euribor rate, which is the average interest rate at which European banks lend to one another for a 3-month period.
  - Interpretation: A higher Euribor rate indicates higher borrowing costs, while a lower rate suggests cheaper borrowing.
- nr.employed (Number of Employees):
  - Description: This is the number of employees, which reflects the size of the workforce or the number of people employed in the economy.
  - Interpretation: A higher value indicates a larger workforce, while a lower value suggests fewer people employed.

A high consumer confidence index might indicate that people are more likely to invest in term deposits.
A low Euribor rate might make borrowing cheaper, potentially reducing the appeal of term deposits.
A high employment variation rate might indicate economic instability, which could influence financial decisions.

---

Numerical Features

- age:
Slight differences in age distribution between subscribers and non-subscribers.
Subscribers had a larger IQR, indicating a slightly wider age range.
- duration:
Longer call durations correlate with higher subscription rates.
Outliers suggest some very long calls for both groups.
- campaign:
Fewer campaign interactions correlate with higher subscription rates.
Non-subscribers had many outliers with a high number of interactions.
- pdays:
No significant impact on subscription rates.
Most values are clustered around 1000 days, with outliers near 0.
- euribor_3month_rate:
Lower Euribor rates correlate with higher subscription rates.
Non-subscribers had a higher IQR and upward skew.
- number_of_employees:
Lower but wider IQR for subscribers.
Non-subscribers had a tiny IQR range (~4900 to ~5300), suggesting limited impact.

Categorical Features

- default:
Individuals who have not defaulted are significantly more likely to subscribe.
Almost no subscribers had a prior default.
- loan:
Individuals without loans are more likely to subscribe.
Very few subscribers had existing loans.
- contact:
Most subscriptions came from cellular contacts.
Telephone contacts had a much smaller subscription rate.
- poutcome:
Most subscribers were in the "nonexistent" group (no prior outcome).

---
