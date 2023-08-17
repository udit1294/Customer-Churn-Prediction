
# Customer Churn Prediction

### **Did you know that attracting a new customer costs five times as much as keeping an existing one?**


![Gif_Merlim_Blogpost](https://user-images.githubusercontent.com/100334542/179733263-0e6e4e24-e0cf-4812-8f0f-5fbb32151d8b.gif)

## Introduction:

Churn prediction means detecting which customers are likely to leave a service or to cancel a subscription to a service. It is a critical prediction for many businesses because acquiring new clients often costs more than retaining existing ones. Once you can identify those customers that are at risk of cancelling, you should know exactly what marketing action to take for each individual customer to maximise the chances that the customer will remain.

Customer churn is defined as when customers or subscribers discontinue doing business with a firm or service.

Customers in the telecom industry can choose from a variety of service providers and actively switch from one to the next. The telecommunications business has an annual churn rate of 15-25 percent in this highly competitive market.

Individualized customer retention is tough because most firms have a large number of customers and can't afford to devote much time to each of them. The costs would be too great, outweighing the additional revenue. However, if a corporation could forecast which customers are likely to leave ahead of time, it could focus customer retention efforts only on these "high risk" clients. The ultimate goal is to expand its coverage area and retrieve more customers loyalty. The core to succeed in this market lies in the customer itself.

Customer churn is a critical metric because it is much less expensive to retain existing customers than it is to acquire new customers.

![image](https://user-images.githubusercontent.com/100334542/179732781-1a8d67e3-0ab7-4ef6-a9fd-1b0a74375fda.png)

#### To reduce customer churn, companies need to predict which customers are at high risk of churn.

To detect early signs of potential churn, one must first develop a holistic view of the customers and their interactions across numerous channels, including store/branch visits, product purchase histories, customer service calls, Web-based transactions, and social media interactions, to mention a few.

As a result, by addressing churn, these businesses may not only preserve their market position, but also grow and thrive. More customers they have in their network, the lower the cost of initiation and the larger the profit. As a result, the company's key focus for success is reducing client attrition and implementing effective retention strategy.

## Required Libaries

1.[Numpy](https://github.com/numpy/numpy)

2.[Pandas](https://github.com/pandas-dev/pandas)

3.[Matplotlib](https://github.com/matplotlib/matplotlib)

4.[Seaborn](https://github.com/mwaskom/seaborn)

5.[Sklearn](https://github.com/scikit-learn/scikit-learn)

6.[Tensorflow](https://github.com/tensorflow/tensorflow)

7.[Keras](https://github.com/keras-team/keras)

## Data 

I have used the Telco Customer Churn dataset which is available on [Kaggle](https://www.kaggle.com/datasets/blastchar/telco-customer-churn)

![Screenshot (26)](https://user-images.githubusercontent.com/100334542/179712733-df224eef-761a-4a4b-80e3-01f1432687ae.png)

### The data set includes information about:

**1.Customers who left within the last month** – the column is called Churn

**2.Services that each customer has signed up for** – phone, multiple lines, internet, online security, online backup, device protection, tech support, and streaming TV and movies

**3.Customer account information** - how long they’ve been a customer, contract, payment method, paperless billing, monthly charges, and total charges

**4.Demographic info about customers** – gender, age range, and if they have partners and dependents
        
#### The target the we will use to guide the exploration is Churn

### Visualize missing values

![image](https://user-images.githubusercontent.com/100334542/179708104-e924c011-8cff-4645-9b16-646a3c9a9d52.png)

**Using this matrix we can very quickly find the pattern of missingness in the dataset.**

From the above visualisation we can observe that it has no peculiar pattern that stands out. In fact there is no missing data.

##### But on deep analysis, we can find some indirect missingness in our data (which can be in form of blankspaces) more particularly in the 'TotalCharges' column. 

                     df2=df[df.TotalCharges == ' ']
                     df2.shape
                     
 Writting this peice of code we can see that there are 11 missing values(blankspace) present in the TotalCharges column.
 
It can also be noted that the Tenure column is 0 for these entries even though the MonthlyCharges column is not empty.
 
 ![Screenshot (24)](https://user-images.githubusercontent.com/100334542/179711888-d5c22069-16c3-40c8-b026-d3514713fc1c.png)
 
 ## **Columns values**

![image](https://user-images.githubusercontent.com/100334542/203642907-325ee45f-5ae8-4ab9-8548-2fed07cf13b1.png)


## **Data Visualization**

![Screenshot (28)](https://user-images.githubusercontent.com/100334542/179717695-101c50fe-8363-43ec-b103-41384ee67790.png)

1)26.6 % of customers switched to another firm.

2)Customers are 49.5 % female and 50.5 % male.

**There is negligible difference in customer percentage/ count who chnaged the service provider. Both genders behaved in similar fashion when it comes to migrating to another service provider/firm.**

![Screenshot (30)](https://user-images.githubusercontent.com/100334542/179720151-e64f36d8-b1c6-4374-98a3-4d21e43e9af9.png)

**About 75% of customer with Month-to-Month Contract opted to move out as compared to 13% of customrs with One Year Contract and 3% with Two Year Contract.**

![Screenshot (32)](https://user-images.githubusercontent.com/100334542/179721540-dbbb7b6b-227d-46fe-8d5b-37af2ffc2284.png)

![newplot](https://user-images.githubusercontent.com/100334542/179721784-840cc1f2-5d5d-4d6e-80f2-cd52e1a74884.png)

**1.Major customers who moved out were having Electronic Check as Payment Method.

2.Customers who opted for Credit-Card automatic transfer or Bank Automatic Transfer and Mailed Check as Payment Method were less likely to move out.**

![newplot (1)](https://user-images.githubusercontent.com/100334542/179723497-250aba85-c5f3-4b52-926f-04d7cf889526.png)

**1)A lot of customers choose the Fiber optic service and it's also evident that the customers who use Fiber optic have high churn rate, this might suggest a dissatisfaction with this type of internet service.

2)Customers having DSL service are majority in number and have less churn rate compared to Fibre optic service.**

![newplot (2)](https://user-images.githubusercontent.com/100334542/179724626-f5578a72-5212-4466-b415-287030464efa.png)

![newplot (3)](https://user-images.githubusercontent.com/100334542/179724761-695e202d-41aa-4e4f-ae5a-94e593db0348.png)

**Customers without dependents are more likely to churn**

**Customers that doesn't have partners are more likely to churn**

![image](https://user-images.githubusercontent.com/100334542/179725120-20fc13be-4a40-4052-b8c4-9794d37bbace.png)

**It can be observed that the fraction of senior citizen is very less.Most of the senior citizens churn.**

![newplot (4)](https://user-images.githubusercontent.com/100334542/179725455-172774f8-651a-42db-986f-d7a71f92f9ad.png)

**Most customers churn in the absence of online security.**

![newplot (5)](https://user-images.githubusercontent.com/100334542/179726540-8ab17fe2-4b2d-4ce1-92ea-1e08768897f5.png)

**Customers with Paperless Billing are most likely to churn.**

![newplot (6)](https://user-images.githubusercontent.com/100334542/179726770-646d51cb-1cf1-4803-b1a0-63d391b05ba2.png)

**Customers with no TechSupport are most likely to migrate to another service provider.**

![newplot (7)](https://user-images.githubusercontent.com/100334542/179727000-6992b217-44eb-4df9-9468-e859be73164a.png)

**Very small fraction of customers don't have a phone service and out of that, 1/3rd Customers are more likely to churn.**

![image](https://user-images.githubusercontent.com/100334542/176259561-1ba497de-a6ed-4b0b-9f35-d9faea1822c9.png)

**Customers with higher Monthly Charges are also more likely to churn**

![image](https://user-images.githubusercontent.com/100334542/179727769-ac05cb3d-a853-41ce-b90b-85d9c813c0c3.png)

**New customers are more likely to churn**

### Get Correlation of "Churn" with other variables

![correlation (1)](https://user-images.githubusercontent.com/100334542/179714703-8390ace4-3acd-49b3-a4e1-e693b322a367.png)

Month to month contracts, absence of online security and tech support seem to be positively correlated with churn. While, tenure, two year contracts seem to be negatively correlated with churn.

Interestingly, services such as Online security, streaming TV, online backup, tech support, etc. without internet connection seem to be negatively related to churn.

We will explore the patterns for the above correlations below before we delve into modelling and identifying the important variables.

# Machine Learning Model Evaluations and Predictions

![image](https://user-images.githubusercontent.com/100334542/179732513-ce27afac-f612-4867-9af1-1b996af05ee9.png)


##Accuracy of the model using variouus model

Logistic Regression Test Accuracy: 0.8038379530916845

Decission Tree Test Accuracy: 0.7149964463397299

Random Forest Test Accuracy: 0.7853589196872779

Naive_Bayes Test Accuracy: 0.7420042643923241

KNN Test Accuracy: 0.7654584221748401

SVM 👉👉👉👉 0.8045486851457001

ANN 👉👉👉👉 0.78

## Conclusion

Customer churn is definitely bad to a firm ’s profitability. Various strategies can be implemented to eliminate customer churn. The best way to avoid customer churn is for a company to truly know its customers. This includes identifying customers who are at risk of churning and working to improve their satisfaction. Improving customer service is, of course, at the top of the priority for tackling this issue. Building customer loyalty through relevant experiences and specialized service is another strategy to reduce customer churn. Some firms survey customers who have already churned to understand their reasons for leaving in order to adopt a proactive approach to avoiding future customer churn.

