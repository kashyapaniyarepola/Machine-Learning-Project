# Machine-Learning-Project - Pump it Up: Data Mining the Water Table

###### Project Link: [https://github.com/kashyapaniyarepola/Machine-Learning-Project](https://github.com/kashyapaniyarepola/Machine-Learning-Project)

## Preprocessing and Feature Engineering Techniques

###### *Feature Selection:* Exploring Simillar Columns and Less Imporatant Columns

- ***scheme_management*** and ***management*** columns contain almost same values and ***scheme_management*** contain 3877 null values. Therefore ***scheme_management*** column is dropped.
- ***management_group*** column in gropped version of ***management*** column and ***management*** column has more details compared to ***management_group*** column. Therefore ***management_group*** column is dropped.
- ***quantity_group*** and ***quantity*** columns contain same values. So, ***quantity_group*** is dropped.
- ***source_type***, ***source_class*** and ***source*** contain same information. But ***source*** column contains more information. So, ***source_type*** and ***source_class*** are dropped
- ***water_quality*** and ***water_group*** columns contain same values and ***water_group*** contain more unique values. So, ***water_quality*** column is dropped.
- ***payment_type*** and ***payment*** conatin same values so, ***payment*** column is dropped.
- ***extraction_type_group***, ***extraction_type_class*** and ***extraction_type*** conatain same values and ***extraction_type_class*** contain less details so, ***extraction_type_class*** and ***extraction_type*** are dropped. 
- Since ***waterpoint_type_group*** and ***waterpoint_type*** contain same information, ***waterpoint_type_group*** is dropped.
- Since ***recorded_by*** conatain only on value type and it doesn't give any information to the model, that column is dropped.
- After observing the data I realized ***wpt_name***, ***scheme_name***, ***id*** and ***region_code*** are not giving information about functionality so, I decided to drop them.
- I dropped ***amount_tsh***, because 70% are not informative.
- In ***date_recorded*** 95% of values are recorded between 2011-2013 so, i dropped that column. Since ***num_private*** has noany informative values, I dropped that column.
- In ***subvillage***, there are lots of nonunique value and that values provide details of location. Since I have ***region** I dropped ***subvillage** column. 

###### Handling Missing Values and Incomplete Values

- *Target Encoding:* Majority values of ***construction_year*** contains *0* value. To handled that, first I created new feature called ***decade*** which categorized years according to dacedes. Then replaces *0* value in ***construction_year*** to mean value(i.e. *2000*). Below diagram shows how ***dacade*** correlated with target values.
 
 ![dacade and target values](https://github.com/kashyapaniyarepola/Machine-Learning-Project/blob/main/diagram%201%20-%20dacade%20and%20target%20value.png)
 
 - ***installer*** column contains lots of *NaN* and *0* values. First replaced them with *Unknown* value. After looking at the data, I realized that there are splling mistakes (eg- trere are values called District Council and District council). Then I corrected those spelling mistakes. Below diagram shows how ***installer_cat*** correlated with target values.

![installer_cat and target values](https://github.com/kashyapaniyarepola/Machine-Learning-Project/blob/main/diagram%202%20-%20installer_cat%20vs%20target%20valu.png)

- *Normalization:* To ease of encoding, I created new feature called ***installee_cat*** by collecting ***installer*** and named *other* for value clounts contain less than *400*. In this case I only have 17 unique ***installer_cat*** values.
- Since ***funder*** conatains *NaN* and *0* values, I replaced them with *Unknown* value. This column contains thousands of differnt categorical values. So, I selected most common 20 values for encoding and added to a new fearture called ***funder_cat***. Below diagram shows how ***funder_cat*** correlated with target.

![funder_cat and target values](https://github.com/kashyapaniyarepola/Machine-Learning-Project/blob/main/diagram%203%20-%20funder_cat%20vs%20target%20values.png)

- *Target Encoding:* In ***longitude***, there are *0* values so I replaced mean(i.e. *35.15*) with them.
- *Target Encoding:* In ***population***, I replaced *0* value with its mean (i.e. *281*). 
- ***public_meeting*** and ***permit*** columns contain null values. So, I replaced them with their most common values.

###### Model Selection and Validation

- After converting target in to ternary values,  I used *Random Forest Classifier* and *XGBClassifier* to train and *XGBClassifier* provided better score. Below are the cross validation results for *Random Forest Classifier*.

![cross validation](https://github.com/kashyapaniyarepola/Machine-Learning-Project/blob/main/cross%20val%20results.png)

###### Submission and Final Rank

- In the Pump it Up: Data Mining the Water Table challenge, I scored ***0.8200*** as my final result and ranked as the ***1135***. Below diagram shows the submission details

![proof of submission](https://github.com/kashyapaniyarepola/Machine-Learning-Project/blob/main/proof%20of%20submission_xgboost.png)

- Below diagram shows the final rank I obtained

![final rank](https://github.com/kashyapaniyarepola/Machine-Learning-Project/blob/main/final%20rank_xgboost.png)


## Notebooks:

- [Data visualization, data preprocessing and feature engineering](https://github.com/kashyapaniyarepola/Machine-Learning-Project/blob/main/Data_Preprosesing_and_Feature_Engineering.ipynb)
- [Model selection, training and evaluation](https://github.com/kashyapaniyarepola/Machine-Learning-Project/blob/main/Training_and_Evaluation.ipynb)
