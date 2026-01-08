# Laptop Price Prediction – Model Development

This project is a Jupyter notebook that focuses on **building and evaluating machine learning models** to predict laptop prices from hardware and display specifications. [file:90]

It follows earlier data‑wrangling and exploratory analysis steps and uses the cleaned laptop dataset to train regression models and assess their performance. [file:90]

---

## Dataset

- Shape: **238 rows × 16 columns**. [file:90]  
- Example columns used as features/target:  
  - Categorical / encoded:  
    - `Manufacturer` (e.g., Acer, Dell, HP, Lenovo, Toshiba).  
    - `Category` (encoded product segment).  
    - `GPU` (encoded GPU class).  
    - `OS` (encoded operating system).  
    - `Price-binned` (e.g., `Low`, `Medium` buckets – mainly for inspection, not the main target).  
    - `Screen-Full_HD` (binary flag).  
    - `Screen-IPS_panel` (binary flag). [file:90]  
  - Numeric:  
    - `CPU_core` (number of CPU cores, encoded).  
    - `Screen_Size_inch`.  
    - `CPU_frequency` (normalized CPU clock).  
    - `RAM_GB`.  
    - `Storage_GB_SSD`.  
    - `Weight_pounds`.  
    - `Price` (target variable for regression). [file:90]  

---

## Notebook overview

### 1. Load and prepare data

- Loads the processed laptop dataset into a pandas DataFrame.  
- Confirms feature types and ensures the target variable `Price` is numeric and free of missing values. [file:90]  
- Selects relevant feature columns (hardware and display attributes) and defines `X` (features) and `y` (Price). [file:90]  

### 2. Train–test split

- Splits the data into **training and test sets** to evaluate model generalization.  
- Uses scikit‑learn style `train_test_split` (implied by the later use of `LinearRegression`). [file:90]  

### 3. Baseline regression model

- Trains a **Linear Regression** model (`LinearRegression()`) on the training data.  
- Fits the model multiple times (for different feature subsets or experiments), as shown by repeated `LinearRegression()` outputs in the notebook. [file:90]  
- Uses the trained model to predict prices on the test set. [file:90]  

### 4. Model evaluation

- Evaluates regression performance using standard metrics such as:  
  - Mean Squared Error (MSE) or Root Mean Squared Error (RMSE).  
  - Coefficient of determination \(R^2\).  
- Compares the model’s predictions to actual prices to assess how well hardware specs explain price variation. [file:90]  

### 5. Feature impact (coefficients)

- Inspects model coefficients to understand how each feature (e.g., `CPU_core`, `RAM_GB`, `Storage_GB_SSD`, `Screen-Full_HD`, `Screen-IPS_panel`, `Weight_pounds`) influences predicted price.  
- Interprets which features have the strongest positive or negative association with price in the linear model. [file:90]  

---

## Key ideas and outcomes

- Demonstrates a full **supervised learning workflow**: feature selection, train–test split, model training, and evaluation, applied to real laptop pricing data. [file:90]  
- Shows how hardware configuration (CPU cores, RAM, SSD size, GPU class) and screen characteristics contribute to price differences captured by a regression model. [file:90]  
- Provides a baseline linear model that can be extended with regularization (Ridge/Lasso), tree‑based models, or hyperparameter tuning in future work. [file:90]  

---

## Technologies used

- Python  
- pandas and NumPy for data handling. [file:90]  
- scikit‑learn for model development (LinearRegression, train–test split, metrics). [file:90]  
- Jupyter Notebook for experimentation and analysis. [file:90]  

