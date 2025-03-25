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
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
![image](https://github.com/user-attachments/assets/59f118fa-59af-4ef5-bad3-79451e879d92)
```
df.info()
```
![image](https://github.com/user-attachments/assets/e0718605-deb1-4469-aa01-ad69f22d8520)
```
df.shape 
```
![image](https://github.com/user-attachments/assets/e27b9466-a81d-49a2-8c62-d7d395aebebc)
```
df.nunique()
```
![image](https://github.com/user-attachments/assets/7e80aee1-8da7-4caa-ac32-ac87c9f17775)

```
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/2d73e865-fea6-4ce9-a196-9992ef493434)
```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/c592e1b8-c8c1-4969-a60e-daa316587bf4)
```
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/user-attachments/assets/50f40f2a-0047-4a7a-bf06-e6c4b1c22e2a)
```
df
```
![image](https://github.com/user-attachments/assets/bc7dabf3-00fd-43b8-b818-9580fede8807)
```
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/d216cc68-910d-4237-a4d4-313d4dc7e078)
```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/b1e5579a-7fa6-4e29-a7ed-95975cbee8a8)
```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/0ff786bc-f0f2-416f-a164-421834cd5090)
```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/user-attachments/assets/80191146-97fb-42db-a971-00b22b2104b2)
```
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/ebe2e76b-ec32-4e6f-9b80-d0d5e84669f5)
```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/user-attachments/assets/d3aeeb21-253b-4947-a1e1-4a268dc2d32f)
```
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/user-attachments/assets/41984297-1b74-40c6-86b3-336678948b6d)
```
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![image](https://github.com/user-attachments/assets/eef44d85-b217-413f-9a11-65b8198595f6)
```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/4adeab3c-9eef-4d3a-8987-76c69527b8ec)
```
numerical_df = df.select_dtypes(include=np.number)
corr = numerical_df.corr()
sns.heatmap(corr, annot=True)
```
![image](https://github.com/user-attachments/assets/2d369ef6-c220-48e2-a3ee-a5a4d3beb907)
```
sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/55366481-5b54-48ff-8cba-379cbb6a547f)

# RESULT
      Exploratory Data Analysis on the given data set successfully.
