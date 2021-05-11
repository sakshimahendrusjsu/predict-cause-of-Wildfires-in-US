# Predicting Causes of Wildfires in US

### Data Preprocessing and Exploratory Data Analysis (EDA)

We started with a handful of features in the beginning primarily based on date and location. 
This included columns:
> FIRE_YEAR, STAT_CAUSE_DESCR, STAT_CAUSE_CODE, LATITUDE, LONGITUDE,
> STATE, DISCOVERY_DATE, DISCOVERY_DOY, FIRE_SIZE, DISCOVERY_TIME, FIPS_CODE,  CONT_DATE,  OWNER_DESCR CONT_TIME

Other columns were mostly reference id columns FOD_ID, FPA_ID, REPORTING ID or FIRE_NAMES which overlapped with other columns and could be avoided.

### Methods Followed

We split the training and test dataset into 80:20 ratio to perform different classification.
We applied following data classification methods on our training dataset:
* Decision tree
* Random Forests
* AdaBoost
* K-NN Classification
* Logistic regression

After performing the data analysis using confusion matrix , we found that some of the causes had less count while other causes like debris had larger counts. Due to this, it was difficult to find the cause as the model lacked enough information to pivot towards them.
This resulted in accuracy of 65% across models.
To solve this problem, we divided the data into two causes:
* Natural Causes
* Human Causes
Dropped miscellaneous/undefined and missing causes
This helped us achieve better results across different classification models.
We were finally able to achieve 85% accuracy.

