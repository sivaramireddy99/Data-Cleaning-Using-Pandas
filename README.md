# Data-Cleaning-Using-Pandas
Transforming Raw Data into Meaningful Data.

🧹 Data Cleaning Using Pandas
📌 Project Overview

This project demonstrates the process of cleaning raw data using the Python Pandas library. Data cleaning is a crucial step in data analysis and machine learning, ensuring that datasets are accurate, consistent, and ready for further processing.

🎯 Objective

The primary objective of this project is to transform messy and incomplete data into a clean and structured dataset by:
1. Typecasting 
2. Handling Duplicates
3. Outlier Analysis
4. Zero and Near Zero Variance
5. Handling Missing Values
6. Discretization
7. Dummy Variable[One-Hot Coding]
8. Transformation
9. Feature Scaling
10. Standardizing text values
Preparing data for analysis
🛠️ Technologies Used
Python
Pandas
NumPy
Jupyter Notebook
📂 Project Structure
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
🔄 Data Cleaning Workflow
1. Import Required Libraries
import pandas as pd
import numpy as np
2. Load Dataset
df = pd.read_csv("raw_data.csv")
3. Explore Data
df.head()
df.info()
df.describe()
4. Handle Missing Values
df.isnull().sum()

df['Age'].fillna(df['Age'].mean(), inplace=True)
5. Remove Duplicate Records
df.drop_duplicates(inplace=True)
6. Correct Data Types
df['Date'] = pd.to_datetime(df['Date'])
7. Standardize Text Data
df['City'] = df['City'].str.strip().str.title()
8. Detect and Handle Outliers
Q1 = df['Salary'].quantile(0.25)
Q3 = df['Salary'].quantile(0.75)
IQR = Q3 - Q1

df = df[
    (df['Salary'] >= Q1 - 1.5 * IQR) &
    (df['Salary'] <= Q3 + 1.5 * IQR)
]
9. Save Cleaned Dataset
df.to_csv("cleaned_data.csv", index=False)
📊 Data Cleaning Checklist
 Dataset Imported
 Data Exploration Performed
 Missing Values Handled
 Duplicate Records Removed
 Data Types Corrected
 Text Values Standardized
 Outliers Treated
 Cleaned Dataset Exported
📈 Key Outcomes
Improved data quality and consistency.
Reduced errors caused by missing or duplicate records.
Standardized data for easier analysis.
Prepared dataset for visualization and machine learning models.
🚀 How to Run
Clone the repository:
git clone https://github.com/sivaramireddy99/Data_Cleaning_Using_Pandas.git
Navigate to the project directory:
cd Data_Cleaning_Using_Pandas
Install required libraries:
pip install -r requirements.txt
Run the Jupyter Notebook:
jupyter notebook
📚 Learning Outcomes
Understanding Data Cleaning Techniques
Working with Pandas DataFrames
Handling Missing Data
Removing Duplicates
Data Type Conversion
Outlier Detection and Treatment
Data Preparation for Analytics
👨‍💻 Author

Siva Rami Reddy
Data Analyst | Python | SQL | Power BI | NumPY | Pandas | Matplotlib | Seaborn

⭐ Project Status

✅ Completed
✅ Ready for Data Analysis and Visualization
