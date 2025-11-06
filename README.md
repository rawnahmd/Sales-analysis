# Sales-analysis
analyzes Amazon product and sales data to uncover insights about customer behavior, product performance, and review sentiment.

## 📑 Table of Contents

- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Tools](#tools)
- [Data Cleaning/Preparation](#data-cleaningpreparation)
- [Exploratory Data Analysis (EDA)](#exploratory-data-analysis)
- [Data Analysis](#data-analysis)
- [Results/Findings](#resultsfindings)
- [Recommendations](#recommendations)
- [References](#-references)


## Project Overview

This project focuses on analyzing Amazon product and review data using Python.
The goal is to clean, preprocess, and visualize product-related information to extract meaningful insights about pricing, ratings, and product performance.

The analysis demonstrates practical data wrangling, visualization, and preprocessing techniques essential for any data science or machine learning pipeline.

## Data Sources 

Amazon Sales data : The primary dataset used for this analysis is the "amazon.csv" file , containing detailed information about each sale done .

##Tools

- Excel - Data cleaning [Download here](https://microsoft.com)
- Programming Language: Python
- Libraries:
  - pandas → Data manipulation and cleaning
  - numpy → Numerical operations
  - matplotlib → Data visualization
  - sklearn.preprocessing.LabelEncoder → Encoding categorical columns

## Data Cleaning/Preparation

In this initial data preparation phase , we performed the following :
1. Data loading and inspection .
2. Handling missing values . 
3. Data cleaning and formatting . 
4. Handling wrong values and duplicates .

## Exploratory Data Analysis 

EDA involved exploring the sales data to answer key questions , such as :
- what is unusually high/low prices
- what is actual_price vs. rating
- what is distribution of actual_price
- What are the Top 5 categories based with highest ratings?
- What are the most popular product reviews?
- What are the most popular product name?

## Data Analysis

### Some important code/features worked with :

-Plot distribution of actual_price
```python
import matplotlib.pyplot as plt
plt.figure(figsize=(8,5))
plt.hist(df['actual_price'], bins=30)
plt.title("Distribution of Actual Prices")
plt.xlabel("Price")
plt.ylabel("Frequency")
plt.show()
```
- Top 5 Categories by Average Rating
```python
top_categories = df.groupby('category')['rating'].mean().sort_values(ascending=False).head(5)
top_categories.plot(kind='bar', color='orange', figsize=(7,4))
plt.title("Top 5 Categories by Average Rating")
plt.ylabel("Average Rating")
plt.show()
```

- Most Popular Products by Review Count
```python
popular_products = df['product_name'].value_counts().head(5)
print(popular_products)
```

- Correlation between Price and Rating
```python
correlation = df['actual_price'].corr(df['rating'])
print("Correlation between Price and Rating:", correlation)
```
## Results/Findings 

- Categories with moderate prices tend to receive higher ratings.

- Some products have consistently high reviews, showing brand trust.

- Label encoding simplified processing for further ML tasks.

- Certain categories dominate both in price and customer satisfaction.
  
- There’s a weak positive correlation between actual_price and rating, meaning expensive products don’t always guarantee higher ratings.
  
- Products with detailed descriptions and more reviews tended to rank higher, showing the importance of customer feedback.

## Recommendations

Based on the analysis, the following actions are recommended for business and future data projects:

1. Optimize Pricing Strategy
2. Focus on Top-Rated Categories
3. Implement Sentiment Analysis
4. Interactive Dashboard

## 📚 References  
- [Kaggle Datasets](https://www.kaggle.com/datasets) – Inspiration for Amazon sales datasets  


