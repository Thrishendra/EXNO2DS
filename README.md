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
```PY
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```
```PY
dt=pd.read_csv('titanic_dataset.csv')
dt
```
## OUTPUT:
![image](https://github.com/user-attachments/assets/7a5a6753-d9a6-4639-acb8-00ba9273cf53)

```PY
dt.info()
```

## OUTPUT:
![image](https://github.com/user-attachments/assets/e01bc954-b26e-4629-8b6d-600631332425)

```PY
dt.shape
```

## OUTPUT:
![image](https://github.com/user-attachments/assets/b1175bae-0558-46fa-ba29-efdeecb5ebc4)

```PY
dt.set_index('PassengerId',inplace=True)
```
```PY
dt.describe()
```

## OUTPUT:
![image](https://github.com/user-attachments/assets/84d61da5-6986-497d-8968-614225422099)

```PY
dt.nunique()
```

## OUTPUT:
![image](https://github.com/user-attachments/assets/c9208630-5b8c-4823-823d-eca0792130dc)

```PY
dt["Survived"].value_counts()
```

## OUTPUT:
![image](https://github.com/user-attachments/assets/cf79bcec-fa6b-4fbf-ae9a-2e61f2aaa587)

```PY
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```

## OUTPUT:
![image](https://github.com/user-attachments/assets/267215bd-4b2e-46bf-855b-19f82f261ddc)

```PY
sns.countplot(data=dt,x='Survived')
```

## OUTPUT:
![image](https://github.com/user-attachments/assets/eeaf076e-b1c4-49a1-b931-05aea17c340f)

```PY
dt
```

## OUTPUT:
![image](https://github.com/user-attachments/assets/62421596-5661-417e-ba4e-5d0a342f4e7c)

```PY
dt.Pclass.unique()
```

## OUTPUT:
![image](https://github.com/user-attachments/assets/f85ffc4d-68a8-4895-921e-008afc6cacc2)

```PY
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
```
## OUTPUT:
![image](https://github.com/user-attachments/assets/a152ca4b-22c7-49d2-8474-8f404c0d2c84)

```PY
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
```
## OUTPUT:
![image](https://github.com/user-attachments/assets/3eed7a03-863f-43b6-9365-bfa71b42c299)

```PY
import seaborn as sns
sns.catplot(x="Survived",data=dt,kind="count") # Changed X to x
```

## OUTPUT:
![image](https://github.com/user-attachments/assets/83111cc8-528a-43d6-8847-9e951870ae67)

```PY
dt.boxplot(column="Age",by="Survived")
```

## OUTPUT:
![image](https://github.com/user-attachments/assets/ec303f67-ade2-4222-983a-76f16235bce5)

```PY
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```

## OUTPUT:
![image](https://github.com/user-attachments/assets/22952110-5d60-435d-98b8-f4fc9ab880a3)

```PY
sns.jointplot(x="Age",y="Fare",data=dt)
```

## OUTPUT:
![image](https://github.com/user-attachments/assets/6c564d00-4eb5-4a09-82b9-373fe8f87499)

```PY
fig, ax1 = plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=dt)
```
## OUTPUT:
![image](https://github.com/user-attachments/assets/d303b23e-baa7-4f1c-81da-e2f00bbcce18)

```PY
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
```

## OUTPUT:
![image](https://github.com/user-attachments/assets/d5f868b5-e493-42b6-bdee-3b3a618c36d8)

```PY
dt = dt.select_dtypes(include=np.number)
corr = dt.corr()
sns.heatmap(corr, annot=True)
```

## OUTPUT:
![image](https://github.com/user-attachments/assets/7ae16a9f-a986-4f09-82d0-d98bb52fe3d5)

```PY
sns.pairplot(dt)
```

## OUTPUT:
![image](https://github.com/user-attachments/assets/35a0b54c-4923-40ae-bdbe-e9e917adebba)

# RESULT
       Hence, The EDA Analysis of an given sample has been analised successfully.
