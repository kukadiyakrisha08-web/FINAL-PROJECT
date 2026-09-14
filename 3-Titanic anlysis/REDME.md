# 🚢 Titanic Survival Analysis

> **Exploratory Data Analysis (EDA) project using Python, Pandas, Matplotlib and Seaborn**

[![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas)](https://pandas.pydata.org/)
[![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-11557c)](https://matplotlib.org/)
[![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-4c9a8b)](https://seaborn.pydata.org/)
[![Google Colab](https://img.shields.io/badge/Google%20Colab-Notebook-orange?logo=googlecolab)](https://colab.research.google.com/)

---

## 📌 Project Overview

The **Titanic Survival Analysis** project performs Exploratory Data Analysis (EDA) on the famous Titanic passenger dataset.

The main purpose of this project is to understand the factors that were associated with passenger survival, including:

- 👩 Gender
- 🎫 Passenger Class
- 🎂 Age
- 💰 Fare
- 🚢 Embarkation Port
- 👨‍👩‍👧‍👦 Family Size

The analysis is performed step-by-step in **Google Colab** using Python data-analysis and visualization libraries.

---

## 🎯 Objectives

The project aims to:

1. Load and understand the Titanic dataset.
2. Explore rows, columns, data types and statistical information.
3. Identify and handle missing values.
4. Check duplicate records.
5. Calculate the overall survival rate.
6. Analyze survival by gender and passenger class.
7. Study age and fare distributions.
8. Analyze survival by age group, embarkation port and family size.
9. Create meaningful visualizations.
10. Identify important patterns and summarize the findings.

---

## 📊 Dataset Information

**Dataset:** Titanic Dataset (`Titanic-Dataset.csv`)

The dataset contains **891 rows and 12 original columns**.

### Important Columns

| Column | Description |
|---|---|
| `PassengerId` | Unique passenger identifier |
| `Survived` | Survival status: `0 = No`, `1 = Yes` |
| `Pclass` | Passenger class: 1st, 2nd or 3rd |
| `Name` | Passenger name |
| `Sex` | Passenger gender |
| `Age` | Passenger age |
| `SibSp` | Number of siblings/spouses aboard |
| `Parch` | Number of parents/children aboard |
| `Ticket` | Ticket number |
| `Fare` | Ticket fare |
| `Cabin` | Cabin information |
| `Embarked` | Port of embarkation |

During the analysis, additional columns such as **`AgeGroup`** and **`FamilySize`** are created.

---

## 🛠️ Technologies & Libraries

- 🐍 **Python**
- 🐼 **Pandas** — data loading, cleaning and analysis
- 🔢 **NumPy** — numerical operations
- 📊 **Matplotlib** — data visualization
- 🎨 **Seaborn** — statistical visualization
- ☁️ **Google Colab** — development environment

---

## 🧹 Data Cleaning

The project includes the following cleaning steps:

- Checking missing values using `isnull().sum()`
- Filling missing `Age` values with the median
- Filling missing `Embarked` values with the mode
- Removing the `Cabin` column because it contains a large number of missing values
- Checking duplicate rows using `duplicated()`

---

## 🔍 Exploratory Data Analysis

### 1. Dataset Exploration

The following operations are performed:

```python
df.head()
df.tail()
df.shape
df.columns
df.info()
df.describe()
```

These help understand the dataset structure, data types, missing values and statistical summary.

### 2. Survival Count

The project compares passengers who survived with those who did not.

```python
df['Survived'].value_counts()
```

`0` represents passengers who did not survive, while `1` represents passengers who survived.

### 3. Overall Survival Rate

```python
survival_rate = df['Survived'].mean() * 100
print(f"Overall Survival Rate: {survival_rate:.2f}%")
```

### 4. Survival by Gender

```python
sns.countplot(x='Sex', hue='Survived', data=df)
```

Gender-wise survival rates are also calculated using:

```python
gender_survival = df.groupby('Sex')['Survived'].mean() * 100
```

### 5. Survival by Passenger Class

Passenger classes are:

- 🥇 1st Class
- 🥈 2nd Class
- 🥉 3rd Class

The project compares both survival counts and survival rates across these classes.

### 6. Age Analysis

Age distribution is visualized using a histogram, followed by a comparison of age against survival.

An `AgeGroup` column is also created:

```python
bins = [0, 12, 18, 30, 50, 100]
labels = ['Child', 'Teenager', 'Young Adult', 'Adult', 'Senior']

df['AgeGroup'] = pd.cut(df['Age'], bins=bins, labels=labels)
```

### 7. Fare Analysis

The project studies the distribution of ticket fares and compares fare values between survived and non-survived passengers.

### 8. Embarkation Analysis

The `Embarked` column represents the passenger's boarding port:

- `S` = Southampton
- `C` = Cherbourg
- `Q` = Queenstown

### 9. Family Size Analysis

Family size is calculated as:

```python
df['FamilySize'] = df['SibSp'] + df['Parch'] + 1
```

The relationship between family size and survival is then visualized.

### 10. Correlation Heatmap

A correlation heatmap is created for numerical variables:

```python
numeric_df = df.select_dtypes(include=np.number)

sns.heatmap(
    numeric_df.corr(),
    annot=True,
    cmap='coolwarm',
    fmt='.2f'
)
```

---

## 📈 Visualizations Created

The project includes:

- 📊 Survival Count
- 👩 Survival by Gender
- 🎫 Survival by Passenger Class
- 🎂 Age Distribution
- 📦 Age vs Survival
- 📈 Survival Rate by Age Group
- 💰 Fare Distribution
- 📦 Fare vs Survival
- 🚢 Survival by Embarkation Port
- 👨‍👩‍👧‍👦 Family Size vs Survival
- 🔥 Correlation Heatmap
- 📊 Passengers by Class and Gender
- 📊 Survival Rate by Class and Gender

---

## 💡 Key Insights

Based on the analysis:

1. **Gender:** Female passengers generally had a much higher survival rate than male passengers.
2. **Passenger Class:** First-class passengers had a higher survival rate compared with second- and third-class passengers.
3. **Age:** Different age groups showed different survival patterns.
4. **Fare:** Passengers paying higher fares generally had better survival outcomes, partly reflecting passenger class.
5. **Family Size:** Survival varied according to family size.
6. **Embarkation:** Survival rates differed among passengers from different embarkation ports.
7. **Overall:** Gender and passenger class were among the strongest factors associated with Titanic survival in this analysis.

---

## 📁 Project Structure

```text
Titanic-Survival-Analysis/
│
├── 📄 Titanic-Dataset.csv
├── 📓 Titanic_Survival_Analysis.ipynb
├── 📖 README.md
└── 📂 images/                 # Optional: saved charts/screenshots
```

---

## ▶️ How to Run in Google Colab

### Step 1 — Open Google Colab

Create a new notebook in Google Colab.

### Step 2 — Import Libraries

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

sns.set_style("whitegrid")

print("Libraries imported successfully!")
```

### Step 3 — Upload Dataset

```python
from google.colab import files

uploaded = files.upload()
```

Upload:

```text
Titanic-Dataset.csv
```

### Step 4 — Load Dataset

```python
df = pd.read_csv("Titanic-Dataset.csv")
print("Dataset loaded successfully!")
```

### Step 5 — Run the EDA Cells

Run the analysis cells in order, from dataset exploration through the final conclusion.

---

## 🧠 Project Learning Outcomes

Through this project, you practice:

- Reading CSV files with Pandas
- DataFrame operations
- Data cleaning
- Missing-value handling
- Statistical analysis
- GroupBy operations
- Creating new analytical columns
- Data visualization
- Correlation analysis
- Drawing conclusions from data

---

## 🏆 Conclusion

The Titanic dataset provides a useful example of how exploratory data analysis can reveal meaningful patterns in historical data.

This project demonstrates a complete basic EDA workflow — from **loading and cleaning data** to **visualizing relationships and communicating insights**.

---

## 👨‍💻 Author

**krisha kukadiya**

> Titanic Survival Analysis — Python EDA Project

---

## ⭐ If You Like This Project

If this project helped you learn Python, Pandas and data visualization, consider giving the repository a ⭐ on GitHub.

---

### 📚 Tools Used

**Python • Pandas • NumPy • Matplotlib • Seaborn • Google Colab**

