# Sales Prediction Using Pycaret

### JOB-A-THON – AnalyticsVidhya September 2021 

![predictoins](https://user-images.githubusercontent.com/42634704/134122693-a796413f-a04a-481d-be63-8595fe85f27f.JPG)

Problem Statement – Sales Prediction for one month

Dataset      -  Train Data 184571 rows X 15 columns (Include Sales as  Target)
	        Test Date  22265 rows X 14 columns
          
Attributes     -    ID, Store_id, Store_Type, Location_Type, Region_Code, Date, Holiday,Discount, Order, Sales

Evaluation    -   The submission will be evaluated using the RMSLE metric. 

## Approach
There is two kind of approaches for this problem 
* Consider all the data set and make general model
* Independently predict Sales for each stores

I tried both approaches and found general model would be better since we achieved better RMSLE for both methods.

## Data Pre-processing  
* Dropped the Order features since we didn’t have it for the test(future) dataset

* Created new features from Date:  'year', ‘day’ ,'quarter’, 'month', ‘weekday’ etc.
* Since target feature was skewed dropped extreme values based on percentiles
* Treated this features as  categorical and used Label encoding : 
      Store_Type, Location_Type, Region_Code, 'Discount', 'weekday', 'Quarter', 'Month‘  


## Modelling
* Used Pycaret Regression for the modelling 
* Four base models have been fitted and tuned 
* Generated Stacking and Blending of the base models

![learning](https://user-images.githubusercontent.com/42634704/134123135-be042a3e-be9c-4ff9-90f6-387729745c1c.JPG)


