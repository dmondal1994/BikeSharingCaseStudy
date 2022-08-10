# Linear Regression Assignment
## Bike Sharing Case Study

<h2> <center> Student Name: Debasish Mondal, Co-hort: May-2022 </center>

#### Problem Statement: Build a multiple linear regression model for the prediction of demand for shared bikes.
#### Businees Goal: To correctly understand how demand varies with different characteristics so that bike companies can adjust their business strategies in line with the demand levels and client expectations.
  
## Data Analysis Steps:
  - Step 0: Import Libraries
  
  - Step 1: Data Reading
  
  - Step 2: Data Quality Checking
    - Step 2.1: Null-value Checking:
    - Step 2.2: Variable Deletion: Delete those variables that do not have any business importance.
    - Step 2.3: Data Consistency Checking: To check whether there is any absurd value present in the dataset or not.
  
  - Step 3: Exploratory Data Analysis (EDA)
    - Step 3.1: Categorical Data Analysis: To analyse categorical features with respect to the total ride count.
    - Step 3.2: Segmented Data Analysis: First, make segments for the numerical variables and then check variation with respect to the total ride count.
  
  - Observations as per the Exploratory Data Analysis (EDA)
      - Upon analysis, we have the following observations:
          - The number of bookings is highest in the `fall` season.
          - The month of `June` has the highest number of bookings.
          - The majority of bookings are on `Friday`.
          - The number of bookings is highest in the `clear (or few clouds or partly cloudy)` weather.
          - The number of bookings is highest in the year `2019`.
          - The number of bookings is greatest if it is not a `holiday`.
          - The number of bookings is greatest if it is a `working day`.
          - The most bookings are made when the `temperature` is between 22.0 and 25.0 degrees Celsius.
          - The most bookings are made when the `feeling temperature` is between 27.0 and 31.0 degrees Celsius.
          - The most bookings are made when the `humidity` is between 66.0 and 74.0 units.
          - The most bookings are made when the `wind speed` is between 5.0 and 8.0 units. 
  
  - Step 4: Model Preparation
    - Step 4.1: Continous Variable Handeling: To check the correlation between continous variables in order to detect multicollinearity.
    - Step 4.2: Categorical Variable Handeling: To create dummy variables for categorical features (other than binary variables).
   
  - Step 5: Model Building
    - Step 5.1: Test-Train Splitting: To split the data into the training and test datasets.
    - Step 5.2: Rescaling Features: To apply scaling on the training dataset.
    - Step 5.3: Model Selection by Iteration: Here we use the Recursive Feature Elimination (RFE) method along with p-values and Variable Inflation Factor (VIF) values.
   
  - Step 6: Model Prediction: To make predictions on the test dataset based on learnings of trainning dataset.
  
  - Step 7: Error Analysis: To check whether the error terms are normally distributed with zero mean or not.
  
  - Step 8: Making Final Business Decisions
    - Upon multilinear regression analysis on the given dataset, we evaluate the following quantities:
    - The `best fitted model equation` is -> `cnt` = 0.0862 + (`yr` × 0.2342) - (`holiday` × 0.0813) + (`atemp` × 0.5674) - (`windspeed` × 0.1239) + (`mnth_august` × 0.0538) + (`mnth_september` × 0.1048) + (`season_summer` × 0.0880) + (`season_winter` × 0.1252) - (`weathersit_light` × 0.2454)
    - **Training Data**
      - R<sup>2</sup> value = 0.800
      - Adjusted R<sup>2</sup> value = 0.796
    
    - **Test Data**
      - R<sup>2</sup> value = 0.774
      - Adjusted R<sup>2</sup> value = 0.763
  
    - The difference in R<sup>2</sup> values between the train and test datasets is `0.800 - 0.774 = 0.026 (less than 0.5)`. Additionally, the difference in adjusted-R<sup>2</sup> values between the train and test datasets is `0.796 - 0.763 = 0.033 (less than 0.5)`. As a result, using the training data, we effectively built a predictive model.
  
    - In terms of achieving business goals, `feeling temperature (i.e. 'atemp' variable)`, `Light Weather (Snow/Rain/Thunderstorm/Scattered clouds etc.) (i.e. 'weathersit_light' variable)`, and `year (i.e. 'yr' variable)` are the top three parameters for booking bike rides.
  
