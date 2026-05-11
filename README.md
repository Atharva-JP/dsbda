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
