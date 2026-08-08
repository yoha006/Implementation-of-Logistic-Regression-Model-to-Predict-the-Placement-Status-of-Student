## Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student

## AIM:
To write a program to implement the the Logistic Regression Model to Predict the Placement Status of Student.

## Equipments Required:
Hardware – PCs
Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
Step 1: start the program

Step 2: Load and preprocess the dataset: drop irrelevant columns, handle missing values, and encode categorical variables using LabelEncoder.

Step 3: Split the data into training and test sets using train_test_split.

Step 4: Create and fit a logistic regression model to the training data.

Step 5: Predict the target variable on the test set and evaluate performance using accuracy, confusion matrix, and classification report.

Step 6:Display the confusion matrix using metrics.ConfusionMatrixDisplay and plot the results.

Step 7:End the program.

## Program:
```
Program to implement the the Logistic Regression Model to Predict the Placement Status of Student.
Developed by: JAYARAJ B
RegisterNumber: 212223043002
```
```
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LogisticRegression
from sklearn.metrics import confusion_matrix,accuracy_score
```
```
dataset=pd.read_csv('Placement.csv')
print(dataset)
```
## Output:
![image](https://github.com/user-attachments/assets/6cfc2506-dda5-4ebe-87b5-d4d853fb67e4)
```
dataset.head()
```
## Output:
![image](https://github.com/user-attachments/assets/72a2d107-6866-4c3e-a457-b4e84a3ccb0e)
```
dataset.tail()
```
## Output:
![image](https://github.com/user-attachments/assets/1578f963-87ee-4a1b-b94e-0d3be2f13730)
```
dataset.info()
```
## Output:
![image](https://github.com/user-attachments/assets/76d2a3b0-4012-44f1-b6f8-deda4cc94001)

```
dataset.drop('sl_no',axis=1,inplace=True)
dataset.info()
```
## Output:
![image](https://github.com/user-attachments/assets/641e9186-5554-4008-92c6-9cbe54af7ee8)
```
dataset["gender"]=dataset["gender"].astype('category')
dataset["ssc_b"]=dataset["ssc_b"].astype('category')
dataset["hsc_b"]=dataset["hsc_b"].astype('category')
dataset["degree_t"]=dataset["degree_t"].astype('category')
dataset["workex"]=dataset["workex"].astype('category')
dataset["specialisation"]=dataset["specialisation"].astype('category')
dataset["status"]=dataset["status"].astype('category')
dataset["hsc_s"]=dataset["hsc_s"].astype('category')
dataset.dtypes
```
## Output:
![image](https://github.com/user-attachments/assets/ab4af9f5-aa7a-46c5-ad6a-85f76e628713)
```
dataset["gender"]=dataset["gender"].cat.codes
dataset["ssc_b"]=dataset["ssc_b"].cat.codes
dataset["hsc_b"]=dataset["hsc_b"].cat.codes
dataset["degree_t"]=dataset["degree_t"].cat.codes
dataset["workex"]=dataset["workex"].cat.codes
dataset["specialisation"]=dataset["specialisation"].cat.codes
dataset["status"]=dataset["status"].cat.codes
dataset["hsc_s"]=dataset["hsc_s"].cat.codes
```
```
dataset.info()
```
## Output:
![image](https://github.com/user-attachments/assets/a3296e42-b0a2-41e5-bd3b-daa0b9fb17ee)
```
dataset.head()
```
## Output:
![image](https://github.com/user-attachments/assets/b74d423d-2cc5-4e03-9289-b5e15ec7ca61)
```
x=dataset.iloc[:,:-1].values 
x
```
## Output:
![image](https://github.com/user-attachments/assets/bd93fb8b-1cf6-4521-b987-bc6ca57259ea)
```
y=dataset.iloc[:,-1].values
y
```
## Output:
![image](https://github.com/user-attachments/assets/97cbc1df-ba85-4283-b6e7-f657f385c44f)
```
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=1)
clf=LogisticRegression()
clf.fit(x_train,y_train)
clf.score(x_test,y_test)
```
## Output:
![image](https://github.com/user-attachments/assets/fa1465f2-eec1-4891-a338-77932b2ef409)

```
y_pred=cf.predict(x_test)
cf.score(x_test,y_test)
```
## Output:
![image](https://github.com/user-attachments/assets/3adc550f-aec6-40e0-bc82-a3efcfab29b7)
```
print(cf)
accuracy=accuracy_score(y_test,y_pred)
print(accuracy)
```
## Output:
![image](https://github.com/user-attachments/assets/39a4f7fb-bfa7-4499-a442-88b26a77ad1b)


## Result:
Thus the program to implement the the Logistic Regression Model to Predict the Placement Status of Student is written and verified using python programming.
