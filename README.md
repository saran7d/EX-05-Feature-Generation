# EX-05-Feature-Generation

DATE:

GITHUB LINK: 

COLAB LINK: https://colab.research.google.com/drive/1Dj37e5h_M0y1RLoCYJi88JximNc0xYbh?usp=sharing


## AIM
To read the given data and perform Feature Generation process and save the data to a file. 

# Explanation
Feature Generation (also known as feature construction, feature extraction or feature engineering) is the process of transforming features into new features that better relate to the target.
 

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature Generation techniques to all the feature of the data set
### STEP 4
Save the data to the file


# CODE

# Encoding.csv

```
import pandas as pd
df=pd.read_csv("data.csv")
df

from sklearn.preprocessing import LabelEncoder, OrdinalEncoder
from sklearn.preprocessing import OneHotEncoder

oe=OrdinalEncoder()
df1=df.copy()

df1["City"] = oe.fit_transform(df1[["City"]])
df1["bin_1"] = oe.fit_transform(df1[["bin_1"]])
df1["Ord_1"] = oe.fit_transform(df1[["Ord_1"]])
df1["Ord_2"] = oe.fit_transform(df1[["Ord_2"]])
df1["bin_2"] = oe.fit_transform(df1[["bin_2"]])

df2=df.copy()

#feature scaling
from sklearn.preprocessing import MinMaxScaler
sc=MinMaxScaler()
df2=pd.DataFrame(sc.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'City', 'Ord_1','Ord_2','Target'])
df2

from sklearn.preprocessing import StandardScaler
sc1=StandardScaler()
df3=pd.DataFrame(sc1.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'City', 'Ord_1','Ord_2','Target'])
df3

from sklearn.preprocessing import MaxAbsScaler
sc2=MaxAbsScaler()
df4=pd.DataFrame(sc2.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'City', 'Ord_1','Ord_2','Target'])
df4

from sklearn.preprocessing import RobustScaler
sc3=RobustScaler()
df5=pd.DataFrame(sc3.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'City', 'Ord_1','Ord_2','Target'])
df5

```

# Titanic_dataset.csv
```

import pandas as pd
rf=pd.read_csv("titanic.csv")
rf

#removing unwanted data
rf.drop("Name",axis=1,inplace=True)
rf.drop("Ticket",axis=1,inplace=True)
rf.drop("Cabin",axis=1,inplace=True)  

rf["Age"]=rf["Age"].fillna(rf["Age"].median())
rf["Embarked"]=rf["Embarked"].fillna(rf["Embarked"].mode()[0])

rf.isnull().sum()

rf1=rf.copy()

from sklearn.preprocessing import LabelEncoder, OrdinalEncoder
embark=['S','C','Q']
oe=OrdinalEncoder()

e1=OrdinalEncoder(categories=[embark])
rf1['Embarked'] = e1.fit_transform(rf[['Embarked']])
rf1['Sex'] = oe.fit_transform(rf[['Sex']])
rf1

#feature scaling
from sklearn.preprocessing import MinMaxScaler
sc=MinMaxScaler()
rf0=pd.DataFrame(sc.fit_transform(rf1),columns=['PassengerId', 'Survived', 'Pclass', 'Sex','Age','SibSp','Parch','Fare','Embarked'])
rf0

from sklearn.preprocessing import StandardScaler
sc1=StandardScaler()
rf3=pd.DataFrame(sc1.fit_transform(rf1),columns=['Passenger','Survived','Pclass','Sex','Age','SibSp','Parch','Fare','Embarked'])
rf3

from sklearn.preprocessing import MaxAbsScaler
sc2=MaxAbsScaler()
rf4=pd.DataFrame(sc2.fit_transform(rf1),columns=['Passenger','Survived','Pclass','Sex','Age','SibSp','Parch','Fare','Embarked'])
rf4

from sklearn.preprocessing import RobustScaler
sc3=RobustScaler()
rf5=pd.DataFrame(sc3.fit_transform(rf1),columns=['Passenger','Survived','Pclass','Sex','Age','SibSp','Parch','Fare','Embarked'])
rf5

```

# OUPUT

# Data.csv:

# Initial dataset:

![](https://github.com/saran7d/EX-05-Feature-Generation/blob/main/71.png)

# Encoded dataset:

![](https://github.com/saran7d/EX-05-Feature-Generation/blob/main/72.png)

# Data scaling using MinMaxScaler:

![](https://github.com/saran7d/EX-05-Feature-Generation/blob/main/73.png)

# Data scaling using StandardScalar:

![](https://github.com/saran7d/EX-05-Feature-Generation/blob/main/75.png)

# Data scaling using MaxAbsScaler:

![](https://github.com/saran7d/EX-05-Feature-Generation/blob/main/76.png)

# Data scaling using RobustScaler:

![](https://github.com/saran7d/EX-05-Feature-Generation/blob/main/77.png)

# Encoding.csv:

# Initial dataset:

![](https://github.com/saran7d/EX-05-Feature-Generation/blob/main/78.png)

# Encoded dataset:

![](https://github.com/saran7d/EX-05-Feature-Generation/blob/main/79.png)

# Data scaling using MinMaxScaler:

![](https://github.com/saran7d/EX-05-Feature-Generation/blob/main/80.png)

# Data scaling using StandardScalar:

![](https://github.com/saran7d/EX-05-Feature-Generation/blob/main/81.png)

# Data scaling using MaxAbsScaler:

![](https://github.com/saran7d/EX-05-Feature-Generation/blob/main/82.png)

# Data scaling using RobustScaler:

![](https://github.com/saran7d/EX-05-Feature-Generation/blob/main/83.png)

# Titanic_dataset.csv:

# Initial dataset:

![](https://github.com/saran7d/EX-05-Feature-Generation/blob/main/84.png)

# isnull.sum()

![](https://github.com/saran7d/EX-05-Feature-Generation/blob/main/85.png)

# Encoded dataset:

![](https://github.com/saran7d/EX-05-Feature-Generation/blob/main/86.png)

# Data scaling using MinMaxScaler:

![](https://github.com/saran7d/EX-05-Feature-Generation/blob/main/87.png)

# Data scaling using StandardScalar:

![](https://github.com/saran7d/EX-05-Feature-Generation/blob/main/88.png)

# Data scaling using MaxAbsScaler:

![](https://github.com/saran7d/EX-05-Feature-Generation/blob/main/89.png)

# Data scaling using RobustScaler:

![](https://github.com/saran7d/EX-05-Feature-Generation/blob/main/90.png)

# RESULT:

Feature Generation process and Feature Scaling process is applied to the given data frames sucessfully.


