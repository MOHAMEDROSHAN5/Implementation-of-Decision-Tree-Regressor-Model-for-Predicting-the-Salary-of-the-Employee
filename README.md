# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

# Algorithm
### Step1:
Import the required libraries.
### Step2:
Upload the csv file and read the dataset.
### Step3: 
Check for any null values using the isnull() function.
### Step4:
From sklearn.tree inport DecisionTreeRegressor.
### Step5: 
Import metrics and calculate the Mean squared error.
### Step6: 
Apply metrics to the dataset, and predict the output.

## Program:
```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: MOHAMED ROSHAN S
RegisterNumber:  212222040101
*/
```
```py
import pandas as pd
data=pd.read_csv('Salary.csv')
data.head()

data.info()

data.isnull().sum()

data["Level"].value_counts()

from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()

data["Position"]=le.fit_transform(data["Position"])
data.head()

data.info()

x=data[["Position","Salary"]]
x.head()

y=data[["Level"]]

from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=100)

from sklearn.tree import DecisionTreeClassifier
dt=DecisionTreeClassifier()
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)

from sklearn.metrics import mean_squared_error
mse = mean_squared_error(y_test,y_pred)
print(mse)

from sklearn.metrics import r2_score
r=r2_score(y_test,y_pred)
print(r)

dt.predict([[4,70000]])



```

## OUTPUT

## DATA HEAD
![ALT](Screenshot%202023-11-08%20210531.png)
## DATA INFO
![ALT](Screenshot%202023-11-08%20210601.png)
## ISNULL & SUM FUNCTION
![ALT](Screenshot%202023-11-08%20210614.png)
## DATA HEAD FOR POSITION
![ALT](Screenshot%202023-11-08%20210637.png)
## MSE VALUE
![ALT](Screenshot%202023-11-08%20210658.png)
## R2 VALUE
![ALT](Screenshot%202023-11-08%20210703.png)
## PREDICTION
![ALT](Screenshot%202023-11-08%20210708.png)

## RESULT:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
