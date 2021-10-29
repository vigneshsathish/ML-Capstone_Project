# Trip Pricing with taxi mobility analytics
This Capstone project was done as a part of my data science course. I like to thank my mentor MS.Vibha santhanam and  my teammates Abhijith S Varma, G.Siva kumar, M.vignesh ,V.Ram prakash for their valuable contributions during the course of this project.

![image](https://user-images.githubusercontent.com/82166286/132977324-04d6a452-847d-4bf4-b5cf-9bff25f746d0.png)

# Business Problem
"Surge pricing" occurs when a company raises the price of its product or service if there is an increase in demand - and lowers prices when demand is weak.Surge pricing only really works when the demand for a service is immediate. For some, “surge pricing,” the use of algorithms to automate price increases on products and services in periods of high demand and limited supply, adheres to a basic principle of the free market economy.

This can happen due to the following factors:</br>
Special events</br>
Rush hour</br>
Bad weather</br>

# Project Statement
We are predicting the surge price type for Sigma Cabs. Previously surge price was given by service providers,from that information they have captured surge price type,we are building a predictive model based on that surge price type, so that they can fix the fare beforehand.We are helping the client to became a cab aggregator.

# Dataset Description
Dataset Link: https://www.kaggle.com/arashnic/taxi-pricing-with-mobility-analytics

## VARIABLE CATEGORIZATION:</br>
No of rows: 131662  
Total Features/Columns :14</br>
Numerical Features :06</br>
Categorical Features:08</br>
Target : Surge Pricing Type(Multiclassification)  


# Complexity Involved
1.The company needs to keep confidentiality , as a result of this there are 3 masked variables(VAR1,VAR2,VAR3) generated by the company. </br>
2.The challenge we faced is model is able to predict the surge type but type 1 ,type 2 and type 3 is not defined so based on EDA,we assumed that Type 1 is of high price, Type 2 is of low price and type 3 is of medium price.

# Exploratory Data Analysis
## Data Preprocessing
![image](https://user-images.githubusercontent.com/82166286/132978094-6c27b691-51cd-48a4-a337-7efe4bedf6e0.png)

# Inference based on Tableau Analysis
Based on analysis from Tableau we came to conclusion surge_type_1 price is high,surge_type_2 price is low and surge_type_3 price is medium </br>
![image](https://user-images.githubusercontent.com/82166286/132978179-4861080b-3ec2-4297-a27b-8633aa245058.png)

# Statistical Data Analysis - MULTICLASSIFICATION TARGET
# **ANOVA TEST - Target and Numerical variables**
# HYPOTHESIS TEST 
Ho : All means are equal ( No relation) </br>
Ha : Atleast one mean is not equal ( Relation) </br>
1. Since our target variable is category and to find whether the feature is significant or not, we did a oneway-anova test to find out the significance of the feature.</br>
2. At 95% confidence level </br>
   Pval<0.05</br>
  "Ha is accepted"</br>
   TRIP_DISTANCE,LIFE_STYLE_INDEX,CUSTOMER_RATING,VAR2,VAR3 ARE SIGNIFICANT WITH TARGET SURGE_TYPE_PRICING

# **CHI SQUARE TEST FOR INDEPENDNCE - Target and categorical variable**
1.The Chi-Square test of independence is used to determine if there is a significant relationship between two nominal (categorical) variables
# HYPOTHESIS TEST:
Ho : Independant (NO relation)</br>
Ha : Not independant (Relation)</br>
</br>
   CATEGORY                    PVALUE  </br>
TYPE OF CAB                 : 0.0  </br>
GENDER                      : 0.26289162562835167  #  pval >0.05 (NOT SIGNIFICANT) </br>
CONFIDENCE_LIFE_STYLE_INDEX : 0.0 </br>
DESTINATION TYPE            : 0.0 </br>
CANCELLATION LAST MONTH     : 0.0 </br>
CUSTOMER_SINCE_MONTHS       : 3.814026989771444e-19 </br>

1. At 95% confidence level </br>
   Pval<=0.05</br>
  "Ha is accepted"</br>
  TYPE OF CAB ,CONFIDENCE_LIFE_STYLE_INDEX,DESTINATION TYPE,CANCELLATION LAST MONTH,CUSTOMER_SINCE_MONTHS  ARE SIGNIFICANT WITH TARGET SURGE_TYPE_PRICING

# ANOVA TEST FOR LINEAR OR NON LINEAR MODELS
# HYPOTHESIS TEST
Ho : All means are equal</br>
Ha : Atleast one mean is not equal</br>

![image](https://user-images.githubusercontent.com/82166286/132978968-83deeb06-3f0d-4d5c-9d1e-1668ce803ecb.png)</br>
 We can see from Plot that within the group and between the group means are almost equal.There is an overlap it is diffcult to predict by means of linear models. so we are going for tree based models.

# Evaluation metric
F1-Weighted score was chosen as a metric of the models.

# Model Comparision
![image](https://user-images.githubusercontent.com/82166286/132981259-2842decd-240f-4eaa-9054-83e8594a2105.png)</br>
KNN model is the Base model </br>
Random Forest model is the Final Model. F1- weighted score increased and bias error reduced.</br>

# Model Deployment
Pickled the best model Random Forest using pickle.dump.</br>
Front end used HTML,CSS.</br>
Backend used Flask.</br>
Hosting in local storage.</br>
Deployment 

# Fututre scope:
We will ask to the client for more information regarding the price, Traffic level at the time of the trip.</br>
We will use more advanced modelling techniques in order to make the prediction more accurate.
 
# Conclusion
We got exposure real world data and its implications.</br>
We learnt about the process of cab aggregation.</br>
We learnt about the Simple imputer library in sklearn.</br>
After doing in depth analysis in Tableau, we learned more about the target variable which is surge pricing type.</br>


