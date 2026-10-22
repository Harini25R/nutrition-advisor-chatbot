# Nutrition Advisor Chatbot

A personalized diet recommendation chatbot that groups users by BMI and BMR using K-Means clustering and suggests calorie ranges and meals from USDA FoodData Central nutrition data.

Developed as an MSc Data Science project at NMKRV College for Women.

[Open the notebook in Google Colab](https://colab.research.google.com/drive/1jULOtCj2bdPRjB2tvaQkGhaZCHoD2Lbe?usp=sharing)

## Overview

Generic diet plans ignore individual differences in body metrics and activity level. This project builds a data-driven advisor that:

1. Collects a user's weight, height, activity level and dietary goal.
2. Calculates BMI and BMR.
3. Assigns the user to a dietary cluster.
4. Recommends a daily calorie range and a breakfast, lunch and dinner suggestion from USDA food data.

## Data

- **User dietary data:** survey responses covering age, gender, height, weight, activity level, dietary goal and food allergies.
- **USDA nutrition data:** food items scraped from USDA FoodData Central (calories, protein, cholesterol, food category and more).

## Methodology

- **Preprocessing:** duplicate removal, median imputation for missing age/weight/height, outlier handling (Z-score and IQR), scaling, and encoding of categorical variables.
- **Feature engineering:** BMI and BMR (Mifflin-St Jeor equation).
- **Clustering:** K-Means and Hierarchical (Ward's method) clustering, with the number of clusters chosen using the Elbow Method and Silhouette Score (k = 3).
- **Recommendation logic:** each cluster maps to a goal (weight gain, maintenance or loss). Calorie ranges are adjusted by BMI category, activity level and goal, and meals are filtered from the USDA dataset by nutrition category.

## Results

- K-Means grouped users into three clusters based on BMI and BMR.
- Silhouette score: **0.895** (K-Means and Hierarchical performed equally).
- K-Means was chosen for its speed, scalability and easier interpretation.

## Tech stack

Python, Pandas, NumPy, Scikit-learn, BeautifulSoup, Matplotlib, Google Colab

## How to run

1. Open the notebook in Google Colab (link above) or download it from this repository.
2. Place `food_dataset.csv` in the same folder.
3. Run all cells. The chatbot asks for your weight, height, activity level and goal in the console, then prints your BMI, cluster, calorie range and meal plan.

## Limitations and future work

- Cluster assignment currently relies on BMI and BMR only.
- Meal suggestions are filtered from the dataset and are not a substitute for advice from a doctor or dietitian.
- Planned: real-time API updates, user feedback to adjust clusters, and deep learning-based clustering.

## Author

Harini R | MSc Data Science | [GitHub](https://github.com/Harini25R)
