# EXP NO 2

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
![lab02(5)](https://github.com/AkshayalakshmiVS/EXNO2DS/assets/128115963/f88906c6-9297-492f-9503-3f61d38ac697)

```
df["Survived"].value_counts()
```
![lab02(7)](https://github.com/AkshayalakshmiVS/EXNO2DS/assets/128115963/00a55ce8-85c3-4cec-bd0f-be69931bdca1)

```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![lab02(8)](https://github.com/AkshayalakshmiVS/EXNO2DS/assets/128115963/90af63f2-93ee-449b-bc9f-a1506e776d20)

```
sns.countplot(data=df,x="Survived")
```

![lab02(9)](https://github.com/AkshayalakshmiVS/EXNO2DS/assets/128115963/823090a7-7559-45ff-a7e1-a41ecce49ae0)

```
df
```
![lab02(10)](https://github.com/AkshayalakshmiVS/EXNO2DS/assets/128115963/9510f440-d240-4cb1-84c5-533ae425e724)

```
df.Pclass.unique()
```

![lab02(11)](https://github.com/AkshayalakshmiVS/EXNO2DS/assets/128115963/14faf5e5-c191-4eaa-8549-2699d83198c0)

```
df.rename(columns={'sex':'Gender'},inplace=True)
df
```
![lab02(12)](https://github.com/AkshayalakshmiVS/EXNO2DS/assets/128115963/52c3b934-6a43-4f63-9252-d7d0d9bb5e1d)

```
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
sns.catplot(x="Sex",col='Survived',kind="count",data=df,height=5, aspect=.7)
```
![lab02(13)](https://github.com/AkshayalakshmiVS/EXNO2DS/assets/128115963/76d50ddb-0064-4867-af85-62136eb56edf)

```
sns.catplot(x='Survived',hue='Sex',data=df,kind='count')
```
![lab02(14)](https://github.com/AkshayalakshmiVS/EXNO2DS/assets/128115963/3296021c-6de4-4ed8-9a04-4937be5ce50c)

```
df.boxplot(column='Age',by="Survived")
```
![lab02(15)](https://github.com/AkshayalakshmiVS/EXNO2DS/assets/128115963/e10fe226-cce7-4eaf-9b5f-dbac11d20928)

```
sns.scatterplot(x=df['Age'],y=df["Fare"])
```
![lab02(16)](https://github.com/AkshayalakshmiVS/EXNO2DS/assets/128115963/98e64c92-8ff9-4276-8de1-6c53b369ab92)
```
import matplotlib.pyplot as plt
fig,ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Sex',data=df)
```
![lab02(17)](https://github.com/AkshayalakshmiVS/EXNO2DS/assets/128115963/154a4ef6-44c9-4451-8f71-c6c72957a48e)

```
sns.catplot(data=df,col='Survived',x='Sex',hue='Pclass',kind='count')
```
![lab02(18)](https://github.com/AkshayalakshmiVS/EXNO2DS/assets/128115963/34e25f68-d33b-441d-a781-73bf9fe64e80)



```
import seaborn as sns
corr=df.corr()
sns.heatmap(corr,annot=True)
```
![lab02(19)](https://github.com/AkshayalakshmiVS/EXNO2DS/assets/128115963/26c8e6cf-a84f-46ea-870f-f5e8a43924af)


```
sns.pairplot(df)
```
![lab02(20)](https://github.com/AkshayalakshmiVS/EXNO2DS/assets/128115963/d8c0bcfb-1a6c-4dbd-a2a1-6bc00544c649)



# RESULT
     Code are sucessfully executed.
