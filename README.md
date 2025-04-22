# Ex No:09 -- Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

1. Import the libraries and read the data frame using pandas

2. Calculate the null values present in the dataset and apply label encoder.

3.Determine test and training data set and apply decison tree regression in dataset.

4.calculate Mean square error, data prediction and r2.

## Program:
```
Developed by: Gokul Anand.M
RegisterNumber:  21222323040049
```
~~~
import pandas as pd
data=pd.read_csv("Salary.csv")
data.head()
~~~
## Output:
![image](https://github.com/user-attachments/assets/6cfb5c8a-9add-4848-9d53-00b64449940c)

~~~
data.info
~~~
## Output:
![image](https://github.com/user-attachments/assets/f6a4100f-3d87-436c-adb1-5afe95af1c72)

~~~
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["Position"]=le.fit_transform(data["Position"])
data.head()
~~~

## Output:
![image](https://github.com/user-attachments/assets/66420b3d-2b63-491a-86d5-2299c142d98e)

~~~
x=data[["Position","Level"]]
y=data[["Salary"]]
~~~

~~~
from sklearn.model_selection import train_test_split
x_train, x_test, y_train, y_test=train_test_split(x,y,test_size=0.2,random_state=2)
~~~

~~~
from sklearn.tree import DecisionTreeRegressor
dt=DecisionTreeRegressor()
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)
~~~

~~~
from sklearn import metrics
mse=metrics.mean_squared_error(y_test, y_pred)
mse
~~~
## Output:
![image](https://github.com/user-attachments/assets/426d6ef1-9ec8-4dce-8d5f-014bbed565e9)

~~~
r2=metrics.r2_score(y_test,y_pred)
r2
~~~

## Output:
![image](https://github.com/user-attachments/assets/01b795a4-c1c2-4c75-a668-7cb76c15d456)

~~~
dt.predict([[5,6]])
~~~

## Output:
![image](https://github.com/user-attachments/assets/c0f6a476-f7ee-46a8-8514-2e10cbd38ce9)













## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
