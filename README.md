# 🫀 Heart Disease Prediction using Machine Learning

## 📌 Project Overview

This project focuses on preparing and analyzing a heart disease dataset for a Machine Learning classification problem.

The main objective is to explore patient health-related data, perform data cleaning and preprocessing, engineer meaningful features, and prepare the dataset for building a Machine Learning model that can predict the presence of heart disease.

The project follows a step-by-step Machine Learning workflow starting from **Exploratory Data Analysis (EDA)** and data cleaning to **feature engineering** and **feature scaling**.

---

## 🎯 Objective

The primary objectives of this project are:

- Analyze the heart disease dataset
- Understand the structure and distribution of the data
- Identify missing or invalid values
- Perform data cleaning and preprocessing
- Analyze relationships between features and heart disease
- Convert categorical variables into numerical form
- Perform feature engineering
- Scale numerical features
- Prepare the final dataset for Machine Learning classification

---

## 📂 Dataset

The dataset used in this project is `heart.csv`.

### 🎯 Target Variable

The target variable is `HeartDisease`.

| Value | Meaning |
|---|---|
| `0` | No Heart Disease |
| `1` | Heart Disease |

### 📋 Features

The dataset contains the following patient health-related features:

- `Age`
- `Sex`
- `ChestPainType`
- `RestingBP`
- `Cholesterol`
- `FastingBS`
- `MaxHR`
- `ExerciseAngina`
- `Oldpeak`
- `RestingECG`
- `ST_Slope`
- `HeartDisease`

---

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Python | Programming language |
| Jupyter Notebook | Development environment |
| Pandas | Data manipulation and analysis |
| NumPy | Numerical operations |
| Matplotlib | Data visualization |
| Seaborn | Statistical visualization |
| Scikit-learn | Machine Learning preprocessing |

---

# 🔍 Exploratory Data Analysis

Exploratory Data Analysis (EDA) was performed to understand the dataset before applying Machine Learning techniques.

The following aspects were analyzed:

- Dataset shape
- Column names
- Data types
- Missing values
- Duplicate records
- Statistical summary
- Target variable distribution
- Numerical feature distributions
- Categorical feature distributions
- Relationships between features and the target variable
- Correlation between numerical features

### 📊 Visualizations

Different plots were used during EDA, including:

- Histograms
- Count plots
- Box plots
- Violin plots
- Correlation heatmap

Examples of relationships explored include:

- Sex vs Heart Disease
- Chest Pain Type vs Heart Disease
- Fasting Blood Sugar vs Heart Disease
- Cholesterol vs Heart Disease
- Age vs Heart Disease

---

# 🧹 Data Cleaning

During the analysis, some records contained `0` values for `Cholesterol` and `RestingBP`.

Since zero is not a meaningful value for these measurements, they were treated as invalid values.

### Cholesterol

The mean cholesterol value excluding zero values was calculated and used to replace the zero values.

### Resting Blood Pressure

Similarly, the mean resting blood pressure excluding zero values was calculated and used to replace zero values.

This helped improve the quality of the numerical data before further processing.

---

# 🔄 Data Preprocessing

Categorical variables were converted into numerical variables using **one-hot encoding**.

   ###python
df_encode = pd.get_dummies(df, drop_first=True)

The encoded dataset was then converted into integer values.

This preprocessing step allows categorical information to be used by Machine Learning algorithms.

---

# 🧩 Feature Engineering

Additional features were created to provide the Machine Learning model with potentially useful information derived from existing features.

## 👤 Age Group

The patient's age was divided into four groups:

- Young
- Adult
- Middle
- Senior

| Age Range | Category |
|---|---|
| 0–30 | Young |
| 31–45 | Adult |
| 46–60 | Middle |
| Above 60 | Senior |

---

## 🩺 High Blood Pressure

A binary feature called **High_BP** was created.
**text**
1 → RestingBP >= 140
0 → RestingBP < 140

---
# 🧪 High Cholesterol

A binary feature called High_Cholesterol was created.

1 → Cholesterol >= 240
0 → Cholesterol < 240

## 🔗 Blood Pressure × Cholesterol

Another interaction feature called BP_Cholesterol was created.

BP_Cholesterol = RestingBP × Cholesterol

## 🏃 Exercise Risk

An Exercise_Risk feature was created using exercise-induced angina and Oldpeak.

Exercise_Risk = ExerciseAngina_Y × Oldpeak

This combines information from exercise-induced angina and ST depression.

# ⚖️ Feature Scaling

Numerical features were standardized using StandardScaler from Scikit-learn.

The following features were scaled:
[
    'Age',
    'RestingBP',
    'Cholesterol',
    'MaxHR',
    'Oldpeak'
]

Standardization transforms numerical features to a common scale, making them more suitable for Machine Learning algorithms that are sensitive to feature magnitude.

# 📊 Current Project Status

The current stage of the project includes:

✅ Data loading
✅ Exploratory Data Analysis
✅ Data cleaning
✅ Categorical encoding
✅ Feature engineering
✅ Feature scaling

The processed dataset is being prepared for the next stage:

Machine Learning model training and evaluation.

# 📁 Project Structure
Heart-Disease-Pred/
│
├── Heart_Disease_Prediction.ipynb
├── heart.csv
└── README.md
## 📄 File Description
File	Description
Heart_Disease_Prediction.ipynb	Jupyter Notebook containing the data analysis and preprocessing workflow
heart.csv	Heart disease dataset
README.md	Project documentation

# 🚀 How to Run

#### 1. Clone the repository
git clone <your-github-repository-url>
#### 2. Navigate to the project
cd Heart-Disease-Pred
#### 3. Install the required libraries
pip install numpy pandas matplotlib seaborn scikit-learn
#### 4. Open Jupyter Notebook
jupyter notebook

Open:

Heart_Disease_Prediction.ipynb

Run the notebook cells sequentially.


### 👨‍💻 Author

Lokesh

This project is part of my Machine Learning learning journey, focusing on building an end-to-end classification workflow using Python and Scikit-learn.