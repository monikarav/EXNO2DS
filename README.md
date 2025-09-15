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
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
df
```

<img width="1626" height="533" alt="image" src="https://github.com/user-attachments/assets/9b6f728a-5805-42dd-b627-824f1a7a6fbf" />

```
df.info()
```
<img width="525" height="427" alt="image" src="https://github.com/user-attachments/assets/a5091df7-e8b1-4942-8e21-e0044edcf108" />

```
df.describe()
```
<img width="777" height="361" alt="image" src="https://github.com/user-attachments/assets/3f16f98b-efbd-4b8f-a184-25e9913155d2" />

```
df.dtypes
```

<img width="336" height="555" alt="image" src="https://github.com/user-attachments/assets/033d6980-659a-4561-a0d3-fbc170db5b40" />

```
df.shape
```
<img width="210" height="51" alt="image" src="https://github.com/user-attachments/assets/ddca1ab2-71ab-4d05-a9fd-7fe92a59c6b6" />

```
df.value_counts()
```

<img width="1586" height="600" alt="image" src="https://github.com/user-attachments/assets/613a2302-d6fb-44db-a3db-2079530db86c" />

```
df['Age'].value_counts()
```
<img width="392" height="605" alt="image" src="https://github.com/user-attachments/assets/f33dbcf5-c0f2-445d-8fb0-a982ec45e9a5" />

```
df.set_index("PassengerId",inplace=True)
df
```
<img width="1602" height="583" alt="image" src="https://github.com/user-attachments/assets/ec9315e8-8073-4be2-8aac-776cc4dd819a" />

```
sns.countplot(data=df,x='Survived')
```
<img width="842" height="597" alt="image" src="https://github.com/user-attachments/assets/848ee218-7979-4dc2-b1d3-3f1412df1939" />

```
df.rename(columns={'Sex': 'Gender'}, inplace=True)
df
```
<img width="1506" height="562" alt="image" src="https://github.com/user-attachments/assets/e0819b80-c1da-4efc-b98a-3bc351f2ef62" />

```
sns.catplot(x='Gender',col='Survived',kind='count',data=df,height=5,aspect=7)
df.boxplot(column="Age",by="Survived")
```
<img width="783" height="606" alt="image" src="https://github.com/user-attachments/assets/de2a29dc-2e73-43a9-99c8-32ca3ec2824c" />

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
<img width="760" height="575" alt="image" src="https://github.com/user-attachments/assets/7ae97e6e-91ce-4499-8753-8ea4492c364d" />

```
plt=sns.boxplot(x='Pclass',y='Age',hue='Gender',data=df)
```
<img width="721" height="492" alt="image" src="https://github.com/user-attachments/assets/38cca4c0-003d-423b-a370-b541c9e90c80" />

```
sns.catplot(x='Pclass',y='Age',hue='Gender',col='Survived',kind='box',data=df)
```
<img width="767" height="396" alt="image" src="https://github.com/user-attachments/assets/6b5ac03e-f343-4c4d-82d0-903815b8a322" />

```
corr=df.corr(numeric_only=True)
sns.heatmap(corr,annot=True)
```
<img width="710" height="557" alt="image" src="https://github.com/user-attachments/assets/dab69961-7b93-46ad-9174-4ca6a8a9c8d6" />















# RESULT
       The given dataset was cleaned by handling missing values and outliers.EDA techniques like countplot, displot, crosstab, and heatmap were applied to gain insights.
