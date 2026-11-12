# Predicting Student Grades: A Regression Analysis of Socioeconomic Factors 📚

**Author:** Claudia dela Paz 
**Course:** CIS468

## 📌 Project Overview
Academic success is traditionally measured using past performance, which frequently masks the underlying environmental and behavioral drivers that influence a student's trajectory. The primary objective of this project is to evaluate the independent predictive power of non-academic variables, specifically financial resources, study habits, and parental involvement, on a secondary student's final grade percentage. 

By excluding previous academic history, this regression analysis tests whether machine learning models can reliably forecast academic outcomes based strictly on a student's socioeconomic and behavioral background.

## 📊 Dataset Features
This project utilizes a simulated survey dataset of 12,000 secondary-school students sourced from Kaggle. The target variable is the continuous `final_grade_pct`. The predictive features used in this analysis are:
* `study_hours_per_week`
* `attendance_rate_pct`
* `annual_family_income_inr`
* `parental_involvement_score`
* `distance_to_school_km`

⚠️ **Data Note:** The Kaggle dataset used in this analysis is entirely **synthetic (simulated survey data)**. While this project successfully demonstrates a robust machine learning methodology and data science pipeline, the specific predictive accuracies cannot be guaranteed to generalize identically to real-world high school student populations.

## 🛠️ Methodology & Models
The project pipeline includes Exploratory Data Analysis (EDA) using correlation heatmaps and pairwise scatter plots, followed by data preprocessing and feature scaling. An 80/20 holdout method and 5-Fold Cross-Validation were used to train and test the following regression algorithms:
1. **Multiple Linear Regression (Baseline)**
2. **Random Forest Regressor (with AI-assisted GridSearchCV tuning)**
3. **K-Nearest Neighbors (KNN) Regression**

## 🏆 Key Results

| Regression Model | R-squared ($R^2$) | Mean Absolute Error (MAE) |
| :--- | :--- | :--- |
| **Multiple Linear Regression** | **0.1026** | **8.6675** |
| **Random Forest** | 0.0306 | 8.9614 |
| **K-Nearest Neighbors (KNN)** | -0.0573 | 9.4546 |

**Conclusion:** 
Multiple Linear Regression achieved the best overall performance, demonstrating that simple linear models are better equipped to handle noisy behavioral data without overfitting. However, the models only explained roughly 10% of the variance in student grades. The advanced Random Forest model overfit the data, while the distance-based KNN model failed entirely (scoring a negative $R^2$). 

Ultimately, this analysis highlights that socioeconomic and environmental metrics alone are insufficient standalone predictors for academic success. Students with nearly identical socioeconomic backgrounds frequently achieve vastly different academic outcomes.

## 🚀 How to Run the Project
1. Clone this repository.
2. Ensure the `student_grade_ses_dataset.csv` file is in the same directory as the notebook (or adjust the file path accordingly).
3. Run the `DELAPAZ_HW2.ipynb` notebook to view the EDA, model training, and performance visualizations.

*Note: Generative AI was utilized as a coding assistant to design the GridSearchCV hyperparameter tuning pipeline for the Random Forest model.*
