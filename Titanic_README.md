Titanic Dataset : Data Cleaning & Preprocessing

 Project Overview

This project focuses on cleaning and preprocessing the famous Titanic dataset using **Python**, **Pandas**, and **NumPy** in **Google Colab**.
The main goal was to transform raw and inconsistent data into a structured and analysis-ready dataset.

The dataset was downloaded from:

Kaggle

The complete preprocessing workflow was implemented in a Jupyter Notebook (`.ipynb`) file.

Objective

The objective of this task was to:

* Handle missing values
* Remove duplicate records
* Convert data types
* Rename columns for better readability
* Prepare the dataset for further analysis and machine learning


Technologies & Tools Used

| Tool / Technology | Purpose                      |
| ----------------- | ---------------------------- |
| Python            | Programming Language         |
| Pandas            | Data Cleaning & Manipulation |
| NumPy             | Numerical Operations         |
| Google Colab      | Development Environment      |
| Kaggle            | Dataset Source               |



 Dataset Information

The Titanic dataset contains passenger information such as:

* Passenger ID
* Survival Status
* Passenger Class
* Name
* Gender
* Age
* Ticket Information
* Fare
* Cabin
* Embarkation Port

Dataset File Used:

```python
train.csv
```

Initial Dataset Problems Identified :-

Before preprocessing, the dataset contained several issues:

| Problem                    | Description                                        |
| -------------------------- | -------------------------------------------------- |
| Missing Values             | Present in Age, Cabin, and Embarked columns        |
| Unnecessary Column         | Cabin column contained excessive null values       |
| Inconsistent Data Types    | Some columns needed conversion for better analysis |
| Less Readable Column Names | Original column names were less descriptive        |
| Possible Duplicate Records | Dataset required duplicate verification            |



Data Cleaning Process

1.Importing Required Libraries

```python
import pandas as pd
import numpy as np
```

These libraries were used for:

* Data manipulation
* Data preprocessing
* Numerical operations


2.Loading the Dataset

```python
df = pd.read_csv("train.csv")
```

The dataset was loaded into a Pandas DataFrame for processing.


3.Exploring the Dataset

The following functions were used:

```python
df.head()
df.info()
df.isnull().sum()
```

Purpose:

* Understand dataset structure
* Identify missing values
* Check data types
* Preview records

 Handling Missing Values

 Age Column

Missing values in the `Age` column were replaced using the median value.

```python
df['Age'] = df['Age'].fillna(df['Age'].median())
```

Impact

* Prevented data loss
* Preserved dataset size
* Median reduced the impact of outliers



Embarked Column

Missing values in the `Embarked` column were filled using the mode.

```python
df['Embarked'] = df['Embarked'].fillna(df['Embarked'].mode()[0])
```

 Impact

* Maintained categorical consistency
* Allowed smoother analysis


 Cabin Column Removal

The `Cabin` column contained too many missing values, so it was removed.

```python
df = df.drop(columns=['Cabin'])
```

Impact

* Reduced unnecessary complexity
* Improved dataset quality
* Removed a highly incomplete feature


Duplicate Removal

```python
df = df.drop_duplicates()
```

Duplicate rows were checked and removed.

```python
print(df.duplicated().sum())
```

 Impact

* Ensured data uniqueness
* Prevented repeated records during analysis
* Improved dataset reliability


Data Type Conversion

The following columns were converted:

```python
df['Age'] = df['Age'].astype(int)
df['Fare'] = df['Fare'].astype(int)
df['Pclass'] = df['Pclass'].astype('category')
df['Embarked'] = df['Embarked'].astype('category')
```

Why Data Type Conversion Was Important

| Column   | Converted To | Reason                              |
| -------- | ------------ | ----------------------------------- |
| Age      | int          | Simplified numeric analysis         |
| Fare     | int          | Standardized fare values            |
| Pclass   | category     | Better handling of categorical data |
| Embarked | category     | Improved memory efficiency          |

Impact

* Improved performance
* Reduced memory usage
* Made analysis more efficient


 Column Renaming

The column names were renamed for better readability.

```python
df = df.rename(columns={
    'PassengerId':'Passenger_Id',
    'Pclass':'Passenger_Class',
    'Survived':'Survival_Status',
    'SibSp':'Siblings_Spouses',
    'Parch':'Parents_Children',
    'Fare':'Ticket_Fare',
    'Embarked':'Port_Embarked'
})
```

---
 Dataset Comparison

Before Cleaning

| Feature                | Status              |
| ---------------------- | ------------------- |
| Missing Values         | Present             |
| Cabin Column           | Mostly empty        |
| Duplicate Verification | Not performed       |
| Data Types             | Mixed / unoptimized |
| Column Names           | Less descriptive    |
| Analysis Ready         | No                |

After Cleaning

| Feature           | Status             |
| ----------------- | ------------------ |
| Missing Values    | Handled            |
| Cabin Column      | Removed            |
| Duplicate Records | Removed / Verified |
| Data Types        | Optimized          |
| Column Names      | More readable      |
| Analysis Ready    |  Yes              |

Overall Impact of Preprocessing

The preprocessing stage significantly improved the dataset quality by:

✅ Handling incomplete data
✅ Improving readability
✅ Making the dataset analysis-ready
✅ Enhancing consistency
✅ Improving memory efficiency
✅ Preparing the data for machine learning and visualization

Final Output

The cleaned dataset was exported as:

```python
cleaned_titanic_dataset.csv
```
Learning Outcomes :-
Through this project, the following concepts were learned:

* Data preprocessing techniques
* Handling missing values
* Duplicate removal
* Data type conversion
* Column renaming
* Working with Pandas DataFrames
* Using Google Colab for data analysis


 Future Scope

The cleaned dataset can now be used for:

* Exploratory Data Analysis (EDA)
* Data Visualization
* Survival Prediction Models
* Machine Learning Projects
* Statistical Analysis



Author

Varshini Nayak

B.Sc. Computer Science Student
Government College of Arts, Science and Commerce, Quepem Goa
