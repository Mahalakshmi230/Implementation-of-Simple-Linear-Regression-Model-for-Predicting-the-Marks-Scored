# Implementation-of-Simple-Linear-Regression-Model-for-Predicting-the-Marks-Scored

## AIM:
To write a program to predict the marks scored by a student using the simple linear regression model.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the standard Libraries.
2. Set variables for assigning dataset values.
3. Import linear regression from sklearn.
4. Assign the points for representing in the graph
5. Predict the regression for marks by using the representation of the graph.
6. Compare the graphs and hence we obtained the linear regression for the given datas.
## Program:
```
/*
Program to implement the simple linear regression model for predicting the marks scored.
Developed by: MAHALAKSHMI R
RegisterNumber: 212223230116
*/
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
df=pd.read_csv('student_scores.csv')
#displaying the content in datafile 
df.head()

df.tail()

# Segregating data to variables
X = df.iloc[:,:-1].values
X

Y=df.iloc[:,1].values
Y

#splitting train and test data
from sklearn.model_selection import train_test_split
X_train,X_test,Y_train,Y_test=train_test_split(X,Y,test_size=1/3,random_state=0)
from sklearn.linear_model import LinearRegression
regressor=LinearRegression()
regressor.fit(X_train,Y_train)
Y_pred=regressor.predict(X_test)
#displaying predicted values
Y_pred
#displaying actual values
Y_test

#graph plot for training data
plt.scatter(X_train,Y_train,color="pink")
plt.plot(X_train,regressor.predict(X_train),color="red")
plt.title("Hours vs Scores (Training Set)")
plt.xlabel("Hours")
plt.ylabel("Scores")
plt.show()

#graph plot for test data
plt.scatter(X_test,Y_test,color="orange")
plt.plot(X_train,regressor.predict(X_train),color="yellow") 
plt.title("Hours vs Scores (Test Set)")
plt.xlabel("Hours")
plt.ylabel("Scores")
plt.show()
```

## Output:
## Contents in the data file (head, tail):
![Screenshot 2024-08-17 205605](https://github.com/user-attachments/assets/3ad5ed58-0065-4e57-9a00-024277758f05)


## X and Y datasets from original dataset:
![Screenshot 2024-08-17 205646](https://github.com/user-attachments/assets/000a0ee0-b2aa-4398-a56b-75c2095bc241)


## Predicted and Test values of Y:
![Screenshot 2024-08-17 205710](https://github.com/user-attachments/assets/d2a852a2-8402-49fd-ac25-935769facc36)


## Graph for Training Data:
![Screenshot 2024-08-17 205733](https://github.com/user-attachments/assets/f13752f3-ad2b-4ccd-9d2c-6d4e342aae48)


## Graph for Test Data:
![Screenshot 2024-08-17 205758](https://github.com/user-attachments/assets/95215c63-fb67-4242-b281-02188acde5e9)


## Result:
Thus the program to implement the simple linear regression model for predicting the marks scored is written and verified using python programming.
