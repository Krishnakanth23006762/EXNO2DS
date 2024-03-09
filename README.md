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

![image](https://github.com/23006823/EXNO2DS/assets/138971409/27aae021-a93c-4d62-8700-79b1beaba84e)
```
dt.info()
```

![image](https://github.com/23006823/EXNO2DS/assets/138971409/23c9a813-e29e-458e-b872-c0e96d2b75d4)
```
dt.shape
```

![image](https://github.com/23006823/EXNO2DS/assets/138971409/9b3f8940-f34a-4efe-857c-5c3e286a59f2)
```
dt.set_index("PassengerId",inplace=True
```
dt.describe()

![image](https://github.com/23006823/EXNO2DS/assets/138971409/603a6476-0b6e-4939-be1d-020a5411eb5a)

```
dt.nunique()
```

![image](https://github.com/23006823/EXNO2DS/assets/138971409/e5e1049e-0421-4ed2-9d7c-15e0a7f0317b)

```
dt["Survived"].value_counts()
```

![image](https://github.com/23006823/EXNO2DS/assets/138971409/19899d18-deb2-459d-8d6f-9610872d098f)
```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```

![image](https://github.com/23006823/EXNO2DS/assets/138971409/453f521f-e016-450a-823e-853513864c8a)
```
sns.countplot(data=dt,x="Survived")
```

![image](https://github.com/23006823/EXNO2DS/assets/138971409/b38c5a88-9b85-4e68-a1fd-f25fb35da7d5)
```
dt
```

![image](https://github.com/23006823/EXNO2DS/assets/138971409/75851857-515c-45a4-9ed0-f97bc501ac02)
```
dt.Pclass.unique()
```

![image](https://github.com/23006823/EXNO2DS/assets/138971409/4868a17d-a4de-45c3-86e4-c769762d77ca)
```
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
```

![image](https://github.com/23006823/EXNO2DS/assets/138971409/822c7791-fb41-44bb-8c23-8b8d1a3d811c)

```
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5, aspect=.7)
```

![image](https://github.com/23006823/EXNO2DS/assets/138971409/fdadc299-3453-47ae-86cd-8bd9e77120a1)
```
sns.catplot(x='Survived',hue="Gender",data=dt,kind="count")
```

![image](https://github.com/23006823/EXNO2DS/assets/138971409/7fb380ba-e219-4d79-aa78-c9591ddcb8b6)
```
dt.boxplot(column="Age",by="Survived")
```

![image](https://github.com/23006823/EXNO2DS/assets/138971409/c84bad98-5cd5-4faf-9d15-85d0645205d9)
```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```

![image](https://github.com/23006823/EXNO2DS/assets/138971409/089a4887-89a2-47b9-9f11-ef75e3016301)
```
sns.jointplot(x="Age",y="Fare",data=dt)
```

![image](https://github.com/23006823/EXNO2DS/assets/138971409/3b43d8e9-fb94-4e0f-ac9a-d31b70eaeb77)
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
