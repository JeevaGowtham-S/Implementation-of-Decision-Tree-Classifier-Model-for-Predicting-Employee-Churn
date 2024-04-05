# EXPERIMENT-06--Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn

## AIM:
To write a program to implement the Decision Tree Classifier Model for Predicting Employee Churn.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook
`
## Algorithm
1. import pandas module and import the required data set.
2. Find the null values and count them.
3. Count number of left values.
4. From sklearn import LabelEncoder to convert string values to numerical values.
5. From sklearn.model_selection import train_test_split.
6. Assign the train dataset and test dataset.
7. From sklearn.tree import DecisionTreeClassifier.
8. Use criteria as entropy.
9. From sklearn import metrics. 10.Find the accuracy of our model and predict the require values.
`
## Program:
```py
Program to implement the Decision Tree Classifier Model for Predicting Employee Churn.
Developed by: JEEVAGOWTHAM S
RegisterNumber:  212222230053
```
```py
import pandas as pd
data = pd.read_csv("Employee.csv")
data.head()
data.info()

data.isnull().sum()

data["left"].value_counts

from sklearn.preprocessing import LabelEncoder
le= LabelEncoder()
data["salary"]=le.fit_transform(data["salary"])
data.head()

x= data[["satisfaction_level","last_evaluation","number_project","average_montly_hours","time_spend_company","Work_accident","promotion_last_5years","salary"]]

x.head()
y=data["left"]

from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test = train_test_split(x,y,test_size=0.2,random_state = 100)


from sklearn.tree import DecisionTreeClassifier
dt = DecisionTreeClassifier(criterion="entropy")
dt.fit(x_train,y_train)

y_pred = dt.predict(x_test)
from sklearn import metrics

accuracy = metrics.accuracy_score(y_test,y_pred)
accuracy

dt.predict([[0.5,0.8,9,260,6,0,1,2]])
```

## Output:
### Data.head()
![image](https://github.com/JeevaGowtham-S/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/118042624/e8ef305c-b8d7-4e86-9b70-2f5bbfcc1ed9)


### Data.info()
![image](https://github.com/JeevaGowtham-S/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/118042624/768d1601-8a40-4e00-a13e-0c3ef777d272)


### Isnull() and Sum()
![image](https://github.com/JeevaGowtham-S/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/118042624/48748818-5c61-42c6-acf7-486fc60f55bb)


### DataValue Counts()
![image](https://github.com/JeevaGowtham-S/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/118042624/e2b0397f-4d1c-4691-9094-3ba2645c7261)


### Data.head() for salary
![image](https://github.com/JeevaGowtham-S/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/118042624/7822ef44-1798-4594-a3b2-b13a4a2b3879)

### X.Head()
![image](https://github.com/JeevaGowtham-S/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/118042624/c76e6fb0-47d6-41a9-bfd6-f6c97631231e)

### Accuracy Value
![image](https://github.com/JeevaGowtham-S/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/118042624/9765d15e-75fa-48b8-b188-f41d972b3ab1)


## Result:
Thus the program to implement the  Decision Tree Classifier Model for Predicting Employee Churn is written and verified using python programming.
