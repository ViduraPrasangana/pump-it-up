# Pump-it-Up-Data-Mining-the-Water-Table-Competition
https://github.com/ViduraPrasangana/pump-it-up.git

## Preprocessing 
### Remove features since similarity and other reasons
* `public_meeting`
* `permit`
* `management_group`
* `extraction_type_group`
* `extraction_type_class`
* `installer` 
* `date_recorded` - there is no relationship
* `construction_year` - removed and added no of working years
* `wpt_name` - almost every value is unique
* `num_private` - most of data are 0
* `subvillage`  - low data for each category
* `region_code` - duplicate of region
* `recorded_by` - there is no relationship
* `scheme_name` - each category has small number of data
* `payment` - payment and payment_type has almost same classes
* `quality_group` - quality_group and water_quality has almost same classes
* `quantity_group` - quantity_group and quantity has same classes
* `source_type` -  source is almost same
* `source_class` -  source is almost same
* `waterpoint_type_group` - waterpoint_type_group and waterpoint_type have almost same classes

### Replace missing values
Below columns had 0 for missing values
* `gps_height`
* `population`
* `amount_tsh`
* `longitude`
* `latitude`
* `construction_year`
First replaced with mean of respective region and district_code
Remaining null values replaced with mean of region
Remaining null values replaced with overall median

Only `construction_year` is replaced with median as mean gives year with decimal points

Below categorical column had NaN for missing values
* `funder` 
* `scheme_management`
Replaced with new category `other` 

### Normalization 
Following categories had large values and normalized to 0 - 20 using Min - Max scaler
* `amount_tsh`
* `gps_height`
* `population`

## Feature Engineering
### Target encoding - Used `ward` feature to target encode. Because, `ward` feature has many unique values.


## Experimented Models

* RandomForestClassifier (sklearn)
* XGBClassifier (xgboost)


## Submission

![Capture](https://github.com/ViduraPrasangana/pump-it-up/blob/master/proof.png)
