**Author**:[Russell Pihlstrom](mailto:rgpihlstrom@yahoo.com)

<img src="https://github.com/rgpihlstrom/Project3/blob/main/images/TitlePic.png" width="600" height="400" />

## Overview

This project uses Decision Tree and RandomForestClassifier supervised learning methods to classify the churn behavior of Telco's customer base.  By analyzing past actual churn vs. no churn behavior along with the respective customer attributes associated with each type of behavior, I developed a model that detected <b><ins>81%</ins></b> of Telco's churning customers.  The developed algorithm, “model”, can be used to predict the future churn vs. no churn behavior with the intent of identifying and preventing future customer flight.  The following 5 features were most predictive of churn: <strong>Month to Month Contract, Customer Tenure, Fiber Optics Internet Service, and Monthly Charges.</strong>


## Business Problem
Customer retention is a serious concern for all companies.  However, within the Telecommunications industry customer churn is of particular importance.  Fierce competition, along with a difficult to differentiate product offering, makes retaining customers, on factors beyond price, almost impossible.  Therefore, the historically thin profits margins of the past are only getting thinner.  In fact, a case study done by the Bain Company on the Telecom industry suggested a 5% increase in customer retention can lead to an increase in profits by 25%-95% percent (https://www.bain.com/client-results/focus-on-customer-engagement-to-improve-retention/).

<br>

### The Current Situation: Telco is Losing 27% of Customers, 31% of Revenue to Churn.


<img src="https://github.com/rgpihlstrom/Project3/blob/main/images/TelcoChurnrates.png" width="600" height="400" />
<br>

## Data
The data used for this project was provided Telco and published and manage by Kaggle and served as a basis for past Kaggle competitions (Telco Customer Churn https://www.kaggle.com/blastchar/telco-customer-churn)  The dataset contains approximately 8k rows and 21 features capturing the purchase, usage, and tenure information on a subset of Telcos customers.  17 of the features are categorical, 3 are continuous, and 1 is ID.  A list of features contained within the data are below.
<br><br>
<img src="https://github.com/rgpihlstrom/Project3/blob/main/images/Columns.png" />

## Model Development Methods
This project uses the Crisp DM methodology to generate and optimize model development.  The intended output of this theoretical business case is focused on helping Telco's CEO, and Marketing leadership do the following:
-   **1. Identify Features Most Associated with Churn.**
-   **2. Evaluate Telco's Current offerings Ability to Prevent Churn.**
-   **3. Identify Areas for Potential Innovation.**
<Br>
Furthermore, the model was developed for the purpose of reuse to identify and potentially prevent future customer churn for Telco.

As prescribed by the Crisp DM methodology, model development was very iterative.  I began by doing secondary research around the basic business drivers of the Telecom industry, gaining a better understanding on the prevalence of churn and the costs associated with fleeing customers.  Along with the project requirements noted above the following additional factors were considered during the modeling process:
-   **1. Data Imbalance**  Early in the development process it was obvious that I was dealing with an imbalanced set of data (more information/ rows of data on non-churn customer vs. churn costomers).  To ensure optimum identification my processes/ modeling would need to account for this imbalance.  I addressed this gap by first attempting the model using different weights and ultimately decided to do SMOTE(Synthetic Minority Oversampling Technique) to overcome this challenge.

- **2. Selection of Supervised Learning Classifiers**  Initially I tried several different types of classifiers, ranging from Logistic Regression, Naive Bayes, Gradient Boost, Ada, and XGBoost.  Ultimately, I decided to use <b><ins>Knn, Decision Trees and Random Forest</ins></b> , as these classifiers are non-parametric and are highly interpretable.  Interpretability, the disproportionate number of categorical features, along with being able to avoid addressing multicollinearity were the most influential factors in selecting which classifiers to select for this project.

-   **3. Business Drivers: Churn Detection > False Alarms**  Recommendations on model development was based on secondary research along with working knowledge on the disparity between the cost to acquire vs the cost to retain customers.  In this hypothetical scenario, the CEO of Telco has asked me to place a particular focus on detection at the potential expense of unnecessary outreach activities.

<img src="https://github.com/rgpihlstrom/Project3/blob/main/images/ChurnOverFalseAlarms.png" width="600" height="400" />


## Model Results (PO ONLY - need to insert real results)
After several iterations the below recall, accuracy, precision, and AUC scores were achieved for the selected classifiers used to predict churn.  Based on these results I decided to move forward with the Random Forest Classifier.
<br/>
<img src="https://github.com/rgpihlstrom/Project3/blob/main/images/ROC.PNG" width="600" height="400" />
<br/>

## Business Results/ Recommendations
As stated above the goal of the project was three fold.  I have outlined and summarized results below

- **1. Top Features Associated with Non Churn vs. Churn:** 
<img src="https://github.com/rgpihlstrom/Project3/blob/main/images/MostImportantFeatures1.png" />

### Observations:
- Type of Contract – 89% of churning customers are in Month-to-Month Contracts.
- Months with Telco – 75% of churn is occurring within 29 months of becoming a customer. 
- Type of Internet Service – 66% of churners are participating in our Fiber Optics internet service.
- Monthly Bill – Median monthly bill for churners is 25% higher than non-churners.

Together these factors were identified by the model as 5 most predictive of churn.


- **2. Current Features/ Services Ability to Prevent Churn:** 
<img src="https://github.com/rgpihlstrom/Project3/blob/main/images/CountofEnrolledServices.png" height="200"/>

### Observations:
- Count of Services Enrolled – 66% of churners are enrolled in 3 or more services.
Given this number is greater than 50%, I would deem that the services are not adequately helping to prevent customer churn.


- **3. Opportunities for Innovation:** 
<img src="https://github.com/rgpihlstrom/Project3/blob/main/images/Innovation2.png" />

### Observations:
My recommendations for innovation is focused on working to create addition solutions around the 5 most predictive features associated with churn which were noted above in point #1.
- Increasing Months with Telco - Examine ideas for Innovation around loyalty programs to incent longevity
- Reducing Monthly Spend -  Examine innovation around bundling services in an attempt to lower monthly spend 
- Type of contract – Obviously, the here goal is to reduce spontaneous churn.  If churn customers are not interested in the 1 year or a 2 year contract, perhaps there is a shorter term contract that can be created.  Perhaps try 6 months or quarterly contracts.  
- Type of internet service -  Given the big difference in rate of churn across DSL vs. Fiber Optics churners, I believe there is something obviously wrong.  My recommendation is to engage in a competitive and or quality analysis to ensure the quality of the fiber optics lines are meeting customer expectations.


## Potential Impact on Revenue
<img src="https://github.com/rgpihlstrom/Project3/blob/main/images/RevenueRamifications1.png" width="600" height="400"/>

### Observations:
- Today Telco experiences 27% customer churn rate which = 31% lost revenue.
- Given the <b>81% churn detection rate</b>, Telco has an opportunity to reduce its churn to as little as 5% (for illustration purposes assuming 100% churn reversal).  The result of detecting and reversing the 81% of the historical rate of churn would result in a saving of 25% in revenue.

## Next Steps

- **Optimize Current Model - (Look To Reduce Overfitting)** - As shown above the gap between the accuracy of the model using the training dataset vs. the testing dataset was wider than optimal.  Therefore, additional analysis is required to try to narrow this gap within 1 or 2% difference between accuracy scores.
- **Examine Detection vs. False Alarm Tradeoffs** - Given the high cost of customer acquisition vs. customer retention some additional analysis may reveal lowering our threshold from 50% to perhaps 40% would capture additional undetected churners.  Capturing additional risk of high-risk flight customers could result in additional improvements in retained revenue. 
- **Examine Additional Classifiers** - For this project I settled on Random Forest, however, given advances in classifiers such as extreme boost and others, there may be additional opportunities to improve our churn detection rates.
- **Put Model(s) Into Productions** - Once we have optimized our models and/or generated enough models to account for the wide variety of churn data I would look to automate and deploy the models via a web-based interface and make it available to the marketing and or customer service teams.


## For More Information

See the full analysis in the [Jupyter Notebooks](folder) or review our <a href="https://github.com/rgpihlstrom/Phase2Project/blob/main/Presentation.pdf">Presentation</a>.

For additional info, contact me here: [ Russell Pihlstrom](mailto:rgpihlstrom@yahoo.com)
