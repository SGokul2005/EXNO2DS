# EXNO2DS
# AIM:
To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
# Developed By: Ashwin Kumar A
# REGISTER  NO: 212223040021
```py
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("titanic_dataset.csv")
df
```
![image](https://github.com/user-attachments/assets/e43104e4-91f5-451a-b1ea-bb0ce04db488)
```py
df.info()
```
![image](https://github.com/user-attachments/assets/ac232bb6-6758-4fc3-a597-043a231b8ea6)
```py
df.shape
```
![image](https://github.com/user-attachments/assets/c5d9f7c5-20c8-4268-aeb4-120c2aaad350)
```py
df.describe()
```
![image](https://github.com/user-attachments/assets/29bcaec9-c0b1-40ff-9619-4d972197eb1a)
```py
df.shape
```
![image](https://github.com/user-attachments/assets/44fc4241-31fc-4d65-86fc-1327386a24c1)
```py
df.nunique()
```
![image](https://github.com/user-attachments/assets/aa22ac07-dd88-4943-b72d-d8bae981f590)
```py
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/d060f8b6-4899-448d-b5f5-a35e9f9b95b4)
```py
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/6ad4e405-c39e-4d08-b5bd-6db933d27334)
```py
sns.countplot(x="Survived",data=df)
```
![image](https://github.com/user-attachments/assets/90f86a50-c40e-46f6-ba8d-fe2e1620eb89)
```py
df
```
![image](https://github.com/user-attachments/assets/2d03e78b-a206-4984-a20b-b09022a22d5d)
```py
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/fe1597e0-38ef-44d8-b02a-2eb7e293eb93)
```py
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/e10eb10e-4baf-4b19-97c9-c92d2f25707e)
```py
 sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/822cefd8-681c-4710-ae2a-20d5242515ce)
```py
 sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/user-attachments/assets/7331c208-d558-4ac7-8442-c52788f73d50)
```py
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/55377bfe-a624-484f-9d41-f653e5b79b32)
```py
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/user-attachments/assets/bc9e3e4e-0cfb-4c61-97b2-ccad3563e36d)
```py
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/user-attachments/assets/b2659c31-25cc-493f-861b-3c83b674fdcb)
```py
fig, ax1 = plt.subplots(figsize=(8,5))
sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![image](https://github.com/user-attachments/assets/790d416f-1b11-48c8-867a-9566718c63d2)
```py
 sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/230d0ae7-142c-4f5c-92d5-6204c6d99b69)
```py
corr = df.select_dtypes(include=['number']).corr()
sns.heatmap(corr,annot=True)
```
```py
sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/2a211a36-6806-4d88-85e1-f2bfcaca0150)

# RESULT
We have performed Exploratory Data Analysis on the given data set successfully.
