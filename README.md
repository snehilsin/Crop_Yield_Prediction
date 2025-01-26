# Crop Yield Prediction Using Machine Learning

# Source of Data 
All dataset(publicly available dataset) here are taken form FAO (Food and Agriculture Organization) and World Data Bank.
http://www.fao.org/home/en/
https://data.worldbank.org/

# Dataset Overview:
This dataset consists of 8 columns and 28,242 entries. Here's a breakdown of each column:

1. Unnamed: 0: Appears to be an index column. It can be dropped as it duplicates row indices.
2. Area: Represents the country or region (e.g., "India", "Albania").
3. Item: Specifies the type of crop (e.g., "Maize", "Potatoes").
4. Year: The year of data collection (1990–2013).
5. hg/ha_yield: Crop yield in hectograms per hectare.
6. average_rain_fall_mm_per_year: Annual average rainfall in millimeters for the area.
7. pesticides_tonnes: Amount of pesticides used in tonnes.
8. avg_temp: Average temperature of the area in degrees Celsius.


# Relationships Between Columns:
# 1.Yield vs. Area, Item, and Year:

Yield (dependent variable) will vary by region, crop type, and year due to local climatic, economic, and agricultural conditions.
Analyzing trends over the years for specific regions or crops may highlight changes due to technological advancements, climate change, or policy interventions.
# 2.Yield vs. Average Rainfall:

Adequate rainfall is essential for crop growth. Too much or too little rainfall may negatively impact yield.
Correlation analysis can reveal the strength and nature of this relationship.
# 3.Yield vs. Pesticide Usage:

Pesticides may boost yield by reducing crop losses to pests, but excessive use could lead to diminishing returns or environmental harm.
Investigate whether pesticide use exhibits diminishing returns or thresholds for optimal use.
# 4.Yield vs. Average Temperature:

Temperature significantly affects crop growth stages, such as germination and ripening. Extreme temperatures can reduce yields.
The relationship may vary for different crops (e.g., maize vs. potatoes) due to specific temperature tolerances.
# 5.Cross-Relationships:

Rainfall and temperature are often interrelated. Including interaction terms in modeling may improve predictions.
Different crops may respond differently to the same environmental factors, making crop type a crucial categorical variable.

The dataset contains data for 101 countries and 10 different crops.

# Tech Stack
# Python:

The primary programming language used for data preprocessing, model building, and evaluation due to its extensive libraries and ease of use.
# Jupyter Notebook:

Used as the development environment to write and execute the code interactively while visualizing outputs.
# Libraries Used
# Data Manipulation and Cleaning:

# Pandas: 
To handle the large dataset efficiently, perform preprocessing tasks, clean missing and duplicate values, and analyze features.
# NumPy: 
For numerical operations like handling arrays and type conversion.
# Data Visualization:

## Seaborn: 
To create visually appealing graphs like bar plots and count plots for analyzing trends.
## Matplotlib: For creating custom plots to complement Seaborn’s capabilities.
## Machine Learning:

Scikit-learn
## Preprocessing: 
Used tools like StandardScaler for feature scaling and OneHotEncoder for handling categorical variables.
## Modeling:
Included several regression algorithms like Linear Regression, Ridge, Lasso, and Decision Tree Regressor.
## Metrics: 
Utilized mean_absolute_error and r2_score to evaluate model performance.
# Machine Learning Models Used
## Linear Regression:

A baseline regression model used to predict crop yields.
Strength: Simple and interpretable.
Limitation: Did not perform well due to the dataset's non-linear relationships.
## Lasso Regression:

Adds L1 regularization to Linear Regression to reduce overfitting.
Outcome: Performed slightly better but still lacked the ability to model non-linearity effectively.
## Ridge Regression:

Adds L2 regularization to Linear Regression to address overfitting by penalizing large coefficients.
Outcome: Similar performance to Lasso Regression.
## Decision Tree Regressor:

Captured non-linear relationships between features and the target variable (crop yield).
Outcome: Achieved the best performance with a Mean Absolute Error (MAE) of 3,956 and R² score of 0.978, making it the final model.
# Key Features of the Preprocessing Pipeline
## ColumnTransformer:

Combined scaling for numerical features and one-hot encoding for categorical features into a unified preprocessing pipeline.
## Train-Test Split:

Ensured a balanced evaluation of the models by using an 80-20 train-test split.
## Custom Prediction System:

A function that accepts user input (Year, Rainfall, Area, Crop Type, etc.), preprocesses it using the trained pipeline, and predicts crop yield using the Decision Tree Regressor.
# Future Enhancements to Tech Stack
Consider integrating Random Forest for even better accuracy.
Deploy the model as a web app using frameworks like Flask or Django for real-world usability.

# Challenges Faced

## 1. Data Quality Issues
Challenge: The dataset had duplicates and non-numeric values in the average_rain_fall_mm_per_year column, which could skew the analysis and model performance.
### Solution:
Removed duplicate rows, reducing the dataset from 28,242 to 25,932 rows.
Implemented a custom function to identify and drop non-numeric values in the rainfall column, ensuring the data was clean and consistent.
## 2. Categorical Encoding and Feature Scaling
### Challenge: 
The dataset included categorical features (Area and Item) that needed to be transformed into numerical values for model training. Additionally, features had varying scales, which could negatively impact certain models.
### Solution:
Used OneHotEncoding to handle categorical variables, expanding them into multiple binary columns while avoiding multicollinearity by dropping the first category.
Applied StandardScaler to scale numeric features (Year, average_rain_fall_mm_per_year, pesticides_tonnes, avg_temp), ensuring all features contributed equally during model training.
## 3. Model Selection and Evaluation
### Challenge: 
Determining the best model for predicting crop yields required experimenting with various algorithms (Linear Regression, Ridge, Lasso, and Decision Tree Regressor). Some models showed low accuracy due to the non-linearity of the data.
### Solution:
Tested multiple models and evaluated them using metrics like Mean Absolute Error (MAE) and R² Score.
The Decision Tree Regressor outperformed others with an MAE of 3,956 and an R² score of 0.978, demonstrating its ability to handle the dataset’s non-linear relationships effectively.
## 4. Handling High Dimensionality
### Challenge: 
One-hot encoding created a large number of additional columns (e.g., 101 for Area and multiple for Item), increasing the dataset's dimensionality and computational cost.
### Solution: 
Efficiently handled high-dimensional data by using the ColumnTransformer to preprocess only relevant features, ensuring the pipeline was computationally manageable.
## 5. Prediction System
### Challenge: 
Integrating preprocessing steps (scaling and encoding) with the predictive model in a seamless pipeline for future predictions was tricky, especially with categorical variables.
### Solution: 
Built a prediction function that applied preprocessing steps to raw inputs before feeding them into the trained Decision Tree model, ensuring accurate predictions.

# Internship Completion Certificate
https://drive.google.com/drive/folders/1Trh5DtAKdohBhFtJD2lH3J57ZKD5Xqft

# About Amity Software Systems Ltd.

www.amitysoftware.com
Noida, India
201 to 500 Employees
Type: Company - Private
Founded in 1986
Revenue: $1 to $5 million (USD)
Software Development

Amity Software stepped into the game of modernizing business processes through cutting-edge technologies. We offer reliable e-governance solutions, insurance software, SAP services, agriculture management system, weighing solutions, and mobile app development services. Our digital solutions enable automation and ensure tasks are completed on time.

1. Drive innovation in the services we offer.
2. Offer a helping hand to make the business processes better.
3. Interact with clients directly to comprehend and analyze the requirements.
