# Predicting Causes of Wildfires in US

### Objective 
This project intends to analyze the “Spatial wildfire occurrence data for the United States” https://www.fs.usda.gov/rds/archive/catalog/RDS-2013-0009.4 with data ranging from 1992-2015. Implement necessary data pre-processing and exploration techniques, apply various classification and regression models to predict the causes for wildfires. Compare and evaluate the performance of the models. Also, improve the accuracy of the predictions using tuning and validation methods.


### Data Preprocessing and Exploratory Data Analysis (EDA)

We started with a handful of features in the beginning primarily based on date and location. 
This included columns:
> FIRE_YEAR, STAT_CAUSE_DESCR, STAT_CAUSE_CODE, LATITUDE, LONGITUDE,
> STATE, DISCOVERY_DATE, DISCOVERY_DOY, FIRE_SIZE, DISCOVERY_TIME, FIPS_CODE,  CONT_DATE,  OWNER_DESCR CONT_TIME

Other columns were mostly reference id columns FOD_ID, FPA_ID, REPORTING ID or FIRE_NAMES which overlapped with other columns and could be avoided.

Additional feature scaling and reducing techniques were applied

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

### Data Flow Diagram

![classification_modelling](/classification_modelling.png)


### Steps
1) Please refer Notebook -> Classifiers_combined_final.ipynb
2) We ran our respective models on a combined dataset and evaluated using kfold cross validation
3) Please download "RDS-2013-0009.4_SQLITE.zip" from link: https://www.fs.usda.gov/rds/archive/Catalog/RDS-2013-0009.4/. The data format is Sqlite.
4) Unzip the folder and place it parallel to the notebook, else update the path in the notebook:
      ``` conn = sqlite3.connect('RDS-2013-0009.4_SQLITE/Data/FPA_FOD_20170508.sqlite') ```
      
EDA:
We carried out indvidual exploratory data analysis too. Please check the following files for more details
1) Descision Tree Classifcation : descisionTreeClassifier.ipynb
2) Random Firest Classification : random_forest_final.ipynb
3) KNN Classification : KNN Classifier_83.88accuracy.ipynb
4) LogisticRegression : wildfire_prediction_with_logistic_regression.ipynb
