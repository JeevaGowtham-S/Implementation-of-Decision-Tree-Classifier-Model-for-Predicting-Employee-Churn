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
Developed by: AJAY ASWIN M
RegisterNumber:  212222240005
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
![272776023-9d2d241f-6815-4c82-a8f9-a4f98b716269](https://github.com/AJAYASWIN-M/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/118679692/57cc553e-0c29-4645-8b49-e51e72560de9)

### Data.info()
![272776163-7f9ac45a-e910-4aec-a636-8c830dd6f052](https://github.com/AJAYASWIN-M/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/118679692/405cf19f-8cba-4c27-a1e0-3a38373d6b37)

### Isnull() and Sum()
![272776227-067d9b0c-721b-48ae-83c6-cdb3d66866ca](https://github.com/AJAYASWIN-M/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/118679692/12d09743-3e39-4d66-ae2f-43f2eaee994c)

### DataValue Counts()
![272777333-49142d5a-ae0f-4421-be20-0a40656968c0](https://github.com/AJAYASWIN-M/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/118679692/03c876d8-3e76-4868-9951-79e50ef034cf)

### Data.head() for salary
![272777420-cdacd324-81f1-4bf2-a6f8-549641bc35d7](https://github.com/AJAYASWIN-M/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/118679692/15efc1a8-9b27-4131-a155-c89bbb641314)

### X.Head()
![272777475-196f2e85-bd4c-4e75-8512-6d02618cefa6](https://github.com/AJAYASWIN-M/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/118679692/e782ad11-a994-4335-92f6-54c71c5a580b)

### Accuracy Value
![272777484-d70a371b-840c-41db-9f2b-c6d99b2ca673](https://github.com/AJAYASWIN-M/Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn/assets/118679692/424aa879-84e9-4362-87ec-67b44c5f1161)


## Result:
Thus the program to implement the  Decision Tree Classifier Model for Predicting Employee Churn is written and verified using python programming.
