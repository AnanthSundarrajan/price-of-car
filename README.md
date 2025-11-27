# What drives the price of a car?

**by Ananth Sundarrajan**

#### Business Question Overview

The core business challenge is to determine the main factors influencing used car prices. This can be conceptualized as a supervised machine learning regression task. Our objective is to develop a predictive model that estimates a used car's price using a variety of features, including its make, model, year, mileage, condition, and other pertinent characteristics. The model's effectiveness will be measured by how accurately it can forecast car prices and pinpoint the most significant features that drive those prices.


#### Research Question
What drives the price of a used car?

#### Data Sources
[Modified dataset from Kaggle - Zipped](https://github.com/AnanthSundarrajan/price-of-car/blob/main/vehicles.csv.zip)

#### Methodology
Using the CRISP-DM Methodology, the predictive model uses the below methods:
- Data Understanding
  * Identify missing values
  * Identify duplicate rows
  * Identify the type of information in each column
- Data Preparation
  * Clean dataset
    - Drop Cols (vin, size, id, region, model)
    - Categorial Cols (cylinders, condition, drive, paint_color, type, manufacturer, title_status, fuel, and transmission) - Replace missing values with 'unknown' to retain information in other columns
    - Numerical Cols (Odometer & Year) - Replace the missing values with the column median.
    - Convert cols "Year" and "Odometer" to integers for easier processing
    - Remove rows where the value is "Zero" in the price column
  * Outlier Analysis
    - Remove outliers from Price, Odometer and year
  * Visualization
    - Visualize the Numerical Columns
    - Visualize categorical columns
  * Encode the categorical data
  * Normalize the numerical columns
  * Split the dataframe into Testing set and Training set
- Modeling
  * Train a Linear regression model
  * Train a Lasso Regression model and tune the hyperparameters with GridsearchCV
  * Train a Ridge Regression model and tune the hyperparameters with GridsearchCV
  * Compare model performance
  * Extract the coefficients from the ridge model (Best model)
- Evaluation
  * Model Evaluation: R-Squared, Mean Squared Error
- Deployment


#### Results
Based on the analysis of key feature importances from the Ridge Regression model, here are actionable recommendations:
1. Focus on acquiring vehicles that historically command higher prices. Specifically, target Tesla vehicles (showed the strongest positive impact on price). This indicates a high demand and willingness to pay a premium for Tesla cars. Dealerships should actively seek out used Teslas.
2. Cars with cylinders_12 cylinders also significantly contribute to higher prices, likely due to their luxury or high-performance appeal. These should be considered for high-end inventory.
3. Re-evaluate Rare Luxury Brands: The strong negative coefficients for Ferrari and Morgan are counter-intuitive. This could point to data issues (sparse data, outliers, or misclassification) or a very specific niche market that the general model doesn't capture well. Dealers should conduct separate, in-depth market research for these ultra-luxury brands before making inventory decisions, rather than relying solely on this model's coefficient.
4. Be cautious with brands like Fiat which showed a notable negative impact on price. While they might attract a specific segment, they are less likely to yield high returns.
5. For vehicles with high positive coefficients (e.g., Teslas, 12-cylinder cars), dealerships can set more aggressive pricing, knowing the market supports a premium.


#### Next steps
1. Assess the model with excluded columns such as "Model" and "Region" to drive deeper insights
2. Run advanced modeling techniques such as "Random Forest" to further evaluate the problem.

#### Outline of project

- [Link to notebook](https://github.com/AnanthSundarrajan/price-of-car/blob/main/car_price.ipynb)
- [Link to dataset - Unzip before running](https://github.com/AnanthSundarrajan/price-of-car/blob/main/vehicles.csv.zip)


##### Contact and Further Information
For technical implementation details or model deployment guidance, please take a look at the complete analysis in the Jupyter Notebook.

Author: Ananth Sundarrajan
Program: UC Berkeley Professional Certificate in Machine Learning and Artificial Intelligence
GitHub: https://github.com/AnanthSundarrajan



