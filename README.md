**Author**:[Russell Pihlstrom](mailto:rgpihlstrom@yahoo.com)
![TElcoTitle](/images/TitlePic.png)


## Overview

This project uses Decision Tree and RandomForestClassifier supervised learning methods to classify the churn behavior of Telco's customer base.  By analyzing past actual churn vs. no churn behavior along with the respective customer attributes associated with each type of behavior, I developed a model that detected 81% of Telco's churning customers.  The developed algorithm, “model”, can be used to predict the future churn vs. no churn behavior with the intent of identifying and preventing future customer flight.  The following 5 features were most predictive of churn: Month to Month Contract, Customer Tenure, Fiber Optics Internet Service, and Monthly Charges.


## Business Problem
Customer retention is a serious concern for all companies.  However, within the Telecommunications industry customer churn is of particular importance.  Fierce competition, along with a difficult to differentiate product, makes retaining customer on factors beyond price almost impossible.  Historically thin profits margins are only getting thinner.  In fact, a case study done by the Bain Company on the telecom industry suggested a 5% increase in customer retention can lead to an increase in profits by 25%-95% percent (https://www.bain.com/client-results/focus-on-customer-engagement-to-improve-retention/).





Telco is currently losing 27% of its customers and 31% of its revenue to churn.


<img src="https://github.com/rgpihlstrom/Project3/tree/main/images/TelcoChurnrates.png" width="200" height="400" />


![TElcoTitle](/images/TelcoChurnrates.png)

To thwart customer churn, Telco is willing to engage in new outreach programs but it must first identify likely to churn customers.  Given the above research along with working knowledge on the cost to acquire vs retain customers, the CEO of Telco has asked me to place a particular focus on detection at the potential expense of unnecessary outreach activities.

![TElcoTitle](/images/ChurnOverFalseAlarms.png)



## Data
1.	**Provided Data**: The data used for this project was provided by Kaggle and used as a past source for competition (Telco Customer Churn https://www.kaggle.com/blastchar/telco-customer-churn)  The data set contained approximately 8k rows and 21 features capturing the purchase, usage, and tenure information on a subset of Telcos customers.  17 of the features were categorical, 3 were continuous, and 1 was ID.

## Methods
This project uses the Crisp DM methodology to generate and optimize the final RandomForestClassifier model.  The model developed provides the opportunity for Telco's CEO, and Marketing staff to do the following:
    1. Identify the features that are most associated with churn
    2. Evaluate Telco's current offerings to determine if its current portfolio of products are aiding in the prevention of churn
    3. Act as a source for innovation, in a attempt to improve customer retention.
Altimately, the model will be used for future purposes to identify and potentially prevent customer churn.

As prescribed by the Crisp DM methodology, model development was very iterative.  I began by doing secondary research around the basic business drivers of the real estate industry, gaining a better understanding on the prevalence of churn in the idustry and the costs associated with lose.  Early in the iterative research/ modeling process it was obvious that I was dealing with an imbalanced set of data (more information on non-churn customer vs. churn costomers), which would require me to adjust the data and or algorythms to account for the imbalance.  I addressed this gap by first attempting the model using different wieights and ultimately decided to do a SMOTE(Synthetic,,,,) technique to overcome this challenge.  

## Model Selctions
During early iterations I tried several different types of classifiers, going from Logistic Regresion, Naive Bayse, Gradient Boost, Ada, and XGBoost.  Ultiimately,  I decided to use Decision Trees and Random Forest as these classifiers are Non-parametric and are hihgly intpretiable.  These were key attributes given my data contained mostly caterogical data, did not require addressing Mulitolinearity, and intended for an audience that would require high interpretibilty.


## Results
The final model generated a recall score of 82%, precision of , and ...

<img src="/images/ROC.PNG" width="400" height="300" align="left">

**The features that had the most influence/ weights include:** 

<img src="/images/MostImportantFeatures1.png">



![A_Players](/images/ChangesInAveargeHome.png)

**Greatest Insight**:  The weight “Assessor Appraisal Value” had, relative to the second most heavy feature “Above Square Footage”, was very surprising and insightful.  The reason this was so insightful was the lack of reference to this variable in all my research in regards to determining a homes sales price.  Research suggested that agents primarily use CMA (Comps) to set pricings and while I did not have a feature related to CMA in my model, I would hypothesize it would be stronger than “Assessor Appraisal Value” in predictive power.  That being said, I hypothesize that "Assessor Appraisal Value" would be the second most heavy feature in a model that contained both "Comp Prices" and "“Assessor Appraisal Value". Given this hypothesis I would recommend it be added as a potential attribute to all home predictive models.  Most research suggests the more common features “Location, Location, Location” as well as “Above Square Footage” as the most helpful. I believe “Assessor Appraisal Value" is currently being overlooked. 

One caveat to this recommendation would be if significant improvements had been made to a home since the last onsite visit of a tax assessor.  Per the King County website, assessors make onsite assessments once every 6 years, this would make older assessments less accurate if significant improvements have been made to a home since the last visit.  The same can be said if significant declines in value had occurred since the last onsite appraisal visit.


## Conclusions/ Recommendations
This analysis leads to three recommendations that would help King County Reality achieve higher seller commissions:

**1. Physical "Controllable" Features:**  As real estate agents look to coach prospective sellers on features to improve in order to maximize sales price they should focus on “Above Square Footage”, as well as increasing “Grade” which is related to features such as custom cabinets, and other various customizations that make homes less "basic" and more designer/ custom
<br>
<img src="/images/ControlableFeatures.png" width="500" height="300"></image>
<br>  
**2. Location "Influenceable" Features:** While the above "controllable" features allow sellers to make short-term efforts and realize instant benefits, location based features, such as the ranking of the school district in which a home resides or the number of attractions within close proximity to a home, are very difficult to impact in a direct manner.  However, over the course of several years a home owner can look to invest in efforts and finances to improve school performance and or influence political decisions related to politicians who believe in bringing more attractions to the area in which a home resides.
<br>
<img src="/images/InfluencableFeatures.png" width="500" height="300"></image>
<br>
**3. Setting "Better" More Informed Prices:**  The 200% delta between the feature “Assessor Appraisal Value” and the next biggest feature "Above Square Footage" suggests that adding “Assessor Appraisal Value” to home price estimate models could be very instrumental in augmenting current processes real estate agents use in setting prices.  This could be especially true in situations where CMA data is either not available, nor as applicable as desired.
<br>
<img src="/images/taxAssesorValues.png" width="500" height="300"></image>

## Next Steps

Further analyses could yield additional insights to help King County Reality increase revenue from sales commissions
- **Augment the Current Model** Look to add prediction accuracy by studying the homes that showed the largest difference between the predicted and the actual prices of homes sold.  Additionally, looking to add features requiring interactivity could be explored as many factors that would seem to be impactful were eliminated due to VIF.
- **Creating Additional Models**  The model created was optimized for the most frequent "Common/ Main stream" home prices, quantity of square footage, number of bathroom/ rooms, lot size and several other related features were used to create the model.  The model was optimized for homes that had prices between ~$300k - ~$900k, Bedrooms between 1-4, Lot Size 4,000 – 12,000, Other).  Additional models could be created focused on homes <$200k, >$900k, Waterfront, large Lot Size, etc. 
- **Deployment** Once we have optimized our models and/or generated enough models to account for the wide variety of homes present in the King County district I would look to automate and deploy the models via a web based interface and make it available to the larger public for impromptu consumption and a potential Marketing tool to generate web traffic and brand awareness.

## For More Information

See the full analysis in the [Jupyter Notebooks](folder) or review our <a href="https://github.com/rgpihlstrom/Phase2Project/blob/main/Presentation.pdf">Presentation</a>.

For additional info, contact me here: [ Russell Pihlstrom](mailto:rgpihlstrom@yahoo.com)
