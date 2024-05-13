# Title and Author
- **Title:** Analysis of Used Cars and Price Prediction
- **Prepared for:** UMBC Data Science master’s degree Capstone by Dr. Chaojie (Jay) Wang
- **Author:** Vikas Reddy Nagulapelly
- [GitHub]( https://github.com/vikas-reddy-319)
- [LinkedIn]( https://www.linkedin.com/in/vikasreddynagulapelly)
- [Presentation]( https://github.com/DATA-606-2023-FALL-TUESDAY/Nagulapelly_Vikas_Reddy/blob/main/docs/Used%20car%20Price%20Prediction.pptx)
- [YouTube Video]( https://www.youtube.com/)

# Background
**Background:** Craigslist is one of the largest advertisement websites for viewing and posting local advertisements, covering various categories, including housing, job postings, items for sale, services, and personals. The data for this project was scraped from the website [Craigslist](https://www.craigslist.org).

**What is it about:** This project focuses on buying used cars and addresses a common issue with buying secondhand cars: the lack of control over pricing.

**Why does it matter:** Access to the right information can help anyone make informed decisions and find good deals when buying a car.

**Research Questions:**
1. Identify the trends in the sales of cars over the years.
2. Investigate the correlation between car price and its specifications.
3. Predict the price of a used car based on its specifications.

# Data
**Data Sources:** [https://github.com/AustinReese/UsedVehicleSearch](https://github.com/AustinReese/UsedVehicleSearch)

**Data Size:** 1.45 GB

**Data Shape:** 426,880 rows, 26 columns

**Time Period:** 1900 - 2022

**Columns Description and Data Types:**
## Column Descriptions and Data Types

| Column Name   | Data Type | Description                                      |
| -------------  | ----------- | ---------------------------------------------  |
| ID            | int       | Unique ID assigned to every ad and serves as the primary key. |
| Price         | int       | Price in US dollars, not adjusted for inflation. |
| Year          | float     | Year of car manufacture.                        |
| Manufacturer   | string   | Name of the car manufacturer, with 43 unique businesses. |
| Model         | string   | Exact model of the car.                        |
| Condition     | string   | Condition of the car (e.g., excellent, good, fair, like new, salvage, new). |
| Cylinders     | string   | Number of cylinders in the car engine (ranging from 3 to 12). |
| Fuel          | string   | Type of fuel used (diesel, gas, electric, hybrid, other). |
| Odometer      | float     | Distance the car has traveled after purchase.  |
| Status        | string   | Status of the car (clean, lien, rebuilt, salvage, parts only, missing). |
| Transmission  | string   | Type of transmission (automatic, manual, other). |
| VIN           | string   | Vehicle identification number.                 |
| Drive         | string   | Drive transmission type (4WD, FWD, RWD).      |
| Type          | string   | Vehicle type (e.g., SUV, mini-van).            |
| State         | string   | Short form representation of the state where the car is listed. |
| Latitude      | float     | Geographic coordinates representing the car's location for sale. |
| Longitude     | float     | Geographic coordinates representing the car's location for sale. |

# Potential Features

In the context of regression analysis, we have identified potential features that can be used to predict the target variable, "Price." These features include:

1. **Condition**
   - Categories: 'good', 'excellent', 'fair', 'like new', 'new', 'salvage'
   - Description: The condition of the used car, which can greatly influence its price.

2. **Fuel**
   - Categories: 'gas', 'other', 'diesel', 'hybrid', 'electric'
   - Description: The type of fuel used by the car, which can impact both environmental factors and operating costs.

3. **Drive**
   - Categories: 'rwd' (Rear-Wheel Drive), '4wd' (Four-Wheel Drive), 'fwd' (Front-Wheel Drive)
   - Description: The drive transmission type of the car, which affects its performance and handling.

4. **Type**
   - Categories: 'pickup', 'truck', 'other', 'coupe', 'SUV' (Sport Utility Vehicle), 'hatchback', 'mini van', 'sedan', 'offroad', 'bus', 'van', 'convertible', 'wagon'
   - Description: The vehicle type or body style, providing insights into the car's intended use and design.

5. **Year**
   - Description: The year of car manufacture, representing its age and technology.

6. **Odometer**
   - Description: The distance the car has traveled after purchase, an important indicator of its usage.

# Target Variable: Price

In regression analysis, the target variable we aim to predict is "Price." This variable represents the price of the used car in US dollars. Understanding the factors influencing car prices is crucial for pricing strategies, valuation, and market analysis.

Using these potential features, we can build regression models to predict the price of used cars based on various attributes. These models can provide valuable insights for both buyers and sellers in the used car market.

# Exploratory Data Analysis (EDA)

In order to gain a deeper understanding of the dataset and prepare it for model training, we conducted Exploratory Data Analysis (EDA). EDA provides essential insights into the relationships within the data, guiding us to make informed decisions about methods and model choices.

## Dataset Transformation

The initial dataset shape was (426,880, 26). After addressing null values, duplicates, and eliminating unnecessary columns, the final dataset shape was (338,589, 14).

## Data Analysis and Visualizations

We created various visualizations using Plotly, Matplotlib, and Pandas to better comprehend the dataset and its characteristics.

### Distribution of Car Prices by Condition

![Condition Pie Chart](https://github.com/DATA-606-2023-FALL-TUESDAY/Nagulapelly_Vikas_Reddy/assets/81422237/fa16a49b-695c-4185-9930-04158b337219)

The pie chart visualizes the average prices of used cars grouped by their condition. Notably, "fair" condition cars account for approximately 79% of the total average prices. This suggests that "fair" condition cars dominate the used car market in terms of average price, while other conditions like "good," "excellent," and "like new" constitute smaller percentages.

![Condition Pie Chart 2](https://github.com/DATA-606-2023-FALL-TUESDAY/Nagulapelly_Vikas_Reddy/assets/81422237/77872a27-ba47-411d-9c97-911aa0cc1ba1)

This pie chart illustrates the distribution of used car prices across different condition categories. It reveals that "fair" and "good" condition cars represent the largest shares of the market at 21% and 20%, respectively, indicating that a significant portion of used car stock falls within mid-tier condition categories.

### Price Variation Based on Odometer Readings

![Odometer vs  Price](https://github.com/DATA-606-2023-FALL-TUESDAY/Nagulapelly_Vikas_Reddy/assets/81422237/c3f4e49d-9c10-4b02-b653-1782037a0a2d)

The interactive plot showcases the relationship between odometer readings and prices for different car brands. It suggests that vehicles with higher odometer readings tend to have lower prices, while those with lower odometer readings command higher prices. For instance, Jeep, with the highest selling odometers, exhibits the lowest prices, while Chevrolet, with a narrower odometer range, commands higher prices.

### Price Trends of Cars by Year

![Price Trends by Year](https://github.com/DATA-606-2023-FALL-TUESDAY/Nagulapelly_Vikas_Reddy/assets/81422237/d6321b76-6300-43ad-8921-81cd71d6117a)

The line chart illustrates the average price of used cars grouped by the year of manufacture. It indicates that from the 1990s to the early 2010s, used cars were relatively high in price. This suggests that during this period, older used cars were valued quite highly, possibly due to factors like limited availability, specific model demand, or collector's value. However, there is a noticeable decrease in average prices after the early 2010s, followed by a price increase during the COVID-19 period.

### Cars Price vs. Odometer Reading by Car Type

![Price vs  Odometer by Car Type](https://github.com/DATA-606-2023-FALL-TUESDAY/Nagulapelly_Vikas_Reddy/assets/81422237/e3e13a24-17dc-441e-bf9f-49c8f4eeba6c)

The interactive scatter plot provides insights into the price and odometer reading of cars by car type. It indicates that buyers of Volvo cars tend to prefer SUVs, which are associated with higher prices. Sedans are the next most preferred car type among Volvo buyers.

![Price vs  Odometer by Car Type 2](https://github.com/DATA-606-2023-FALL-TUESDAY/Nagulapelly_Vikas_Reddy/assets/81422237/6d965cc8-5594-4060-9e88-a8ef350c6346)

For Toyota cars, buyers are willing to pay higher prices for trucks, even though the majority of buyers prefer SUVs over other car types.

In our analysis, we explored the relationship between the target variable, "Price," and various features, including condition, odometer, type, year, and fuel. These visualizations help us gain a better understanding of the dataset and its underlying patterns.

# 5. Model Training

In the predictive analytics phase, we will employ various machine learning models to build a regression model for predicting the target variable, "Price." The models we plan to use include:

1. **Linear Regression**
   - Description: Linear regression is a simple yet powerful model that seeks to establish a linear relationship between the input features and the target variable. It is widely used for predicting numeric values and is interpretable.

2. **Random Forest**
   - Description: Random Forest is an ensemble learning method that combines multiple decision trees to create a robust and accurate model. It is known for handling complex relationships and providing feature importance.

3. **Decision Tree**
   - Description: Decision trees are a fundamental model for regression tasks. They split the dataset into subsets based on feature conditions to predict numeric values. Decision trees are interpretable and can handle both linear and nonlinear relationships.

4. **XGBoost Regression**
   - Description: XGBoost is a gradient boosting algorithm that is highly efficient and effective for regression tasks. It optimizes the gradient descent process to minimize the loss function and make accurate predictions.

These models will be trained and evaluated using the dataset, and their performance will be assessed based on metrics such as mean squared error, R-squared, and more. The goal is to determine which model performs best in predicting used car prices based on the selected features.

By utilizing a combination of these models, we aim to provide accurate price predictions that can be valuable for both buyers and sellers in the used car market.

# 6. Comparision of Models
![Models_comparision](https://github.com/DATA-606-2023-FALL-TUESDAY/Nagulapelly_Vikas_Reddy/assets/81422237/ec9494be-721a-45b6-8e79-d7878f891f14)

Random Forest algorithm has the highest R2 score for the test data

# 7. Application of Trained Models

The application of the trained models in our project is manifested through the development of a user-friendly Streamlit web app. This interactive platform empowers users to input specific details about a used car, ranging from its manufacturer and condition to cylinders, fuel type, and various other features. Leveraging the predictive power of our trained models, particularly the Random Forest Regressor, the app dynamically analyzes these inputs and forecasts the estimated price of the car. This application holds immense practical value for both potential buyers and sellers in the used car market. Buyers can make informed decisions based on predicted prices, while sellers can set competitive and fair rates. The intuitive design and seamless user experience of the web app ensure accessibility to a broad audience, bridging the gap between complex machine learning models and end-users, and enhancing the overall transparency and efficiency of the used car trading process.

![Streamlit](https://github.com/DATA-606-2023-FALL-TUESDAY/Nagulapelly_Vikas_Reddy/assets/81422237/6e8c26a8-29ab-41a0-b2c4-64ac771613fc)

# 8. Conclusion and Future Scope

In summary, our project achieved significant success in accurately predicting used car prices. The models, including Decision Tree, Grid Search CV using Decision Tree, and Random Forest Regressor, demonstrated robust performance, providing valuable insights into the dynamic factors influencing pricing.

The emphasis on data preprocessing ensured a refined dataset for training, contributing to the models' effectiveness. The practical implications of our findings extend to both buyers and sellers, fostering a more transparent and informed used car market. 

Looking forward, the project's future scope involves expanding datasets, exploring advanced modeling techniques, and refining user interfaces for broader accessibility.

# 9. References

Videos

https://www.youtube.com/watch?v=VqgUkExPvLY
https://www.youtube.com/@DataThinkers

Articles

https://minaomobonike.medium.com/data-analysis-and-science-of-craigslist-used-car-dataset-cfe8b0147a51
https://pypi.org/project/streamlit/




