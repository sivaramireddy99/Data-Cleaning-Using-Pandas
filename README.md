# 🧹 Data-Cleaning-Using-Pandas

**Transforming Raw Data into Meaningful Data**

---

## 📌 Project Overview

This project demonstrates the process of cleaning raw data using the **Python Pandas** library. Data cleaning is one of the most important steps in Data Analytics and Machine Learning, ensuring that datasets are accurate, consistent, and ready for analysis.

---

## 🎯 Objective

The primary objective of this project is to transform messy and incomplete data into a clean and structured dataset by performing:

* Typecasting
* Handling Duplicates
* Outlier Analysis
* Zero and Near-Zero Variance Detection
* Handling Missing Values
* Discretization
* Dummy Variables (One-Hot Encoding)
* Data Transformation
* Feature Scaling
* Standardizing Text Values

---

## 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Jupyter Notebook

---

## 📂 Project Structure

```text
Data_Cleaning_Using_Pandas/
│
├── data/
│   ├── raw_data.csv
│   └── cleaned_data.csv
│
├── notebooks/
│   └── data_cleaning.ipynb
│
├── screenshots/
│   └── output_images.png
│
├── requirements.txt
└── README.md
```

---

## 🔄 Data Cleaning Workflow

### 1️⃣ Import Required Libraries

```python
import pandas as pd
import numpy as np
```

### 2️⃣ Load Dataset

```python
df = pd.read_csv("raw_data.csv")
```

### 3️⃣ Explore Data

```python
df.head()
df.info()
df.describe()
```

### 4️⃣ Typecasting

```python
df['Date'] = pd.to_datetime(df['Date'])
```

### 5️⃣ Handling Missing Values

```python
df.isnull().sum()

df['Age'].fillna(df['Age'].mean(), inplace=True)
```

### 6️⃣ Handling Duplicates

```python
df.drop_duplicates(inplace=True)
```

### 7️⃣ Outlier Analysis

```python
Q1 = df['Salary'].quantile(0.25)
Q3 = df['Salary'].quantile(0.75)

IQR = Q3 - Q1

df = df[
    (df['Salary'] >= Q1 - 1.5 * IQR) &
    (df['Salary'] <= Q3 + 1.5 * IQR)
]
```

### 8️⃣ Zero & Near-Zero Variance

```python
df.nunique()
```

### 9️⃣ Discretization

```python
df['Age_Group'] = pd.cut(
    df['Age'],
    bins=[0,18,35,60,100],
    labels=['Child','Young','Adult','Senior']
)
```

### 🔟 Dummy Variables (One-Hot Encoding)

```python
df = pd.get_dummies(df, columns=['City'])
```

### 1️⃣1️⃣ Data Transformation

```python
df['Salary'] = np.log1p(df['Salary'])
```

### 1️⃣2️⃣ Feature Scaling

```python
from sklearn.preprocessing import MinMaxScaler

scaler = MinMaxScaler()

df[['Salary']] = scaler.fit_transform(df[['Salary']])
```

### 1️⃣3️⃣ Standardizing Text Data

```python
df['City'] = df['City'].str.strip().str.title()
```

### 1️⃣4️⃣ Save Cleaned Dataset

```python
df.to_csv("cleaned_data.csv", index=False)
```

---

## 📊 Data Cleaning Checklist

* ✅ Dataset Imported
* ✅ Data Exploration Performed
* ✅ Typecasting Applied
* ✅ Missing Values Handled
* ✅ Duplicate Records Removed
* ✅ Outliers Treated
* ✅ Zero/Near-Zero Variance Checked
* ✅ Discretization Applied
* ✅ One-Hot Encoding Performed
* ✅ Data Transformation Applied
* ✅ Feature Scaling Completed
* ✅ Text Values Standardized
* ✅ Cleaned Dataset Exported

---

## 📈 Key Outcomes

* Improved data quality and consistency.
* Reduced errors caused by missing and duplicate records.
* Standardized and transformed data for better analysis.
* Enhanced dataset reliability for Machine Learning models.
* Prepared data for visualization and business intelligence reporting.

---

## 🚀 How to Run

### Clone the Repository

```bash
git clone https://github.com/sivaramireddy99/Data_Cleaning_Using_Pandas.git
```

### Navigate to the Project Directory

```bash
cd Data_Cleaning_Using_Pandas
```

### Install Required Libraries

```bash
pip install -r requirements.txt
```

### Run Jupyter Notebook

```bash
jupyter notebook
```

---

## 📚 Learning Outcomes

* Understanding Data Cleaning Techniques
* Working with Pandas DataFrames
* Handling Missing Data
* Removing Duplicates
* Data Type Conversion
* Outlier Detection and Treatment
* Feature Engineering
* Data Transformation & Scaling
* Preparing Data for Analytics and Machine Learning

---

## 👨‍💻 Author

### Siva Rami Reddy

**Data Analyst | Python | SQL | Power BI | NumPy | Pandas | Matplotlib | Seaborn**

---

## ⭐ Project Status

✅ Completed

✅ Ready for Data Analysis and Visualization

---

### If you found this project useful, don't forget to ⭐ the repository!
