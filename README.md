**Author**:[Russell Pihlstrom](mailto:rgpihlstrom@yahoo.com)
![TElcoTitle](/images/TitlePic.png)


## Overview

This project uses Decision Tree and RandomForestClassifier supervised learning methods to classify the churn behavior of Telco's customer base.  By analyzing past actual churn vs. no churn behavior along with the respective customer attributes associated with each type of behavior, I developed a model that detected <b><ins>81%</ins></b> of Telco's churning customers.  The developed algorithm, “model”, can be used to predict the future churn vs. no churn behavior with the intent of identifying and preventing future customer flight.  The following 5 features were most predictive of churn: <strong>Month to Month Contract, Customer Tenure, Fiber Optics Internet Service, and Monthly Charges.</strong>


## Business Problem
Customer retention is a serious concern for all companies.  However, within the Telecommunications industry customer churn is of particular importance.  Fierce competition, along with a difficult to differentiate product offering, makes retaining customers, on factors beyond price, almost impossible.  Therefore, the historically thin profits margins of the past are only getting thinner.  In fact, a case study done by the Bain Company on the Telecom industry suggested a 5% increase in customer retention can lead to an increase in profits by 25%-95% percent (https://www.bain.com/client-results/focus-on-customer-engagement-to-improve-retention/).

<br>

### The Current Situation: Telcos Losing 27% of Customers, 31% of Revenue to Churn.


<img src="https://github.com/rgpihlstrom/Project3/blob/main/images/TelcoChurnrates.png" width="600" height="400" />
<br>

## Data
The data used for this project was provided Telco and published and manage by Kaggle and served as a basis for past Kaggle competitions (Telco Customer Churn https://www.kaggle.com/blastchar/telco-customer-churn)  The dataset contains approximately 8k rows and 21 features capturing the purchase, usage, and tenure information on a subset of Telcos customers.  17 of the features are categorical, 3 are continuous, and 1 is ID.  A list of features contained within the data are below.
<br><br>
<img src="https://github.com/rgpihlstrom/Project3/blob/main/images/Columns.png" />

## Model Development Methods
This project uses the Crisp DM methodology to generate and optimize model development.  The intended output of this theoretical business case is focused on helping Telco's CEO, and Marketing leadership do the following:
-   **1. Identify Features Most Associated with churn.**
-   **2. Evaluate Telco's Current offerings Ability to Prevent Churn.**
-   **3. Identify Areas for Potential Innovation**
Furthermore, the model would obviously be used for future purposes to identify and potentially prevent customer churn.

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
- Type of Contract – You can see that 89% of churning customers are in Month-to-Month Contracts
- Months with Telco – 75% of your churn is occurring within 29 months of become a customer. 
- Type of Internet Service – Here 66% of churners are using your Fiber Optics program
- Monthly Bill – Here you can see the median monthly bill churners pay is 25% greater than loyal customers

Together these factors were identified by the model as most predictive of churn.


- **2. Current Features/ Services Ability to Prevent Churn:** 
<img src="https://github.com/rgpihlstrom/Project3/blob/main/images/CountofEnrolledServices.png" height="200"/>

### Observations:
Here  you can see that 66% of Telco churners are enrolled in 3 or more services, given this number is greater than 50%, I would deem the services are not adquately helping prevvent customer churn.


- **3. Opportunities for Innovation:** 
<img src="https://github.com/rgpihlstrom/Project3/blob/main/images/Innovation2.png" />

### Observations:
No surprises here, my reccomendations focus on working to create innovation that agument the areas identified above in point #1. 
- Increasing months with telco -  Innovation around loyalty programs to incent longevity
- Reducing monthly spend -  Innovation around bundling services in an attempt to loyal monthly spend 
- Type of contract – Obviously, the goal is to reduce spontaneous churn.  If churn candadates are not interested in the 1 year or a 2 year contract, perhaps there is an shorter term contract that can be created.  Perhaps try 6 months or quarterly contracts.  
- Type of internet service -  Given the big difference in rate of churn across DSL vs. Fiber Optics churners I believe there is something obviously wrong.  I reccomendation is to engage in a competitive and or quality analysis to ensure the quality of the fiber optics lines meeting customer expecations.


## Potential Impact on Revenue
<img src="https://github.com/rgpihlstrom/Project3/blob/main/images/RevenueRamifications1.png" width="600" height="400"/>

### Observations:
- Today Telco experiences 27% customer churn rate which = 31% lost revenue.
- With the help of the Model developed for this project, with 81% detection, Telco has an opportunity to reduce this to as little as 5% (for illustration purposes assuming 100% churn reversal), this would result in a saving of 25% in revenue.

## Next Steps


- **Optimize Current Model - (Look To Reduce Overfitting)** - 
- **Examine Dectection vs. False Alarm Tradeoffs** - 
- **Examine Additional Classifiers** - 
- **Put Model(s) Into Productions** - Once we have optimized our models and/or generated enough models to account for the wide variety of churn data I would look to automate and deploy the models via a web based interface and make it available to the marketing and or customer service teams.


## For More Information

See the full analysis in the [Jupyter Notebooks](folder) or review our <a href="https://github.com/rgpihlstrom/Phase2Project/blob/main/Presentation.pdf">Presentation</a>.

For additional info, contact me here: [ Russell Pihlstrom](mailto:rgpihlstrom@yahoo.com)
