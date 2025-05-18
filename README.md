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

## CODING AND OUTPUT:
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
dt=pd.read_csv("titanic_dataset.csv")
dt
```
![Screenshot 2025-03-21 112309](https://github.com/user-attachments/assets/3344eecc-ab86-415e-b21e-cd89f39ac2f4)

```
dt.info()
```
![image](https://github.com/user-attachments/assets/42b422d0-f50d-4e00-96ce-cddd05305ddb)
```
dt.shape[0]
dt.shape[1]
dt.set_index('PassengerId',inplace=True)
dt.describe()
```
![image](https://github.com/user-attachments/assets/ccefc172-4dd2-41f8-ac14-16d17efa79b2)

```
dt['Survived'].value_counts()
per=(dt['Survived'].value_counts()/dt.shape[0]*100).round(2)
per
sns.countplot(data=dt,x='Survived')
```
![image](https://github.com/user-attachments/assets/1a3fae5a-5687-46f1-87ab-ba5dacffc01a)
```
dt.Pclass.unique()
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
```
![image](https://github.com/user-attachments/assets/ece08fc7-1557-4c40-b68c-efe1d6db90c6)
```
sns.catplot(x='Gender',col='Survived',kind='count',data=dt,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/2f9f1092-272b-4f85-951d-5164128bc903)
```
sns.catplot(x='Survived',hue='Gender',data=dt,kind='count')
```
![image](https://github.com/user-attachments/assets/3dd4a125-41f0-4149-b249-3ef30e7baffd)
```
dt.boxplot(column='Age',by='Survived')
```
![image](https://github.com/user-attachments/assets/40ed1bf4-8bbd-4cf4-84f4-a47137306121)
```
sns.scatterplot(x=dt['Age'],y=dt['Fare'])
```

![image](https://github.com/user-attachments/assets/b9b0cac3-c9f0-407c-ab5f-65ceb6eaec21)
```
sns.jointplot(x='Age',y='Fare',data=dt)
```
![image](https://github.com/user-attachments/assets/b1360b09-4bf3-4b40-bb85-03e401ff54bd)

```
fig,ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=dt)

```
![image](https://github.com/user-attachments/assets/5f657791-2f7e-4892-b5be-c102ea073b96)

```
sns.catplot(data=dt,col='Survived',x='Gender',hue='Pclass',kind='count')
```
![image](https://github.com/user-attachments/assets/46ed48ad-33f1-4527-b8e9-230f33dd5e8f)

```
corr=dt.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/user-attachments/assets/b9afc9cc-2251-47e1-a386-ce3837b3e768)

```
sns.pairplot(dt)
```
![Screenshot 2025-03-21 113615](https://github.com/user-attachments/assets/99499374-f0ce-40df-908c-697b04261527)



# RESULT
      Hence EDA analysis for the given dataset is done successfully.
