# Bank-Telemarketing
Portfolio Machine Learning Classification

**Context**

The realm of banking encompasses everything related to banks, including their institutions, business activities, and the methods and processes involved in conducting their operations. In this context, "bank" refers to an entity that gathers funds from the public in the form of deposits and channels them to the public in the form of credit and other forms, aiming to improve the well-being of the general population. One of the strategies employed by banks to gather assets and liabilities is through deposit programs.

A deposit is a type of savings where withdrawals can only be made at specific times based on an agreement between the Depositor and the Bank. This deposit program involves a practice where funds gathered from the first set of customers are withheld for a specific period. These funds are then lent or credited to a second set of customers with an additional specified interest rate. After the agreement period expires, the funds are returned to the first set of customers with a specified interest rate. This practice is commonly known as "Spread based income," indicating the profit gained by banks through the process of fund gathering and distribution.

However, attracting potential depositors is not an easy task. It requires efforts to stimulate potential customers by highlighting the benefits they can gain by entrusting their funds to the bank. In addition to creating attractive programs, banks also need to establish effective marketing strategies to promote their deposit programs to potential customers.

Identifying potential depositors is also a challenge as not all potential customers are interested in making deposits. Targeting all bank customers through marketing efforts could lead to high costs, and there's no guarantee that all those targeted would be interested in deposits. Typically, only potential customers with sufficient funds, strong cash flows, and genuine interest would invest in deposits. This implies that while the cost might be significant, the conversion rate might not necessarily be high. Hence, banks need to strategically target potential customers to optimize marketing costs and maintain a consistently high conversion rate.


**Problem Statement**


**Problem Statement for Analytics**

What are the specific customer characteristics that should be included in the target marketing campaign for the deposit program to increase the volume of deposited assets?

**Problem Statement for Machine Learning**

How can we predict the likelihood of a customer making a deposit? This prediction is crucial to ensure that the bank's deposit campaign targets the right audience effectively.

The application of machine learning methods is essential to facilitate predictions, offer more quantifiable insights, and provide recommendations.


**Goals**

The goal is for the bank to identify the ideal customer characteristics for targeted marketing strategies and to predict the likelihood of a client making a deposit. This approach aims to make the bank's marketing efforts more efficient and precise, ultimately boosting revenue.


**Analytical Approach**

Our approach involves analyzing data to identify potential depositor groups and constructing a classification model. This model will aid the bank in predicting the probability that a customer will make a deposit.


**Metrics**

   1. Accuracy: in this context would measure the overall correctness of the model's predictions. It tells us how often the model correctly predicts both customers who will and will not make a deposit. However, if the dataset has imbalanced classes (more of one class than the other), high accuracy might be misleading as the model could simply predict the majority class.

   2. Recall: would be crucial to capture as many customers who will make a deposit as possible. A high recall means the model identifies most of the actual positive cases (customers who will make a deposit), which is essential to avoid missing out on potential revenue.

   3. Precision: is important to ensure that when the model predicts a customer will make a deposit, it's highly likely to be correct. A high precision indicates that customers predicted to make a deposit are more likely to actually do so, minimizing false positives.

   4. F1-Score: is a combination of Precision and Recall. It's useful when we need to strike a balance between identifying as many positive cases as possible (Recall) while ensuring that those predictions are accurate (Precision). It helps to assess the overall effectiveness of the model.

   5. ROC-AUC Curve: is a graphical representation of the trade-off between Sensitivity (Recall) and Specificity (1 - False Positive Rate). A model with a high ROC-AUC value indicates that it's effective in distinguishing between customers who will and will not make a deposit.

In summary, for this classification task, we want to maximize Recall to capture as many potential depositors as possible, while maintaining a reasonable level of Precision to avoid wasting resources on customers who are unlikely to make a deposit. The F1-Score provides a balanced view, and the ROC-AUC Curve gives insights into the overall discriminatory power of the model.

**Imbalance Dataset**
This dataset has imbalance dataset characteristics, because the label is dominated by one of the unique values, in column of the target, the proportion of unique value 'no' is very high compared to unique value 'yes'. In the machine learning stage, a treatment will be applied to overcome the imbalance problem in the dataset.

**Data Analytics**
* Customers who are still students and are under 26 years old and customers who are retired and aged 70 years and over tend to make deposits.
* Customers who have no study certificate tend to be dominant in making deposits.
* Single customers show higher deposit propensity compared to married or divorced individuals
* Homeowners and non-homeowners appear to have the same propensity to deposit.
* Customers who have loans and do not have loans appear to have the same tendency to deposit.
* Customers who are not defaulted tend to be more interested in depositing.
* The observed marketing technique has the highest number of customers who make deposits ranging from 1-4 contacts.
* It can be seen that if there is no contact before the campaign is carried out, the results show a dominant result in customers who make a deposit.
* Customers have a tendency to deposit if there is an interval of more than 25 days since the last contact.
* The proportion of depositor customers is more dominant if they were contacted using cellular.
* There are months that are the last month customers were contacted which have a proportion of customers who tend to deposit, these months in particular include March, September, October, and December.
* There are 14.22% of customers who made deposits even though the previous marketing campaign was considered a failure to make deposits. Meanwhile, there are 34.88% of customers who are considered successful in making deposits in the previous marketing campaign but are no longer depositing.

**Machine Learning Method**

The dataset has a considerable difference between the amount of data for class 1 and 0, since the model will easily predict class 0, thus giving a high accuracy value, therefore that the accuracy metric cannot be used as the main metric because in this case, but still used as an additional metric for model quality preservation. Instead we will prioritize the use of ROC-AUC metric as the ROC-AUC metric is a value obtained by taking into account the true positive rate (TP / TP + FN) and false positive rate (FP / FP + TN) where the selection of this metrics is very suitable for the imbalanced dataset. **The ROC-AUC score that is closer to 1 means that the model is getting better at distinguishing the class 1 (customer makes a deposit) and 0 (customer does not make a deposit).** For the metrics used in the classification report, there are precision, recall, and f1-score.

                precision    recall  f1-score   support

         0.0       0.98      0.89      0.93      7306
         1.0       0.49      0.82      0.61       928

    accuracy                           0.88      8234
    macro avg      0.73      0.86      0.77      8234
    weighted avg   0.92      0.88      0.90      8234
              
