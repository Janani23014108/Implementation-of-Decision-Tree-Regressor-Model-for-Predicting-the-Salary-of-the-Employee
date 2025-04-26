# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Load Data – Import the dataset containing employee details and their salaries.
2. Preprocess Data – Handle missing values, encode categorical variables, and split into training and test sets.
3. Initialize Model – Create a DecisionTreeRegressor with suitable parameters (e.g., max_depth=5).
4. Train Model – Fit the regressor using training data (model.fit(X_train, y_train)).
5. Predict & Evaluate – Predict salaries on test data and evaluate using metrics like MAE, MSE, and R² score.
6. Visualize & Interpret – Plot the tree and analyze feature importance for salary prediction.
 

## Program and Output:
```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: J.JANANI
RegisterNumber:  212223230085
*/
```

```
import pandas as pd
data=pd.read_csv("/content/Salary.csv")
data.head()
```
![436841740-a1a03c2a-4e4f-4a37-aeb1-48778c4981ab](https://github.com/user-attachments/assets/a91cbd50-878d-4869-9360-f7b00819b1c8)

```
data.info()
data.isnull().sum()
```
![436841889-693dfbb7-5633-43ea-a8ac-07fdb9d177c9](https://github.com/user-attachments/assets/281e7ec3-584f-40bb-8215-8e4646df1027)

```
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["Position"]=le.fit_transform(data["Position"])
data.head()
```
![436841972-15326f94-b85a-41bd-ae50-d68f5c1019b2](https://github.com/user-attachments/assets/8148d002-33b7-4994-934f-15dcc8b0aa70)

```
x=data[["Position","Level"]]
x.head()
y=data["Salary"]
y.head()
```
![436842111-4fa53b0b-b28a-4400-9dbd-de9c0f29ff87](https://github.com/user-attachments/assets/5856fcef-ad80-46f9-8e98-c6ba1d21dc78)

```
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=2)

from sklearn.tree import DecisionTreeRegressor
dt=DecisionTreeRegressor()
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)
y_pred
```

![436842266-616230ce-23db-4d89-bb2c-7ce55bed997b](https://github.com/user-attachments/assets/30da3297-2d2b-4cee-a66c-650410f83760)


```
from sklearn import metrics
from sklearn.metrics import r2_score
r2 = r2_score (y_test, y_pred)
r2
```

![436842415-b33524c2-3147-458b-9251-f960abe4b34f](https://github.com/user-attachments/assets/4d6330ee-5f16-4f34-913d-2ba6aa1baa37)

```
dt.predict([[5,6]])
```

![436842535-df6942a1-3494-45ed-83f0-4307f4943273](https://github.com/user-attachments/assets/149318a3-f414-497b-a66b-8d2c86b04da2)


## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
