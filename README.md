
<H3>NAME: V MYTHILI</H3>
<H3>REG NO: 212223040123</H3>
<H3>EX NO: 2</H3>

# EDA Analysis using Python

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
dt=pd.read_csv("titanic_dataset.csv")
dt
```

![image](https://github.com/user-attachments/assets/b7b0e093-ad83-4582-ad25-533d0a892bb2)


```
dt.info()
```

![image](https://github.com/user-attachments/assets/c209c169-b67a-43e7-b890-beead962faa2)

```

dt.shape
```

![image](https://github.com/user-attachments/assets/14969779-cb37-47c5-8685-713b62fb1d3e)

```
#dt.set_index("PassengerId",inplace=True)
dt
```

![image](https://github.com/user-attachments/assets/a9c396a2-3a76-465f-8b90-66e47c1c9aa7)

```
dt.describe()
```

![image](https://github.com/user-attachments/assets/a475f15e-b45e-4ca5-84f2-f9caad66ad88)

```
dt.nunique()
```
![image](https://github.com/user-attachments/assets/919af540-cdb6-4a80-967c-fc4c712fc8da)

```
dt["Survived"].value_counts()
```

![image](https://github.com/user-attachments/assets/9eae7390-2604-4309-9dd4-1a226c0abf83)

```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```

![image](https://github.com/user-attachments/assets/9343c988-d002-4498-91c9-d48dd780f4f0)

```
sns.countplot(data=dt,x="Survived")
```


![image](https://github.com/user-attachments/assets/b66c80d1-a8a3-41ef-a68b-c13583fbdfb4)

```
dt.Pclass.unique()
```

![image](https://github.com/user-attachments/assets/695a6038-6167-4a73-8828-6a589af7a0a5)

```
dt.rename(columns={'Sex': 'Gender'}, inplace = True)
dt
```

![image](https://github.com/user-attachments/assets/2c18fc03-6645-4704-9822-5e5cfbf7f371)

```
sns.catplot(x='Gender',col='Survived',kind='count',data=dt,height=5, aspect= 0.7)
```

![image](https://github.com/user-attachments/assets/105a919c-276b-4dd8-b393-b19ba86bbc47)

```
sns.catplot(x='Survived', hue='Gender',data=dt,kind='count')
```

![image](https://github.com/user-attachments/assets/ba8a4378-461c-4974-a2d2-469e6866be91)


```
dt.boxplot(column='Age',by='Survived')
```
![image](https://github.com/user-attachments/assets/1df26b72-61c8-4143-a9cb-37b178591891)

```
sns.scatterplot(x=dt['Age'], y= dt['Fare'])
```

![image](https://github.com/user-attachments/assets/ee0a50d0-25cf-4a3d-8ceb-a6a0a071c9ae)

```
sns.jointplot(x='Age',y='Fare',data=dt)
```

![image](https://github.com/user-attachments/assets/3a000dbf-c4ec-48f7-980c-66956ec003db)

```
sns.catplot(data=dt,col = 'Survived',x='Gender',hue='Pclass',kind='count')
```


![image](https://github.com/user-attachments/assets/4e3c1c55-bcb4-42df-a6a1-47265bb27d61)

```
df = pd.read_csv('/content/titanic_dataset.csv')
df_numeric = df.select_dtypes(include=['number'])
corr = df_numeric.corr()
sns.heatmap(corr,annot=True)
```

![image](https://github.com/user-attachments/assets/8d16b9e5-9c9d-40a1-8beb-b6dc1ef1c788)

```
sns.pairplot(dt)
```

![image](https://github.com/user-attachments/assets/a40ef33f-8e73-49c8-8a93-e1b78d69b7a4)



![image](https://github.com/user-attachments/assets/e21e20c4-9cf2-44e0-ab13-d6b30f544d13)


# RESULT
     Thus, the Exploratory Data Analysis on the given data set was performed successfully.
