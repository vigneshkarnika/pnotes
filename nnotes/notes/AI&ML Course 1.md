---
tags: [programming]
title: AI&ML Course 1
created: '2021-03-22T12:52:25.747Z'
modified: '2021-03-23T06:13:14.936Z'
---

# AI&ML Course 1

## pandas

```
https://www.kaggle.com/c/titanic/data
```
Download Train Data Set 


### DF functions
```py
import numpy as np
import pandas as pd
df=pd.read_csv('train.csv')
df.head() #show top rows for preview
df.tail()
df.head(10) #show top rows for preview
df.tail(23)
df.shape #displays rows and cols (891 rows, 12 cols)
df['Survived'] #displays only survived rows
df['Survived'].sum() # sum of all survived
df['Survived'].unique() # gives possible values of that cols
diefdf=df['Survived']==0
diefdf.sum()
diefdf.mean() 
#0.6161616161616161
diefdf.unique()
# array([ True, False])
diefdf.nunique()
#2


diefdf.describe()
#count      891
#unique       2
#top       True
#freq       549
#Name: Survived, dtype: object

df.dtypes

#PassengerId      int64
#Survived         int64
#Pclass           int64
#Name            object
#Sex             object
#Age            float64
#SibSp            int64
#Parch            int64
#Ticket          object
#Fare           float64
#Cabin           object
#Embarked        object
#dtype: object
```


### DF Subsetting(kind of sql select)

```py
df[df['Survived']==1].tail() 
df[(df['Survived']==1) & (df['Sex']=='female')].tail() 
```

### loc and iloc
```py
df.sample(frac=1)
ft=df.tail(10)
ft.loc[0] # this is index name
ft.iloc[0] # this is index position
df.loc[0,["Name","Sex"]]
df.loc[0,"Name"]
df.iloc[0,[0,2]]
df.iloc[2:-1]

```


### map and apply

```py
df.sort_index(inplace=True)

fnd=df['Name'].values[-10:][0]
#'Markun, Mr. Johann'
fnd.split(",")[0]
df['Name']=df['Name'].map(lambda name:name.split(",")[0])

# apply does more than a map - need to do something across rows
df['Name']=df.apply(lambda dfv:dfv['Name'].split(",")[0] +"-"+ str(dfv['Age']),axis=1)
```


### GroupBy
```py
df.groupby("Pclass")["Age"].apply(lambda age:age.isnull().sum())

#Pclass
#1     30
#2     11
#3    136
#Name: Age, dtype: int6

df.groupby("Survived")["Age"].apply(lambda age:age.isnull().sum())
#Survived
#0    125
#1     52
#Name: Age, dtype: int64


df.groupby("Pclass").agg({"Age":[sum,min,max,np.mean]})
```


## Numpy


