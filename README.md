# EXP NO 2  EDA ANALYSIS USING PYTHON

### NAME : SARANYA S
### REG NO : 212223110044
## AIM:
      To perform Exploratory Data Analysis on the given data set.
      
## EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
## ALGORITHM:
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
![lab02](https://github.com/AkshayalakshmiVS/EXNO2DS/assets/128115963/ad910c75-3f6b-455d-be51-ac5cc92b7482)

```
df.info()
```
![lab02(1)](https://github.com/AkshayalakshmiVS/EXNO2DS/assets/128115963/ffdc7bf5-442d-46d4-bb90-582ef03adf8b)

```
df.shape
```
![lab02(2)](https://github.com/AkshayalakshmiVS/EXNO2DS/assets/128115963/67cef4ed-e81c-48f4-a2b7-9774461c2409)

```
import pandas as pd
df=pd.read_csv("/content/titanic_dataset.csv")
df.set_index("PassengerId",inplace=True)
print(df.set_index)
```
![lab02(3)](https://github.com/AkshayalakshmiVS/EXNO2DS/assets/128115963/34f3bcbf-a69b-47a9-9cc7-3b8fc59df9f9)

```
df.describe()
```
![lab02(4)](https://github.com/AkshayalakshmiVS/EXNO2DS/assets/128115963/8c940ad5-ebd1-4594-be50-1b8a4de34e36)

```
df.nunique()
```
![image](https://github.com/user-attachments/assets/9b129701-21cf-48c9-ad3b-85cf8962eddd)


```
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/ea036f49-9e55-46b9-83ca-94aa03d9401f)

```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/85103464-9aad-4207-8bcb-1e09ffa2cd52)


```
sns.countplot(data=df,x="Survived")
```

![image](https://github.com/user-attachments/assets/093dfd81-f4db-421e-84c9-20918fb5ff71)


```
df
```
![image](https://github.com/user-attachments/assets/c0078901-c724-4992-84f3-d4c092f1c9ec)


```
df.Pclass.unique()
```

![image](https://github.com/user-attachments/assets/d1ef664b-c756-4f7a-914f-67dc1890a60a)


```
df.rename(columns={'sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/37e6ac63-33da-41f5-b65c-1ef3a50012ce)


```
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
sns.catplot(x="Sex",col='Survived',kind="count",data=df,height=5, aspect=.7)
```
![image](https://github.com/user-attachments/assets/c5392995-24c3-4790-835e-f4093e2f5e4b)


```
sns.catplot(x='Survived',hue='Sex',data=df,kind='count')
```
![image](https://github.com/user-attachments/assets/b97f59a2-c0ad-4466-b55e-a148a605e7b5)


```
df.boxplot(column='Age',by="Survived")
```
![image](https://github.com/user-attachments/assets/689c86e3-8665-46f1-97e3-c9a2606d2eed)


```
sns.scatterplot(x=df['Age'],y=df["Fare"])
```
![image](https://github.com/user-attachments/assets/cb0804a9-923e-4a08-bcb8-ac40b65341ae)

```
import matplotlib.pyplot as plt
fig,ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Sex',data=df)
```
![image](https://github.com/user-attachments/assets/b55fc3cf-b77e-4cf2-a3e2-1de5f7ffdbf2)


```
sns.catplot(data=df,col='Survived',x='Sex',hue='Pclass',kind='count')
```
![image](https://github.com/user-attachments/assets/6bcb9b90-6c7f-4699-9bea-6302535c92bd)

```
import seaborn as sns
corr=df.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/user-attachments/assets/bffd46df-1f86-4868-af9e-b3fefe2384f5)


```
sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/4e3d4713-4432-4bb1-a37a-45cbbccd6710)



# RESULT
     Code are Sucessfully Executed.
