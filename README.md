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
df=pd.read_csv('titanic_dataset.csv')
df
```

<img width="1502" height="641" alt="Screenshot 2025-09-16 104154" src="https://github.com/user-attachments/assets/f7fab15f-794b-4e38-8640-6ed34c735a49" />

```
df.info()
```
<img width="510" height="491" alt="Screenshot 2025-09-16 104201" src="https://github.com/user-attachments/assets/8bb62a9f-ba87-42ef-997d-fc6e6adbb66b" />


```
df.dtypes
```
<img width="332" height="611" alt="image" src="https://github.com/user-attachments/assets/5a616f5c-961f-4476-ace5-5b6555a75251" />


```
df.describe()
```
<img width="908" height="451" alt="image" src="https://github.com/user-attachments/assets/31407c44-5bd5-4477-88bc-73a74da379aa" />


```
df.value_counts()
```
<img width="1558" height="647" alt="Screenshot 2025-09-16 104225" src="https://github.com/user-attachments/assets/34f872c4-df9e-4c84-bb15-e9e048770e14" />



```
df["Sex"].value_counts()
```


<img width="321" height="263" alt="Screenshot 2025-09-16 104231" src="https://github.com/user-attachments/assets/3b7c27ff-aae7-46a9-84ea-d7001051889e" />

```
df.shape
```
<img width="186" height="99" alt="Screenshot 2025-09-16 104236" src="https://github.com/user-attachments/assets/71189596-80f9-47de-b2ea-ae5cbf0e71bc" />


```
df.set_index("PassengerId",inplace=True)
df.describe()
```

<img width="809" height="442" alt="Screenshot 2025-09-16 104242" src="https://github.com/user-attachments/assets/46024228-e32d-4d4a-88b0-69ff687b945f" />

```
df.nunique()
```
<img width="345" height="592" alt="Screenshot 2025-09-16 104249" src="https://github.com/user-attachments/assets/d3560676-ba13-46b0-95ea-e3a02d06ecf3" />


```
sns.countplot(data=df,x="Survived")
```
<img width="910" height="649" alt="Screenshot 2025-09-16 104257" src="https://github.com/user-attachments/assets/4bf0ab90-1d74-4af2-9100-62b7fafe0724" />


```
df.Pclass.unique()
```

<img width="260" height="105" alt="Screenshot 2025-09-16 104303" src="https://github.com/user-attachments/assets/90cbdd45-66db-46c8-9f4b-bb64323c50fe" />

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
<img width="1554" height="642" alt="Screenshot 2025-09-16 104311" src="https://github.com/user-attachments/assets/ccd005fe-0356-409f-a609-489b79fd51a5" />

```
sns.catplot(data=df,x='Gender',col='Survived',kind="count",height=5,aspect=.7,hue='Gender')
```

<img width="1076" height="743" alt="Screenshot 2025-09-16 104319" src="https://github.com/user-attachments/assets/d4555b01-6a11-4e5e-9ef8-90c530f673d3" />

```
df.boxplot(column="Age",by="Survived")
```

<img width="867" height="673" alt="Screenshot 2025-09-16 104325" src="https://github.com/user-attachments/assets/a220ece7-5c76-4978-9e53-afc0f33749ed" />

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```

<img width="851" height="636" alt="Screenshot 2025-09-16 104335" src="https://github.com/user-attachments/assets/f3eb21a4-f988-451a-a19b-8f0e4964d9c7" />

```
fig, ax1=plt.subplots(figsize=(8,5))
plt=sns.boxplot(ax=ax1,x='Pclass',y='Age',data=df,palette='rainbow',hue='Gender')
```

<img width="940" height="680" alt="Screenshot 2025-09-16 104344" src="https://github.com/user-attachments/assets/92dc5273-8b64-409c-94e3-9d0a02802cd2" />

```
sns.catplot(data=df,x='Gender',col='Survived',kind="count",hue='Pclass',palette='rainbow')
```

<img width="1477" height="700" alt="Screenshot 2025-09-16 104354" src="https://github.com/user-attachments/assets/a79a3b16-0733-41a2-a941-b70b726719d2" />

```
corr=df.select_dtypes(include=np.number).corr()
sns.heatmap(corr,annot=True)
```


<img width="791" height="636" alt="Screenshot 2025-09-16 104402" src="https://github.com/user-attachments/assets/832fd89a-2d31-4b52-b9e7-b02fcafd0bf9" />

# RESULT
        Thus exploratory data analysis on the given data set has been executed successfully.
