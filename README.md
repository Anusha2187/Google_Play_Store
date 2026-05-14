# Google Play Store App Analytics & Rating Prediction

## Project Overview
This project analyzes Google Play Store application data to understand patterns in app ratings, reviews, installs, pricing, app categories, and content ratings. The project includes data cleaning, exploratory data analysis, feature engineering, database preparation, and machine learning models to predict app rating categories. This helps developers chose categories that can possibly receive higer ratings. This can then be considered as an indication for predicting increased downloads and higher reveneus for the apps that receive higher ratings.

## Objective
The goal of this project is to identify factors that influence app ratings and build machine learning models that can classify/predict app rating levels based on app metadata such as reviews, installs, size, type, price, category, and content rating.

## Dataset
The dataset used is `googleplaystore.csv`, containing Google Play Store app information including:

- App name
- Category
- Rating
- Reviews
- Size
- Installs
- Type
- Price
- Content Rating
- Last Updated
- Current Version
- Android Version

## Key Steps Performed

### 1. Data Cleaning
- Removed invalid rating outliers above 5
- Handled missing values in `Rating`, `Type`, `Current Ver`, and `Android Ver`
- Converted `Reviews`, `Installs`, `Price`, and `Size` into numeric formats
- Removed symbols such as `+`, `,`, and `$`
- Converted `Last Updated` into datetime format
- Renamed columns for SQL compatibility

### 2. Exploratory Data Analysis
- Checked missing value percentages
- Generated summary statistics for app ratings
- Used boxplots to detect outliers
- Grouped app categories by average rating, total price, and average reviews

### 3. Feature Engineering
- Applied one-hot encoding to app categories
- Mapped app type into binary values: Free = 0, Paid = 1
- Encoded content rating categories
- Scaled features using MinMaxScaler
- Rounded ratings for classification modeling

### 4. Machine Learning Models
Several classification models were tested to predict app rating levels:

- Decision Tree Classifier
- Random Forest Classifier
- K-Nearest Neighbors
- Logistic Regression
- Linear Support Vector Classifier

Model performance was evaluated using:
- Accuracy score
- Train/test split
- Cross-validation
- Confusion matrices
- GridSearchCV for hyperparameter tuning

## Tools & Technologies
- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- MySQL Connector
- Google Colab
- Jupyter Notebook

## Business Value
This analysis can help app developers, product managers, and marketplace analysts understand which app characteristics are associated with higher user ratings and stronger marketplace performance. The model can also support early-stage app benchmarking by estimating expected rating outcomes based on app metadata.

## Key Insights
- App ratings required cleaning because the dataset included invalid values above the expected 1–5 rating range.
- Installs, reviews, price, category, and content rating were transformed into model-ready features.
- Multiple classification models were compared to evaluate which approach best predicts app rating categories.
- Random Forest and Decision Tree models were useful for capturing nonlinear patterns in app marketplace data.

## Future Improvements
- Add more visualizations for category-level rating trends
- Include feature importance analysis from Random Forest
- Improve content rating encoding to include all content rating classes
- Add model comparison table with final accuracy scores
- Fix minor code issues and standardize variable names
- Save cleaned data and trained models for reuse
- Build a simple dashboard using Streamlit or Tableau
- Add business recommendations for app developers

## Repository Structure
```text
google-play-store-analytics/
│
├── README.md
├── Google_Play_Store_Project.ipynb
├── googleplaystore.csv
├── requirements.txt
├── images/
│   ├── rating_distribution.png
│   ├── category_analysis.png
│   └── confusion_matrix.png
└── output/
    └── cleaned_play_store_data.xlsx


