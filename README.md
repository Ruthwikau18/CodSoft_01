# 🚢 CodSoft Task 1 – Data Cleaning and Preprocessing

## 📌 Project Overview

This project is part of the **CodSoft Data Analytics Internship – Task 1**. The objective is to clean and preprocess a real-world dataset using **Python, Pandas, and NumPy**.

The **Titanic dataset** was imported, inspected, analyzed for data-quality issues, cleaned, and prepared for further data analysis.

---

## 🎯 Objectives

* Import and inspect the dataset using Python.
* Understand the structure and characteristics of the dataset.
* Identify missing values.
* Detect duplicate records.
* Identify inconsistent data entries.
* Handle missing/null values.
* Remove duplicate records.
* Correct inappropriate data types.
* Standardize categorical data.
* Prepare the dataset for further analysis.
* Export the cleaned dataset as a CSV file.

---

## 🛠️ Technologies Used

* **Python**
* **Pandas**
* **NumPy**
* **Google Colab**
* **Jupyter Notebook**

---

## 📊 Dataset

### Titanic Dataset

The Titanic dataset contains information about passengers aboard the Titanic.

### Main Features

| Column      | Description                            |
| ----------- | -------------------------------------- |
| PassengerId | Unique passenger identification number |
| Survived    | Survival status                        |
| Pclass      | Passenger class                        |
| Name        | Passenger name                         |
| Sex         | Passenger gender                       |
| Age         | Passenger age                          |
| SibSp       | Number of siblings/spouses aboard      |
| Parch       | Number of parents/children aboard      |
| Ticket      | Ticket number                          |
| Fare        | Ticket fare                            |
| Cabin       | Cabin information                      |
| Embarked    | Port of embarkation                    |

---

## 🔍 Data Cleaning Process

### 1. Import Libraries

```python
import pandas as pd
import numpy as np
```

### 2. Load Dataset

```python
url = "https://raw.githubusercontent.com/datasciencedojo/datasets/master/titanic.csv"
df = pd.read_csv(url)
```

### 3. Inspect Dataset

The dataset was inspected using:

```python
df.head()
df.shape
df.info()
df.describe()
```

These functions were used to understand the dataset's structure, dimensions, data types, and statistical information.

### 4. Identify Missing Values

```python
df.isnull().sum()
```

Missing values were analyzed for each column.

### 5. Handle Missing Values

* Missing `Age` values were replaced with the median age.
* Missing `Embarked` values were replaced with the most frequent value.
* Missing `Cabin` values were replaced with `"Unknown"`.

```python
df['Age'] = df['Age'].fillna(df['Age'].median())
df['Embarked'] = df['Embarked'].fillna(df['Embarked'].mode()[0])
df['Cabin'] = df['Cabin'].fillna('Unknown')
```

### 6. Remove Duplicate Records

Duplicate records were identified and removed.

```python
df = df.drop_duplicates()
```

### 7. Standardize Data

Categorical values were standardized using:

```python
df['Sex'] = df['Sex'].str.strip().str.lower()
df['Embarked'] = df['Embarked'].str.strip().str.upper()
```

### 8. Correct Data Types

Appropriate data types were assigned to numerical columns using Pandas `astype()`.

```python
df['PassengerId'] = df['PassengerId'].astype(int)
df['Survived'] = df['Survived'].astype(int)
df['Pclass'] = df['Pclass'].astype(int)
df['Age'] = df['Age'].astype(float)
df['Fare'] = df['Fare'].astype(float)
```

---

## ✅ Final Validation

After cleaning, the dataset was checked again for:

* Missing values
* Duplicate records
* Data types
* Dataset dimensions
* Data consistency

```python
df.isnull().sum()
df.duplicated().sum()
df.dtypes
df.info()
```

---

## 💾 Export Cleaned Dataset

The cleaned dataset was exported as a CSV file:

```python
df.to_csv('cleaned_titanic_dataset.csv', index=False)
```

---

## 📁 Project Structure

```text
CodSoft-Task-1/
│
├── CodSoft_Task1_Data_Cleaning.ipynb
├── cleaned_titanic_dataset.csv
└── README.md
```

---

## 🎓 Learning Outcomes

Through this project, I gained practical experience in:

* Data loading using Pandas
* Data inspection
* Missing-value handling
* Duplicate detection and removal
* Data type conversion
* Data standardization
* Data validation
* CSV data export
* Basic data preprocessing

---

## 👨‍💻 Internship

**CodSoft – Data Analytics Internship**

**Task:** Task 1 – Data Cleaning and Preprocessing

**Tools:** Python | Pandas | NumPy | Google Colab

---

## ⭐ Acknowledgement

This project was completed as part of the **CodSoft Data Analytics Internship** to develop practical skills in data cleaning and preprocessing using Python.
