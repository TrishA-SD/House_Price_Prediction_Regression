# 🏡 House Price Prediction Regression Model

## 📌 Project Overview
In the real estate industry, accurate estimation of property prices is critical for stakeholders. This project is an end-to-end Machine Learning regression model developed to predict house prices based on various property characteristics. The primary objective was to build two different algorithms: a parametric model (**Multiple Linear Regression**) and a distance-based model (**K-Nearest Neighbors Regressor**).

## 📊 Dataset Details
The dataset consists of **1,000 records** and **8 features**. 
* **Square_Footage**: Size of the house in sq. ft. (Continuous)
* **Num_Bedrooms**: Number of bedrooms (Discrete)
* **Num_Bathrooms**: Number of bathrooms (Discrete)
* **Year_Built**: The year the property was constructed
* **Lot_Size**: Size of the lot in acres
* **Garage_Size**: Car capacity of the garage
* **Neighborhood_Quality**: Rating from 1-10
* **House_Price**: The target variable (Continuous)

## 🛠️ Tech Stack
* **Language:** Python
* **Data Manipulation:** Pandas, NumPy
* **Data Visualization:** Matplotlib, Seaborn
* **Machine Learning:** Scikit-Learn

## 🚀 Methodology
### 1. Exploratory Data Analysis (EDA)
* Conducted univariate analysis using histograms and box plots to understand data distributions. Checked for skewness, finding the target variable to be relatively symmetrical (-0.063).
* Performed bivariate analysis using scatter plots and a correlation heatmap. 
* **Key Insight:** Discovered a massive **0.99 positive linear correlation** between `Square_Footage` and `House_Price`.

### 2. Data Preprocessing
* **Outlier Handling:** The dataset proved to be incredibly clean, resulting in 0.0% outliers removed.
* **Feature Scaling:** Applied `StandardScaler` to numerical variables (e.g., `Lot_Size`, `Square_Footage`) to ensure all features were on an even mathematical scale, which is strictly required for distance-based models like KNN.
* **Data Splitting:** Separated the data into training (80%) and testing (20%) sets to ensure unbiased evaluation.

### 3. Model Training & Hyperparameter Tuning
* **Linear Regression:** Trained as the baseline parametric model.
* **K-Nearest Neighbors (KNN):** Implemented a `for loop` to iterate through $K$ values from 2 to 10. Generated an **Elbow Plot** tracking Root Mean Squared Error (RMSE) to mathematically determine the optimal neighbors, stabilizing at **$K=6$**.

## 📈 Results & Evaluation

| Model | $R^2$ Score | Mean Absolute Percentage Error (MAPE) | Notes |
| :--- | :--- | :--- | :--- |
| **Linear Regression** | **0.998** | 16.6% | **Winner!** Perfect fit due to high data collinearity. |
| **KNN Regressor ($K=6$)** | **0.896** | 15.2% | Highly accurate, optimized via Elbow Plot. |

## 💡 Conclusion & Business Impact
While the optimized K-Nearest Neighbors model performed admirably with nearly 90% accuracy ($R^2 = 0.896$) , the **Multiple Linear Regression model was the undisputed winner** with an $R^2$ score of 0.998.Because the exploratory data analysis revealed a near-perfect linear relationship between house size and price (0.99 correlation), the simpler parametric model proved to be the most effective. For House owners, Linear Regression is highly recommended here, as it is not only computationally lighter but also provides easily interpretable coefficients (e.g., knowing exactly how much value one extra bedroom adds).
