# Used_Car_Price_Polynomial_Regression
Machine Learning project for predicting used car selling prices using Polynomial Regression, Ridge Regularization, feature engineering, and hyperparameter tuning.
# Used Car Price Prediction Using Polynomial Regression

## 📌 Project Overview

This project focuses on predicting the selling price of used cars using Machine Learning.

The project uses **Polynomial Regression with Ridge Regularization** to capture nonlinear relationships between vehicle characteristics and selling price.

The model is trained using historical used-car data and evaluated using regression metrics such as **MAE, RMSE, and R² Score**.

---

## 🎯 Objective

The main objective of this project is to build a machine learning model that can estimate the selling price of a used car based on its specifications and usage information.

The model considers factors such as:

* Car brand
* Car age
* Kilometres driven
* Mileage
* Engine capacity
* Maximum power
* Torque
* Number of seats
* Fuel type
* Seller type
* Transmission
* Previous ownership

---

## 💡 Problem Statement

Determining the appropriate selling price of a used car can be difficult because the price depends on multiple factors.

Traditional price estimation may not properly capture the relationships between vehicle characteristics.

This project uses machine learning to learn these relationships from historical data and predict the expected selling price of a vehicle.

---

## 🧠 Machine Learning Approach

This project follows a complete machine learning workflow:

```text
Raw Dataset
     ↓
Data Understanding
     ↓
Data Cleaning
     ↓
Missing Value Handling
     ↓
Feature Engineering
     ↓
Categorical Encoding
     ↓
Feature Scaling
     ↓
Polynomial Feature Generation
     ↓
Ridge Regression
     ↓
Hyperparameter Tuning
     ↓
5-Fold Cross Validation
     ↓
Model Evaluation
     ↓
Price Prediction
```

---

## 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Scikit-learn
* Google Colab
* Git
* GitHub

---

## 📊 Dataset

The project uses a used-car dataset containing information about vehicle specifications, usage, and selling prices.

Important columns include:

* `name`
* `year`
* `selling_price`
* `km_driven`
* `fuel`
* `seller_type`
* `transmission`
* `owner`
* `mileage`
* `engine`
* `max_power`
* `torque`
* `seats`

The raw dataset is not included in this repository if redistribution is not permitted by its source/license.

See:

```text
data/README.md
```

for dataset setup instructions.

---

## 🧹 Data Preprocessing

The following preprocessing techniques are used:

### Missing Value Handling

Numerical missing values are handled using mean imputation.

### Duplicate Removal

Duplicate records are identified and removed.

### Numerical Conversion

Values stored as text, such as:

```text
18.9 kmpl
1197 CC
74 bhp
```

are converted into numerical values.

### Categorical Encoding

Categorical features are converted using One-Hot Encoding.

### Feature Scaling

Numerical features are standardized using StandardScaler.

---

## 🔧 Feature Engineering

Several new features are created to improve the model.

### Car Age

```python
car_age = 2026 - year
```

### Kilometres Per Year

```python
km_per_year = km_driven / car_age
```

### Power Per Engine

```python
power_per_engine = max_power / engine
```

### Engine Per Seat

```python
engine_per_seat = engine / seats
```

### Brand Extraction

The first word from the vehicle name is extracted as the car brand.

For example:

```text
Maruti Swift Dzire
        ↓
Maruti
```

---

## 📈 Why Polynomial Regression?

A simple Linear Regression model assumes a mostly linear relationship between the input features and selling price.

However, used-car prices can have nonlinear relationships with:

* Car age
* Mileage
* Engine size
* Maximum power
* Kilometres driven

Polynomial Regression allows the model to capture nonlinear relationships and interactions between numerical features.

For example:

```text
X
X²
X₁ × X₂
```

can be generated from the original numerical features.

---

## 🛡️ Why Ridge Regression?

Polynomial feature expansion increases the number of features and can cause overfitting.

Ridge Regression applies L2 regularization to control model complexity.

Therefore, the final approach is:

```text
Polynomial Features
        +
Ridge Regression
        ↓
Polynomial Ridge Regression
```

---

## ⚙️ Hyperparameter Tuning

GridSearchCV is used to select the best combination of:

### Polynomial Degree

```text
1
2
3
```

### Ridge Alpha

```text
0.01
0.1
1
10
100
```

The combinations are evaluated using 5-fold cross-validation.

---

## 📏 Model Evaluation

The following metrics are used:

### MAE

Mean Absolute Error measures the average absolute difference between actual and predicted prices.

Lower MAE is better.

### RMSE

Root Mean Squared Error gives greater importance to larger prediction errors.

Lower RMSE is better.

### R² Score

R² measures how much variation in the target variable is explained by the model.

The final model achieved approximately:

```text
Test R² ≈ 0.866
```

This means the model explains approximately **86.6% of the variation in used-car selling prices on the test dataset**.

> Note: R² is a regression metric and should not be described as classification accuracy.

---

## 📊 Results

The project includes visualizations for:

* Actual vs Predicted Prices
* Residual Analysis
* Polynomial Degree Comparison

These visualizations help evaluate how well the model generalizes to unseen data.

---

## 📁 Project Structure

```text
Used_Car_Price_Polynomial_Regression/
│
├── README.md
├── notebooks/
│   └── Used_Car_Price_Polynomial_Regression.ipynb
│
├── results/
│   ├── actual_vs_predicted.png
│   ├── residual_plot.png
│   └── polynomial_degree_comparison.png
│
├── data/
│   └── README.md
│
├── requirements.txt
├── .gitignore
└── LICENSE
```

---

## ▶️ How to Run

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/Used_Car_Price_Polynomial_Regression.git
```

### 2. Open the notebook

Open:

```text
notebooks/Used_Car_Price_Polynomial_Regression.ipynb
```

using Google Colab or Jupyter Notebook.

### 3. Add the dataset

Download the dataset from its original source and place the CSV according to the instructions in:

```text
data/README.md
```

### 4. Install dependencies

```bash
pip install -r requirements.txt
```

### 5. Run the notebook

Execute the notebook cells from top to bottom.

---

## 🚀 Future Improvements

Possible improvements include:

* Build a Streamlit web application
* Add additional car datasets
* Compare Polynomial Regression with Random Forest and Gradient Boosting
* Add model explainability
* Deploy the prediction application
* Add automated model retraining
* Create an API for price prediction

---

## 👨‍💻 Author

**Sanjay R.**

B.Tech – Artificial Intelligence and Data Science

---

## ⭐ Conclusion

This project demonstrates an end-to-end machine learning workflow for used-car price prediction, including data preprocessing, feature engineering, polynomial feature generation, Ridge regularization, hyperparameter tuning, cross-validation, and model evaluation.
