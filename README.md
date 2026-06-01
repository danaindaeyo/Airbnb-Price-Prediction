# Airbnb Pricing Analysis - Bondi Beach

## Project Overview
This project analyzes Airbnb listing data from Sydney to determine a competitive daily accommodation rate for a client's property in Bondi Beach. Using machine learning, we estimate the fair market value based on property characteristics and market conditions.

## Business Problem
The client currently charges $500 per night for their Bondi Beach property. Our goal is to determine if this rate is competitive in the current market and recommend a fair price based on the property's features and comparable listings in the area.

## Client Property Details
🏠 **Property Specifications:**
- **Location:** Bondi Beach (longitude: 151.274506, latitude: 33.889087)
- **Host Status:** Superhost (hosting since August 2010)
- **Capacity:** Accommodates 10 people
- **Layout:** 5 bedrooms, 3 bathrooms, 7 beds
- **Reviews:** 95.0 rating score with 53 reviews
- **Booking Terms:** 
  - Minimum stay: 4 nights
  - Cleaning fee: $370
  - Security deposit: $1,500
  - Strict cancellation policy with 14-day grace period
- **Availability:** 255 days out of the next 365

## Data Source
The analysis uses Sydney Airbnb listing data obtained from the following GitHub repository:
```
https://raw.githubusercontent.com/Finance-781/FinML/master/Lecture%202%20-%20End-to-End%20ML%20Project%20/Practice/datasets/sydney_airbnb.csv
```

The dataset contains detailed information about listings across Sydney, with 84 columns and thousands of property listings. The analysis specifically filters for properties in the Bondi Beach area to ensure relevant market comparisons.

## Data Types
The key features used in the analysis include:

| Feature | Data Type | Description |
|---------|-----------|-------------|
| host_is_superhost | float64 | Whether the host is a superhost (1 = Yes, 0 = No) |
| accommodates | int64 | Number of people the property can accommodate |
| bathrooms | float64 | Number of bathrooms |
| bedrooms | float64 | Number of bedrooms |
| beds | float64 | Number of beds |
| review_scores_rating | float64 | Overall review score out of 100 |
| number_of_reviews | int64 | Total number of reviews received |
| cleaning_fee | float64 | Cleaning fee in USD |
| security_deposit | float64 | Security deposit in USD |
| availability_365 | int64 | Number of days available in the next year |
| longitude | float64 | Geographic longitude of the property |
| latitude | float64 | Geographic latitude of the property |
| price | float64 | Nightly rental price in USD (target variable) |

## Methodology
1. **Data Loading and Cleaning:**
   - Load Sydney Airbnb dataset
   - Handle missing values
   - Convert price columns to appropriate numeric formats
   - Filter data to focus on Bondi Beach properties

2. **Exploratory Data Analysis:**
   - Analyze price distribution in Bondi Beach
   - Examine property feature distributions
   - Identify key factors influencing pricing

3. **Predictive Modeling:**
   - Select relevant features for price prediction
   - Split data into training and testing sets
   - Train a Random Forest Regressor model
   - Validate model using cross-validation
   - Evaluate model performance using Mean Absolute Error

4. **Price Prediction:**
   - Apply the trained model to the client's property details
   - Determine the estimated fair market value

## Model Used
The price prediction was performed using a **Random Forest Regressor** with the following specifications:
- **Algorithm:** Random Forest Regressor
- **Number of estimators:** 100
- **Random state:** 42 (for reproducibility)
- **Training method:** Supervised learning with labeled price data
- **Validation:** 5-fold cross-validation

Random Forest was chosen for this analysis because it:
- Handles non-linear relationships well
- Is robust against outliers (important for real estate data)
- Can capture complex interactions between features
- Provides good performance without extensive hyperparameter tuning
- Reduces overfitting through ensemble methodology

## Results
- **Model Performance:** Mean Absolute Error of $83.90
- **Average Listing Price in Bondi Beach:** $207.08 per night
- **Estimated Fair Price for Client's Property:** $805.08 per night

## Key Finding
The model suggests the client is significantly undercharging for their property. The estimated fair market value of $805.08 per night is approximately 61% higher than the current rate of $500 per night. This presents an opportunity for the client to increase revenue without compromising competitiveness in the market.

## Technologies Used
- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn (RandomForestRegressor)

## Requirements
```
numpy
pandas
matplotlib
seaborn
scikit-learn
```

## Usage
The notebook contains the complete workflow from data loading to final price prediction. To run the analysis:
1. Import the required libraries
2. Load the Sydney Airbnb dataset
3. Run the data preparation and modeling steps
4. Input your property details to get a price estimate
