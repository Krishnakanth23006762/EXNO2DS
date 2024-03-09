# B KRISHNAKANTH
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
```
```
dt=pd.read_csv("/content/titanic_dataset.csv")
dt
```

![1](https://github.com/Krishnakanth23006762/EXNO2DS/assets/138849446/31bf379e-7009-4f01-b389-10d7219f5e17)

```
dt.info()
```

![2](https://github.com/Krishnakanth23006762/EXNO2DS/assets/138849446/68b9de22-e0c9-4d92-8b2b-71df2449970e)

```
dt.shape
```

![3](https://github.com/Krishnakanth23006762/EXNO2DS/assets/138849446/d44b1f32-cfed-48dc-9af0-880612ce5887)

```
dt.set_index("PassengerId",inplace=True
```
dt.describe()

![4](https://github.com/Krishnakanth23006762/EXNO2DS/assets/138849446/5b5cdae0-e600-4e79-a5ee-a093dd05f913)


```
dt.nunique()
```
![5](https://github.com/Krishnakanth23006762/EXNO2DS/assets/138849446/159c8ada-2997-41dd-95c6-ebfc7903ebf5)


```
dt["Survived"].value_counts()
```

![6](https://github.com/Krishnakanth23006762/EXNO2DS/assets/138849446/7bfa59bf-427e-4f80-addd-066864ac8ee6)

```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```
![7](https://github.com/Krishnakanth23006762/EXNO2DS/assets/138849446/a5e34476-2410-4bee-91be-5838149bfc26)

```
sns.countplot(data=dt,x="Survived")
```

![8](https://github.com/Krishnakanth23006762/EXNO2DS/assets/138849446/dadcc2d4-cf89-4a5c-b846-dea3947cdab7)

```
dt
```

![9](https://github.com/Krishnakanth23006762/EXNO2DS/assets/138849446/83a72182-d4d7-44d9-9793-ce627edd878c)

```
dt.Pclass.unique()
```
![10](https://github.com/Krishnakanth23006762/EXNO2DS/assets/138849446/6a308d99-0179-43f1-bd66-1efe27a04414)

```
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
```

![11](https://github.com/Krishnakanth23006762/EXNO2DS/assets/138849446/35a35ed4-0a8b-4164-8e46-6cda230f32db)


```
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5, aspect=.7)
```
![12](https://github.com/Krishnakanth23006762/EXNO2DS/assets/138849446/34dad3ae-65be-443c-b9d2-312f75d75334)


```
sns.catplot(x='Survived',hue="Gender",data=dt,kind="count")
```
![13](https://github.com/Krishnakanth23006762/EXNO2DS/assets/138849446/07b63315-6dda-4e75-9406-502c38d48cfa)

```
dt.boxplot(column="Age",by="Survived")
```

![14](https://github.com/Krishnakanth23006762/EXNO2DS/assets/138849446/f893e268-0980-4de1-b376-cc7fd8ec67fc)

```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```

![15](https://github.com/Krishnakanth23006762/EXNO2DS/assets/138849446/25be6585-deb0-415a-a16c-1069102a891e)

```
sns.jointplot(x="Age",y="Fare",data=dt)
```

```
import matplotlib.pyplot as plt
fig, ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=dt)
```

![image](https://github.com/23006823/EXNO2DS/assets/138971409/a5473432-41ab-4722-872e-53037544fdeb)
```
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
```

![image](https://github.com/23006823/EXNO2DS/assets/138971409/7b72bb3b-6824-479c-8703-3d5378b2023e)
```
#co-relation
import seaborn as sns
corr=dt.corr()
sns.heatmap(corr,annot=True)
```

![image](https://github.com/23006823/EXNO2DS/assets/138971409/6b0e3e5a-85cc-489e-92dc-235451d57476)
```
sns.pairplot(dt)
```

![image](https://github.com/23006823/EXNO2DS/assets/138971409/eb83a5af-b99a-41fd-9c84-e0c828434964)
```
# RESULT
The code successfully excuted
