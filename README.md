# Machine-Learning-Project - Pump it Up: Data Mining the Water Table

## Preprocessing and Feature Engineering Techniques

###### Exploring Simillar Columns and Droping Them

- ***scheme_management*** and ***management*** columns contain almost same values and ***scheme_management*** contain 3877 null values. Therefore ***scheme_management*** column is dropped.
- ***management_group*** column in gropped version of ***management*** column and ***management*** column has more details compared to ***management_group*** column. Therefore ***management_group*** column is dropped.
- ***quantity_group*** and ***quantity*** columns contain same values. So, ***quantity_group*** is dropped.
- ***source_type***, ***source_class*** and ***source*** contain same information. But ***source*** column contains more information. So, ***source_type*** and ***source_class*** are dropped
- ***water_quality*** and ***water_group*** columns contain same values and ***water_group*** contain more unique values. So, ***water_quality*** column is dropped.
- ***payment_type*** and ***payment*** conatin same values so, ***payment*** column is dropped.
- ***extraction_type_group***, ***extraction_type_class*** and ***extraction_type*** conatain same values and ***extraction_type_class*** contain less details so, ***extraction_type_class*** and ***extraction_type*** are dropped. 
- Since ***waterpoint_type_group*** and ***waterpoint_type*** contain same information, ***waterpoint_type_group*** is dropped.

###### Handling Missing Values and Incomplete Values

- Majority values of ***construction_year*** contains 0 value. To handled that, first I created new feature called ***decade*** which categorized years according to dacedes. Then replaces 0 value in ***construction_year*** to mean value(i.e. 2000). Below diagram shows how ***dacade*** correlated with target values.
 
 ![dacade and target values]()

## Notebooks:

Data visualization, data preprocessing and feature engineering can be found in:

Model selection, training and evaluation can be found in:
