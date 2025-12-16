# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
 
Hardware – PCs
Anaconda – Python 3.7 Installation / Jupyter notebook

## Program:
```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: vignesh s
RegisterNumber:  25014344
*/
import pandas as pd
data=pd.read_csv("Salary.csv")
data.head()

data.info

data.isnull().sum()

from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["Position"]=le.fit_transform(data["Position"])
data.head()

x=data[["Position","Level"]]
y=data[["Salary"]]

from sklearn.model_selection import train_test_split
x_train, x_test, y_train, y_test=train_test_split(x,y,test_size=0.2,random_state=2)

from sklearn.tree import DecisionTreeRegressor
dt=DecisionTreeRegressor()
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)

from sklearn import metrics
mse=metrics.mean_squared_error(y_test, y_pred)
mse

r2=metrics.r2_score(y_test,y_pred)
r2

dt.predict([[5,6]])

```

## Output:


<img width="571" height="237" alt="Screenshot 2025-12-16 105543" src="https://github.com/user-attachments/assets/518f8949-a086-4d4e-a9e0-1baa2e53b980" />

<img width="752" height="233" alt="Screenshot 2025-12-16 105551" src="https://github.com/user-attachments/assets/defb9aea-d0a4-46fe-9419-e9e1b9be7d4c" />

<img width="353" height="111" alt="Screenshot 2025-12-16 105557" src="https://github.com/user-attachments/assets/178697a3-54c4-4eb3-be25-9f0e3a778324" />

<img width="187" height="52" alt="Screenshot 2025-12-16 105605" src="https://github.com/user-attachments/assets/ab149880-a620-488b-bf40-225ad7ceb4ff" />

<img width="318" height="28" alt="Screenshot 2025-12-16 105620" src="https://github.com/user-attachments/assets/f72b5303-dddb-48c2-825c-6706d95dd7a0" />

<img width="288" height="31" alt="Screenshot 2025-12-16 105626" src="https://github.com/user-attachments/assets/becfd281-04a2-45df-92eb-c895bc5e787d" />

## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
