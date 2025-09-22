# EXNO2DS
# AIM:
      To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Da
ta Cleansing,Removing Outliers and Exploratory Data Analysis.

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

<img width="1081" height="492" alt="Screenshot 2025-09-22 105026" src="https://github.com/user-attachments/assets/7edb28b2-bbce-4a72-8fc9-22e733a89d68" />

```
df.info()
```
<img width="471" height="371" alt="Screenshot 2025-09-22 105032" src="https://github.com/user-attachments/assets/f710b0c4-de30-433d-bd26-f2eac9e4d0bf" />

```
df.shape
```
<img width="194" height="67" alt="Screenshot 2025-09-22 105037" src="https://github.com/user-attachments/assets/0470f278-20ed-417c-8fd6-7f5d38c21cf1" />

```
import pandas as pd
df=pd.read_csv("/content/titanic_dataset.csv")
df.set_index("PassengerId",inplace=True)
print(df.set_index)
```
<img width="712" height="782" alt="Screenshot 2025-09-22 105052" src="https://github.com/user-attachments/assets/d9bc9aad-28c9-45fa-8d71-acff6a37bc84" />

```
df.describe()

```
<img width="594" height="277" alt="Screenshot 2025-09-22 105057" src="https://github.com/user-attachments/assets/234fc9a2-47a2-4e9c-b460-cf4c15152b05" />

```
df.nunique()
```
<img width="295" height="235" alt="Screenshot 2025-09-22 105101" src="https://github.com/user-attachments/assets/6df03a7d-4607-4573-b370-febcc0faeeaf" />

```
df["Survived"].value_counts()
```
<img width="335" height="91" alt="Screenshot 2025-09-22 105105" src="https://github.com/user-attachments/assets/4c0ecde5-5a9e-4fe8-8952-6f2095b4b3bf" />

```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
<img width="583" height="114" alt="Screenshot 2025-09-22 105111" src="https://github.com/user-attachments/assets/5094b4b4-305c-450e-b0ee-01d79c982cce" />

```
sns.countplot(data=df,x="Survived")
```
<img width="709" height="485" alt="Screenshot 2025-09-22 105117" src="https://github.com/user-attachments/assets/f6c300fb-a435-474e-b3a2-8f056922384b" />

```
df
```
<img width="1025" height="410" alt="Screenshot 2025-09-22 105133" src="https://github.com/user-attachments/assets/eae6c047-87ac-497e-964c-082787dba3e5" />

```
df.Pclass.unique()
```
<img width="354" height="61" alt="Screenshot 2025-09-22 105138" src="https://github.com/user-attachments/assets/1d8ea09c-7d05-4995-9978-035404f4f09f" />

```
df.rename(columns={'sex':'Gender'},inplace=True)
df
```
<img width="1005" height="416" alt="Screenshot 2025-09-22 105208" src="https://github.com/user-attachments/assets/3065f164-000e-4918-94e7-7694e289b197" />

```
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
sns.catplot(x="Sex",col='Survived',kind="count",data=df,height=5, aspect=.7)
```
<img width="815" height="557" alt="Screenshot 2025-09-22 105532" src="https://github.com/user-attachments/assets/8d04df19-1442-420a-a4f0-426fe2edc262" />

```
sns.catplot(x='Survived',hue='Sex',data=df,kind='count')
```
<img width="753" height="527" alt="Screenshot 2025-09-22 105537" src="https://github.com/user-attachments/assets/18196916-394d-4bec-a4d1-c2fb52dc2858" />

```
df.boxplot(column='Age',by="Survived")
```
<img width="779" height="507" alt="Screenshot 2025-09-22 105544" src="https://github.com/user-attachments/assets/b51c8f12-3049-40bc-9cf5-5212b1a5cc93" />

```
sns.scatterplot(x=df['Age'],y=df["Fare"])
```
<img width="650" height="487" alt="Screenshot 2025-09-22 105551" src="https://github.com/user-attachments/assets/55cc371c-34f6-450b-9ca5-d6a34a5844a1" />

```
import matplotlib.pyplot as plt
fig,ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Sex',data=df)
```
<img width="826" height="499" alt="Screenshot 2025-09-22 105559" src="https://github.com/user-attachments/assets/f91ba56e-4335-42f7-b2bc-6e7771d62586" />

```
sns.catplot(data=df,col='Survived',x='Sex',hue='Pclass',kind='count')
```
<img width="1023" height="516" alt="Screenshot 2025-09-22 105610" src="https://github.com/user-attachments/assets/d283bbcc-7006-4461-9022-8267a668793f" />

```
import seaborn as sns
corr=df.corr()
sns.heatmap(corr,annot=True)
```
<img width="1038" height="651" alt="Screenshot 2025-09-22 105747" src="https://github.com/user-attachments/assets/68d12a5c-1d9d-4a97-8513-7493954bf297" />

```
sns.pairplot(df)
```
<img width="907" height="875" alt="Screenshot 2025-09-22 105802" src="https://github.com/user-attachments/assets/cb833489-5ab3-4b9d-b00b-d1d3173381c8" />


# RESULT

 Code are sucessfully executed.
