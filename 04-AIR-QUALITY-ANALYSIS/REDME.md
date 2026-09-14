# 🌍 Air Quality Analysis

```{=html}
<p align="center">
```
`<b>`{=html}📊 Exploring Air Pollution Trends & Weather
Relationships`</b>`{=html}
```{=html}
</p>
```

------------------------------------------------------------------------

## 📌 Project Overview

**Air Quality Analysis** is a Python-based data analysis and
visualization project that explores air pollution measurements collected
over time.

The project focuses on understanding:

-   🌫️ Pollution levels and their changes over time
-   🧪 Relationships between different pollutants
-   🌡️ The relationship between air pollution and weather conditions
-   📈 Monthly and time-based pollution trends
-   🔥 Correlations between air-quality and weather variables

The analysis uses the **UCI Machine Learning Repository Air Quality
Dataset**.

------------------------------------------------------------------------

## 🎯 Objectives

The main objectives of this project are:

1.  Load and explore an air-quality dataset.
2.  Clean missing and invalid values.
3.  Process date and time information.
4.  Analyze major air pollutants such as CO, NOx and NO2.
5.  Study the relationship between pollution and temperature.
6.  Analyze correlations using a heatmap.
7.  Visualize monthly pollution trends.
8.  Present meaningful findings and conclusions.

------------------------------------------------------------------------

## 🛠️ Technologies & Libraries

  Technology                  Purpose
  --------------------------- ----------------------------------
  🐍 Python                   Programming & analysis
  🐼 Pandas                   Data processing and manipulation
  🔢 NumPy                    Numerical operations
  📊 Matplotlib               Data visualization
  🎨 Seaborn                  Statistical visualization
  📓 Jupyter / Google Colab   Development environment

------------------------------------------------------------------------

## 📂 Dataset

**Dataset:** Air Quality UCI Dataset

The dataset contains hourly measurements of air pollutants and
environmental variables.

### Important Variables

  Column       Description
  ------------ --------------------------------
  `CO(GT)`     Carbon Monoxide concentration
  `C6H6(GT)`   Benzene concentration
  `NOx(GT)`    Nitrogen Oxides concentration
  `NO2(GT)`    Nitrogen Dioxide concentration
  `T`          Temperature
  `RH`         Relative Humidity
  `AH`         Absolute Humidity

> **Note:** In this dataset, `-200` represents missing/unavailable
> measurements and is treated as a missing value during cleaning.

------------------------------------------------------------------------

## 🔄 Project Workflow

``` text
📂 Load Dataset
      ↓
🔍 Explore Data
      ↓
🧹 Clean Missing Values
      ↓
📅 Process Date & Time
      ↓
🔢 Convert Data Types
      ↓
📈 Analyze Pollution Trends
      ↓
🌡️ Study Weather Relationships
      ↓
🔥 Correlation Analysis
      ↓
📊 Create Visualizations
      ↓
🎯 Findings & Conclusion
```

------------------------------------------------------------------------

## 📊 Visualizations

### 1. CO Pollution Trend

A line chart is used to understand how **Carbon Monoxide (CO)**
concentration changes over time.

### 2. NOx vs NO2 Comparison

A comparison line chart helps visualize the behavior of **NOx** and
**NO2** over time.

### 3. Temperature vs CO

A scatter plot is used to examine the relationship between
**temperature** and **CO pollution**.

### 4. Correlation Heatmap

A Seaborn heatmap shows correlations among:

-   CO
-   C6H6
-   NOx
-   NO2
-   Temperature
-   Relative Humidity
-   Absolute Humidity

### 5. Monthly CO Analysis

Monthly averages are calculated to identify broader pollution trends
while reducing hourly fluctuations.

------------------------------------------------------------------------

## 🔍 Key Findings

The analysis provides several useful observations:

-   **CO and C6H6** show a very strong positive correlation in the
    analyzed dataset.
-   **NOx and NO2** show a strong positive relationship.
-   Several pollution and humidity variables also show strong
    relationships.
-   Temperature has measurable relationships with several air-quality
    variables.
-   Pollution levels vary considerably across different time periods.
-   Monthly aggregation helps reveal longer-term pollution patterns.

> ⚠️ **Important:** Correlation indicates an association between
> variables; it does not by itself prove that one variable causes
> another.

------------------------------------------------------------------------

## 🧹 Data Cleaning

The dataset requires preprocessing before analysis.

### Missing Value Handling

The special value `-200` is converted into missing data:

``` python
df.replace(-200, np.nan, inplace=True)
```

Numerical missing values are then handled using the median:

``` python
df.fillna(df.median(numeric_only=True), inplace=True)
```

### Date & Time Processing

The separate date and time fields are combined into a `DateTime` column
so that time-based analysis can be performed.

------------------------------------------------------------------------

## 🚀 How to Run the Project

### 1. Clone or download the project

Download the project files to your computer.

### 2. Install required libraries

``` bash
pip install pandas numpy matplotlib seaborn
```

### 3. Open the notebook

Open the `.ipynb` file using:

-   Jupyter Notebook
-   JupyterLab
-   Google Colab

### 4. Add the dataset

Make sure `AirQualityUCI.csv` is available in the notebook's working
directory.

### 5. Run the cells

Run the notebook cells from top to bottom to reproduce the analysis and
visualizations.

------------------------------------------------------------------------

## 📁 Suggested Project Structure

``` text
Air-Quality-Analysis/
│
├── 📓 Air_Quality_Analysis.ipynb
├── 📄 AirQualityUCI.csv
├── 📖 README.md
└── 📁 outputs/
    └── charts/
```

------------------------------------------------------------------------

## 💡 Learning Outcomes

Through this project, you can learn:

-   ✅ Pandas DataFrame operations
-   ✅ Data cleaning and preprocessing
-   ✅ Missing-value handling
-   ✅ Date and time manipulation
-   ✅ Numerical data conversion
-   ✅ Statistical correlation
-   ✅ Matplotlib visualization
-   ✅ Seaborn visualization
-   ✅ Trend analysis
-   ✅ Data interpretation

------------------------------------------------------------------------

## 🎓 Project Type

**Academic / Data Analysis Project**

**Domain:** Environmental Data Analysis 🌱

**Primary Focus:** Air Pollution & Weather Relationship

------------------------------------------------------------------------

## 👨‍💻 Conclusion

This project demonstrates how Python can be used to transform raw
air-quality measurements into meaningful insights.

By combining **Pandas, Matplotlib, and Seaborn**, the project provides a
clear view of pollution trends, relationships between pollutants, and
associations between air quality and weather conditions.

The visualizations make complex environmental data easier to understand
and help identify important patterns that can support further
air-quality research.

------------------------------------------------------------------------

```{=html}
<p align="center">
```
🌱 `<b>`{=html}Analyze Data • Understand Pollution • Visualize
Insights`</b>`{=html} 🌱
```{=html}
</p>
```

