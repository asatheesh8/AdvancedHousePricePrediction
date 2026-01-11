# Advanced House Price Prediction

Lifecycle of a Data Science Project Involves:
* Exploratory Data Analysis
* Feature Engineering
* Feature Selection
* Model Building
* Model Deployment

This project covers Exploratory Data Analysis (EDA), Feature Engineering, and Feature Selection on Advanced House Price Prediction Dataset.

##
<details>
    <summary><strong> 1 - Exploratory Data Analysis (EDA) </strong></summary>
In EDA, we try to find out:

* Missing Values
* All Numerical Variables
* Distribution of Numerical Variables
* Categorical Variables
* Cardinality of Categorical Variables
* Outliers
* Relationship between independent and dependent feature (SalePrice)

A) Missing Values
* List all features with missing values and the percentage of missing values.
* Since there are a lot of missing values, the relationship between these values and the dependent feature is plotted.
* Missing values are imputed with MEDIAN (for numerical) and 'Missing' (for categorical).

B) Numerical Features
* List all numerical features.
* List all features with temporal values and simplify them.
* Analyse Continuous and Discrete variables separately:
    * Discrete : Bar plots
    * Continuous : Histogram. If it is skewed log normalise it.
    * Check for outliers with boxplot after normalising.

C) Categorical Features
* Plot bar charts to see distribution.

</details>

##
<details>
    <summary><strong> 2 - Feature Engineering </strong></summary>

Steps followed in Feature Engineering:
* Missing Values
* Temporal Variables
* Categorical Variables (remove rare labels)
* Standardize values

A) Categorical with NaN values - replace with new label.

B) Numerical (Discrete) variables with NaN values - Replace with median values.
* Create a new field that acts like a flag for these missing records that got imputed.

C) Numerical (Continuous) Variables - apply log normalisation.

D) Handling Rare Categorical Features - Replace labels with less than 1% occurance with 'Rare_var'.

Use Ordinal Encoding for categorical features and scale the features to prepare them for Model Training.

</details>

##
<details>
    <summary><strong> 3 - Feature Selection </strong></summary>

Read the training dataset and assign X (independent features) and y (dependent feature - to be trained to predict).

Lasso Regression with alpha (penalty - bigger alpha = less features) selected.

SelectFromModel to select features with non-zero coefficients.

Apply these and fit to X_train and y_train.

Get support - True (important) / False (not important)

Train the model over these selected features in Model Training.

</details>