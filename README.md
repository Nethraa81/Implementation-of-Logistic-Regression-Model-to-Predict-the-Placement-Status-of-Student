# Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student

## AIM:
To write a program to implement the the Logistic Regression Model to Predict the Placement Status of Student.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the required packages and print the present data.
2. Print the placement data and salary data.
3. Find the null and duplicate values.
4. Using logistic regression find the predicted values of accuracy , confusion matrices.
5. Display the results.
## Program:
```
/*
Program to implement the the Logistic Regression Model to Predict the Placement Status of Student.
Developed by: NETHRAA N
RegisterNumber: 24900193 
*/
```

import pandas as pd

data=pd.read_csv(r"C:\Users\admin\Desktop\Placement_Data.csv")

data.head()

data1=data.copy()

data1=data1.drop(["sl_no","salary"],axis=1)

data1.head()

data1.isnull().sum()

data1.duplicated().sum()

from sklearn.preprocessing import LabelEncoder

le=LabelEncoder()

data1["gender"]=le.fit_transform(data1["gender"])

data1["ssc_b"]=le.fit_transform(data1["ssc_b"])

data1["hsc_b"]=le.fit_transform(data1["hsc_b"])

data1["hsc_s"]=le.fit_transform(data1["hsc_s"])

data1["degree_t"]=le.fit_transform(data1["degree_t"])

data1["workex"]=le.fit_transform(data1["workex"])

data1["specialisation"]=le.fit_transform(data1["specialisation"])

data1["status"]=le.fit_transform(data1["status"])

data1

x=data1.iloc[:,:-1]

x

y=data1["status"]

y

from sklearn.model_selection import train_test_split

x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=0)

from sklearn.linear_model import LogisticRegression

lr=LogisticRegression(solver="liblinear")

lr.fit(x_train,y_train)

y_pred=lr.predict(x_test)

y_pred

from sklearn.metrics import accuracy_score

accuracy=accuracy_score(y_test,y_pred)

accuracy

from sklearn.metrics import confusion_matrix

confusion=confusion_matrix(y_test,y_pred)

confusion

from sklearn.metrics import classification_report

classification_report1=classification_report(y_test,y_pred)

print(classification_report1)

lr.predict([[1,80,1,90,1,1,90,1,0,85,1,85]])

## Output:
![the Logistic Regression Model to Predict the Placement Status of Student](sam.png)

## HEAD:

![Screenshot 2024-11-15 172446](https://github.com/user-attachments/assets/15e3f9da-1877-4330-9c5b-31bc90fd24af)

## COPY:

![Screenshot 2024-11-15 172536](https://github.com/user-attachments/assets/3fa0d912-2534-427e-b6a8-3f54c96acfa6)

## FIT TRANSFORM:

![Screenshot 2024-11-15 172630](https://github.com/user-attachments/assets/4fa5b45e-dc92-4e3b-9e4c-3b9b5b7aa89c)

![Screenshot 2024-11-15 172647](https://github.com/user-attachments/assets/14822eeb-f138-428c-94f3-8469c2376135)

## LOGISTIC REGRESSION:

![Screenshot 2024-11-15 172748](https://github.com/user-attachments/assets/189a7ed3-49c7-4108-8495-ce8278ede284)

## ACCURACY SCORE:

![Screenshot 2024-11-15 172923](https://github.com/user-attachments/assets/fe7c8a80-c9fd-45d9-a5bb-a168fe05684c)

## CONFUSION MATRIX:

![Screenshot 2024-11-15 173009](https://github.com/user-attachments/assets/7e767cfc-f8f6-4d7c-b00d-5997bb7a2454)

## CLASSIFICATION REPORT:

![Screenshot 2024-11-15 173053](https://github.com/user-attachments/assets/01c39950-80d1-4f77-9ada-60d0ad7680c2)

## PREDICTION:

![Screenshot 2024-11-15 173142](https://github.com/user-attachments/assets/91d65129-7e6f-4492-b153-4549affed4fe)



## Result:
Thus the program to implement the the Logistic Regression Model to Predict the Placement Status of Student is written and verified using python programming.
