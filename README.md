# dsbda

-------------------------------------------------------------------------------------------------------

# practical 1

import numpy as np
import pandas as pd

df = pd.read_csv("StudentsPerformance.csv")

print(df.head())

print(df.isnull().sum())

print(df.isnull())

print(df.describe())

print(df.shape)

print(df.dtypes)

df["math score"] = df["math score"].astype(float)

print(df.dtypes)

df["gender"].replace({"female": 0, "male": 1}, inplace=True)

df

print(df.head())

df["gender"].replace({"female": 0, "male": 1}, inplace=True)

print(df.head())

-------------------------------------------------------------------------------------------------------

# practical 2

import pandas as pd

df = pd.read_csv("StudentsPerformance.csv")

df

print(df.isnull().sum())

df.dropna()

mean_val = df["math score"].mean()

df["math score"] = df["math score"].fillna(mean_val)

df.boxplot()

check_outliers = df[df["math score"] > 30]

print(check_outliers)

cols = ['math score', 'reading score', 'writing score']

for col in cols:
    df[col] = (df[col] - df[col].min()) / (df[col].max() - df[col].min())

df.head()


---------------------------------------------------------------------------------------------------------------------

# practical 3

import pandas as pd

df = pd.read_csv("Iris.csv")

print(df.head())

print(df.describe())

print(df["SepalLengthCm"].describe())

print(df.info())

print(df.groupby("Species").describe())




satosa = df[df["Species"] == "Iris-setosa"].describe()

versicolor = df[df["Species"] == "Iris-versicolor"].describe()

virginica = df[df["Species"] == "Iris-virginica"].describe()

print("satosa\n", satosa)

print("versicolor\n", versicolor)

print("virginica\n", virginica)

----------------------------------------------------------------------------------------------------------------

# problem statements 

# pr 1

PROBLEM STATEMENT :
Perform the following operations using Python on any open source dataset.
1. Import all the required Python libraries.
2. Locate open source data from the web (e.g., https://www.kaggle.com)
Provide a clear description of the data and its sources (i.e., URL of the web site)
3. Load the dataset into the pandas data frame.
4. Data Preprocessing : Check for missing values in the data using pandas insult(), describe() function to get some initial statistics. Provide variable description. Types of variables, etc. Check the dimensions of the data frame.
5. Data formatting and data normalization : Summarize the types of variables by checking the data types (i.e., character, numeric,integer,factor and logical) of the variables in the dataset. If variables are not in the correct data type, appply proper type conversions.
6. Turn categorial variables into quantitative variables in python.


# pr 2

PROBLEM STATEMENT :
Create an “Academic performance” dataset of students and perform the following operations using Python :
1. Scan all variables for missing values and inconsistencies. If there are missing values and/or inconsistencies, use any of the suitable techniques to deal with them. 
2. Scan all numeric variables for outliers. If there are outliers, use any of the suitable techniques to deal with them. 
3. Apply data transformations on at least one of the variables. The purpose of this transformation should be one of the following reasons: to change the scale for better understanding of the variable, to convert a non-linear relation into a linear one, or to decrease the skewness and convert the distribution into a normal distribution.


# pr 3

PROBLEM STATEMENT :
Perform the following operations on any open sourse dataset :
1. provide summary statistics (mean, median, minimum, maximum, standard deviation) for a dataset (age, income, etc.) with the numeric variables grouped by one of the qualitative (categorical) variables. For example, if your categorical variable is age groups and quantitative variable is income, then provide summary statistics of income group by age groups
Create a list that contains a numeric value for each response to the categorical variable.
2. Write a program to display some basic statistical details like percentile, mean, standard devaition, etc. of the species of 'Iris-Setosa','Iris-Versicolor' and 'Iris-Virginica of the iris.csv dataset.
Provide the codes with outputs and explain everything that you do in this step.
