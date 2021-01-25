**Author**:[Russell Pihlstrom](mailto:rgpihlstrom@yahoo.com)
![TElcoTitle](/images/TitlePic.png)


## Overview

This project uses Decision Tree and RandomForestClassifier supervised learning methods to classify the churn behavior of Telco's customer base.  By analyzing past actual churn vs. no churn behavior along with the respective customer attributes associated with each type of behavior, I developed a model that detected <b><ins>81%</ins></b> of Telco's churning customers.  The developed algorithm, “model”, can be used to predict the future churn vs. no churn behavior with the intent of identifying and preventing future customer flight.  The following 5 features were most predictive of churn: <strong>Month to Month Contract, Customer Tenure, Fiber Optics Internet Service, and Monthly Charges.</strong>


## Business Problem
Customer retention is a serious concern for all companies.  However, within the Telecommunications industry customer churn is of particular importance.  Fierce competition, along with a difficult to differentiate product offering, makes retaining customers, on factors beyond price, almost impossible.  Therefore, the historically thin profits margins of the past are only getting thinner.  In fact, a case study done by the Bain Company on the Telecom industry suggested a 5% increase in customer retention can lead to an increase in profits by 25%-95% percent (https://www.bain.com/client-results/focus-on-customer-engagement-to-improve-retention/).



<br/>

### Current Situation: Telcos is losing 27% of its customers and 31% of its revenue to churn.


<img src="https://github.com/rgpihlstrom/Project3/blob/main/images/TelcoChurnrates.png" width="600" height="400" />
<br/>

## Data
1.	**Provided Data**: The data used for this project was provided by Kaggle and served as a basis for past Kaggle competitions (Telco Customer Churn https://www.kaggle.com/blastchar/telco-customer-churn)  The dataset contains approximately 8k rows and 21 features capturing the purchase, usage, and tenure information on a subset of Telcos customers.  17 of the features are categorical, 3 are continuous, and 1 is ID.
<img src="https://github.com/rgpihlstrom/Project3/blob/main/images/Columns.png" />

## Methods
This project uses the Crisp DM methodology to generate and optimize model development.  The intended output of this theoretical business case is focused on helping Telco's CEO, and Marketing leadship do the following:
-   **1. Identify the features that are most associated with churn.**
-   **2. Evaluate Telco's current offerings to determine if its current portfolio of products are aiding in the prevention of churn.**
-   **3. Act as a source for innovation, in a attempt to improve customer retention.**
Ultimately, the model will be used for future purposes to identify and potentially prevent customer churn.

As prescribed by the Crisp DM methodology, model development was very iterative.  I began by doing secondary research around the basic business drivers of the Telecom industry, gaining a better understanding on the prevalence of churn and the costs associated with fleeing customers.  ALong with the preject requirements noted above the following addtional factors were considered during the modeling process:
-   **1. Data imbalance**  Early in the development process it was obvious that I was dealing with an imbalanced set of data (more information/ rows of data on non-churn customer vs. churn costomers).  To ensure optimum identification my processes/ modeling would need to account for this imbalance.  I addressed this gap by first attempting the model using different weights and ultimately decided to do a SMOTE(Synthetic,,,,) technique to overcome this challenge.

- **2. Selection of which supervised learning methods to use**  Initiallyt I tried several different types of classifiers, ranging from Logistic Regresion, Naive Bayse, Gradient Boost, Ada, and XGBoost.  Ultiimately,  I decided to use <b><ins>Knn, Decision Trees and Random Forest</ins></b> , as these classifiers are Non-parametric and are hihgly intpretiable.  Inteprabilty, the disportionate number of categorical features, along with being able to avoid addressing mulitolinearity were the ultimate factors in driving classifier selection.  

-   **3. Business Drivers: Churn Detection > False Alarms**  Reccomendations on model developmnent was based on secondary research along with working knowledge on the disparity between the cost to acquire vs the cost to retain customers.  In this hypotheical scenario, the CEO of Telco has asked me to place a particular focus on detection at the potential expense of unnecessary outreach activities.

<img src="https://github.com/rgpihlstrom/Project3/blob/main/images/ChurnOverFalseAlarms.png" width="600" height="400" />


## Model Selctions
During early iterations I tried several different types of classifiers, going from Logistic Regresion, Naive Bayse, Gradient Boost, Ada, and XGBoost.  Ultiimately,  I decided to use Decision Trees and Random Forest as these classifiers are Non-parametric and are hihgly intpretiable.  These were key attributes given my data contained mostly caterogical data, did not require addressing Mulitolinearity, and intended for an audience that would require high interpretibilty.
<br/>
<img src="/images/ROC.PNG" width="400" height="300">
<br/>
## Results/ Reccomendaitons
The final model generated a recall score of 81%, precision of , and ....,  As stated above the goal of the project was three fold. 
I have outlined and summarized results below

- **1. The features that had the most influence/ weights include:** 
<img src="/images/MostImportantFeatures1.png">
- **2. Current Features Abilty to Prevent Churn:** 

<img src="/images/MostImportantFeatures1.png">

- **3. Opportunities for Innovation:** 
<img src="/images/MostImportantFeatures1.png">


## Next Steps

Further analyses could yield additional insights to help King County Reality increase revenue from sales commissions
- **Augment the Current Model** Look to add prediction accuracy by studying the homes that showed the largest difference between the predicted and the actual prices of homes sold.  Additionally, looking to add features requiring interactivity could be explored as many factors that would seem to be impactful were eliminated due to VIF.
- **Creating Additional Models**  The model created was optimized for the most frequent "Common/ Main stream" home prices, quantity of square footage, number of bathroom/ rooms, lot size and several other related features were used to create the model.  The model was optimized for homes that had prices between ~$300k - ~$900k, Bedrooms between 1-4, Lot Size 4,000 – 12,000, Other).  Additional models could be created focused on homes <$200k, >$900k, Waterfront, large Lot Size, etc. 
- **Deployment** Once we have optimized our models and/or generated enough models to account for the wide variety of homes present in the King County district I would look to automate and deploy the models via a web based interface and make it available to the larger public for impromptu consumption and a potential Marketing tool to generate web traffic and brand awareness.

## For More Information

See the full analysis in the [Jupyter Notebooks](folder) or review our <a href="https://github.com/rgpihlstrom/Phase2Project/blob/main/Presentation.pdf">Presentation</a>.

For additional info, contact me here: [ Russell Pihlstrom](mailto:rgpihlstrom@yahoo.com)
