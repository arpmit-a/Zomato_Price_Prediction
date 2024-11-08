# Restaurant Rating Prediction - Zomato Bangalore

This project aims to predict restaurant ratings for Bangalore's Zomato dataset by applying machine learning algorithms and comparing model performances. We explored various regressors to find the best model for accurate rating prediction.

## Contributors

- Master

---

## Table of Contents

- [Data Cleaning](#data-cleaning)
- [Model Training and Evaluation](#model-training-and-evaluation)
- [Model Comparison](#model-comparison)
- [Model Saving](#model-saving)
- [Usage](#usage)

---

## Data Cleaning

1. **Importing Libraries**: Libraries such as Pandas, Numpy, Matplotlib, Seaborn, and more were imported to facilitate data manipulation and visualization.
2. **Loading Dataset**: The dataset is read from `zomato.csv`.
3. **Removing Unwanted Columns**: Dropped columns that are irrelevant to rating prediction, such as `url`, `address`, `phone`, etc.
4. **Renaming Columns**: Renamed columns for clarity (e.g., `rate` to `Rating`, `approx_cost(for two people)` to `Cost`).
5. **Handling Missing Values**: Null values were handled by removing columns with excessive missing data and dropping rows with remaining null values.
6. **Data Cleaning**:
   - Processed `Rating` to remove unwanted text.
   - Converted `Cost` from strings to float.
   - Cleaned restaurant names for unnecessary characters.

The cleaned dataset was saved as `zomatoclean_final.xlsx` for model training.

---

## Model Training and Evaluation

### Encoding Categorical Features

Label encoding was applied to categorical columns (`book_table`, `online_order`, `cuisines`, `rest_type`, and `City`).

### Splitting Data

The data was split into training and testing sets with a 90-10 split.

### Model Training

Three different regressors were trained to predict restaurant ratings:

1. **XGBoost Regressor**  
   - Model Score (Test): r² = 0.735, MSE = 0.052

2. **Extra Tree Regressor**  
   - Model Score (Test): r² = 0.902, MSE = 0.019

3. **Random Forest Regressor**  
   - Model Score (Test): r² = 0.904, MSE = 0.019

### Model Comparison

| Models         | r² Score (Train) | MSE (Train) | r² Score (Test) | MSE (Test) |
|----------------|------------------|-------------|-----------------|------------|
| XGBoost       | 0.782            | 0.042       | 0.735           | 0.052      |
| Extra Tree    | 0.999            | 0.0001      | 0.902           | 0.019      |
| Random Forest | 0.986            | 0.0027      | 0.904           | 0.019      |

The **Random Forest Regressor** achieved the best performance, with the highest r² score and lowest MSE on test data.

---

## Model Saving

The best model (Random Forest Regressor) was saved using `pickle` for future use. Label encoders for categorical variables were also saved.

### Files Saved
- **best_model.sav**: Contains the trained Random Forest model.
- **encoder_book_table.sav**, **encoder_city.sav**: Contains encoders for categorical columns.

---

## Usage

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/your-repo-name
