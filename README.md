# Pump it Up Data Mining the Water Table - Competition

Implementation Link : https://github.com/HimashiRathnayake/Pump-it-Up-Data-Mining-the-Water-Table-Competition

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

# Experiments

### Preprocessing Techniques :

* Fix typo errors in the Dataset - `installer`
* Drop duplicated features - `source_class`, `source_type`, `management_group`, `scheme_management`, `quantity_group`, `quality_group`, `payment_type`, `extraction_type_class`, `extraction_type`, `waterpoint_type_group`, `region_code`
* Identify and fix the feature types.
* Handling missing Values 
  * Add a new Category for missing values or add missing values to an existing category like `Unknown`. - For categorical features.
  * Replace 0 which seems to be unknown by mean. - `longitude`, `population`.
  * Replace NaN values by most common value / median value. - `public_meeting`, `permit`
* Remove features with less details.
  * `wpt_name`, `scheme_name` - Lots of None values, & most of the labels in this feature have very low value count.
  * `amount_tsh` - Most of the data (70%) is 0.0. 
  * `date_recorded` - Most of the dates are beetween 2011-2013 & seems to be non-informative.
  * `num_private` - Most of the data (99%) is 0.
  * `sub_village` - Very low value count.
  * `recorded_by` - One unique value for all.
* Reduce feature's category counts - Only keep few categories & group other categories to Other, for the features having large number of categories - `installer`, `funder`
* Converting target values to ternary values. - `status_group`

### Feature Engineering Techniques :

* Check Mutual Information
* Binning to groups - `construction_year`
* Clustering - `longitude`, `latitude`
* Principal Component Analysis - `gps_height`, `population`
* Target Encoding - `ward`

### Experimented Models :

* [Random Forest Classifier](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html)
* [XGBoost Classifier](https://xgboost.readthedocs.io/en/latest/python/python_api.html)

### Experiments Results :

| Modal | Train Accuracy | Test Accuracy |
| --- | --- | --- |
| Random Forest | 0.9089 | 0.7913 |
| XGBoost | 0.9060 | 0.8111 |

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

# Submission
![result2](https://user-images.githubusercontent.com/47143221/133818657-3af2c817-ccd2-4af3-ac8a-bc94b8632c3b.png)
![result3](https://user-images.githubusercontent.com/47143221/133819480-47e90b1c-08bc-4724-b8f7-7ac9d5fdc862.png)
