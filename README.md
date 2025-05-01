# 🧹 Dirty Data Cleaning & EDA – Animal Observations 2024

## 📌 Overview

This project focuses on cleaning and analyzing a messy dataset containing ~1,000 animal observations made across Central and Eastern Europe in 2024.  
The dataset includes various issues such as:

- Missing values  
- Duplicate records  
- Formatting errors  
- Inconsistent categorical labels  

The goal is to:
- Clean the dataset  
- Perform exploratory data analysis (EDA)  
- Visualize trends and geospatial distributions  
- Extract insights about animal types, locations, and patterns

---

## 📁 Dataset Details

- **Source**: [Kaggle – Dirty Data to Clean](https://www.kaggle.com/datasets/joannanplkrk/dirty-data-to-clean-whats-wrong-with-this-dataset)
- **File Used**: `animal_data_dirty1.csv`
- **Size**: ~1,000 records
- **Columns Include**:
  - Animal type, Country, Gender
  - Weight & Body Length
  - Latitude & Longitude
  - Observation Date & Animal Name
  - Data Compiled By (4 contributors)

---

## 🧽 Data Cleaning Steps

| Column              | Issue                                                | Action Taken                          |
|---------------------|------------------------------------------------------|----------------------------------------|
| `animal_code`       | All values missing                                   | Dropped the column                     |
| `weight_kg`         | 15 missing values                                    | Filled with column median              |
| `body_length_cm`    | 15 missing values                                    | Filled with column median              |
| `latitude`, `longitude` | 78 rows missing — essential for mapping         | Dropped those rows                     |
| `animal_name`       | Only 52 non-null entries                             | Kept as optional context               |
| `gender`            | Inconsistent values like `"not determined"`         | Standardized and cleaned               |
| `animal_type`       | Typos like `"European bison™"`, `"lynx?"`           | Cleaned and standardized               |
| `observation_date`  | Stored as strings                                    | Converted to `datetime` format         |
| Duplicate Rows      | Present                                              | Removed                                |

📊 **Final Cleaned Dataset Shape**: `913 rows × 10 columns`

---

## 📊 Exploratory Data Analysis (EDA)

### ✅ Distribution of Animal Types
- Bar plot showing frequency of each animal type
- Cleaned duplicates like `"lynx?" → "lynx"`

### ✅ Gender Distribution
- Count plot for gender breakdown
- Standardized to lowercase (`male`, `female`, `unknown`)

### ✅ Observation Timeline
- Line chart showing number of observations per date
- Covers March–June 2024

### ✅ Country-wise Observations
- Bar plot showing counts per country
- Highest: Poland, Romania, Hungary

### ✅ Geospatial Analysis
- Scatter plot of latitude vs longitude

---

## 🧠 Insights Summary

- Most observed species: **European bison**, **lynx**, **grey wolf**
- Common regions: **Poland**, **Romania**, **Hungary**
- Peak observation period: **March–April 2024**
- Minor anomalies: Some unrealistic weights/body lengths flagged as outliers

---

## 💻 Technologies Used

- Python (Pandas, NumPy)
- Matplotlib & Seaborn for visualization
- Folium for geospatial mapping
- Jupyter Notebook for step-by-step analysis

---

## 📂 Repository Structure

<pre lang="markdown"> ``` . ├── data/ │ ├── animal_data_dirty1.csv │ └── animal_data_cleaned.csv ├── notebooks/ │ └── animal_data_eda.ipynb ├── README.md └── requirements.txt ``` </pre>
