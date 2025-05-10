# EXNO-6-DS-DATA VISUALIZATION USING SEABORN LIBRARY

# Aim:
  To Perform Data Visualization using seaborn python library for the given datas.

# EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# Algorithm:
STEP 1:Include the necessary Library.

STEP 2:Read the given Data.

STEP 3:Apply data visualization techniques to identify the patterns of the data.

STEP 4:Apply the various data visualization tools wherever necessary.

STEP 5:Include Necessary parameters in each functions.

# Coding and Output:
```python
import seaborn as sns
import matplotlib.pyplot as plt
import pandas as pd
import numpy as np
```

```python
x = [1, 2, 3, 4, 5]
y = [3, 6, 2, 7, 1]
sns.lineplot(x=x,y=y)
```
![image](https://github.com/user-attachments/assets/bb7f0279-62f3-4f2c-857a-3b5305685739)


```python
df = sns.load_dataset("tips")
df
```
![image](https://github.com/user-attachments/assets/73385f6b-16cb-4858-982a-15c0d85b9e39)


```python
sns.lineplot(x="total_bill",y="tip", data=df, hue="sex", linestyle='solid', legend="auto")
```
![image](https://github.com/user-attachments/assets/f305a7bd-03b6-43ce-8068-a943b44156c9)


```python
x=[1, 2, 3, 4, 5]
y1=[3, 5, 2, 6, 1]
y2=[1, 6, 4, 3, 8]
y3=[5, 2, 7, 1, 4]
```

```python
sns.lineplot(x=x, y=y1)
sns.lineplot(x=x, y=y2)
sns.lineplot(x=x, y=y3)
plt.title("Multi-Line Plot")
plt.xlabel('X Label')
plt.ylabel("Y Label")
```
![image](https://github.com/user-attachments/assets/987d4bf6-0c46-4880-8ccc-e95d1d96447f)


```python
tips=sns.load_dataset('tips')
avg_total_bill = tips.groupby('day')['total_bill'].mean()
avg_tip = tips.groupby('day')['tip'].mean()
plt.figure(figsize=(8, 6))
p1 = plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill')
p2 = plt.bar(avg_tip.index, avg_tip, bottom=avg_total_bill, label='Tip')
plt.xlabel('Day of the Week')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()
```
![image](https://github.com/user-attachments/assets/38de4ae2-77e4-4455-aff8-813ebb6b73ae)


```python
avg_total_bill = tips.groupby('time')['total_bill'].mean()
avg_tip=tips.groupby('time') ['tip'].mean()
p1= plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill', width=0.4)
p2 = plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label='Tip', width=0.4)
```
![image](https://github.com/user-attachments/assets/59b5a28b-b4c9-40de-92e9-e1d37ab37924)


```python
years=range(2000, 2012)
apples=[0.895, 0.91, 0.919, 0.926, 0.929, 0.931, 0.934, 0.936, 0.937, 0.9375, 0.9372, 0.939]
oranges = [0.962, 0.941, 0.930, 0.923, 0.918, 0.908, 0.907, 0.904, 0.901, 0.898, 0.9, 0.896, ]

plt.bar(years, apples)
plt.bar(years, oranges, bottom=apples)
```
![image](https://github.com/user-attachments/assets/c4367fa1-5776-4596-b545-6b55a7adf8b2)


```python
import seaborn as sns
dt= sns.load_dataset('tips')
sns.barplot(x='day', y='total_bill', hue='sex', data=dt, palette='Set1')
plt.xlabel('Day of the Week')
plt.ylabel("Total Bill")
plt.title('Total Bill by Day and Gender')
```
![image](https://github.com/user-attachments/assets/349ce90d-eb6c-4b16-b490-88174dc9c6f4)


```python
tit=pd.read_csv("titanic_dataset.csv")
tit
```
![image](https://github.com/user-attachments/assets/8b2d72b5-6f4d-4ba2-add6-b066abfbedb1)


```python
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow')
plt.title("Fare of Passenger by Embarked Town")
```
![image](https://github.com/user-attachments/assets/591e92ac-bb91-4e43-ac45-8357bbd86ee0)


```python
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow', hue='Pclass')
plt.title("Fare of Passenger by Embarked Town, Divided by Class")
```
![image](https://github.com/user-attachments/assets/7ad52430-e60f-440c-8efd-a7ae488177ec)


```python
tips=sns.load_dataset('tips')
sns.scatterplot(x='total_bill', y='tip', hue='sex', data=tips)
plt.xlabel('Total Bill')
plt.ylabel("Tip Amount")
plt.title('Scatter Plot of Total Bill vs. Tip Amount')
```
![image](https://github.com/user-attachments/assets/6b920591-73d8-42fc-8f67-9e912d2fd071)


```python
num_var = np.random.randn(1000)
num_var=pd.Series(num_var, name = "Numerical variable")
num_var
```
![image](https://github.com/user-attachments/assets/5b4e6d9f-39bc-420f-94ab-3865bf018f5f)


```python
sns.histplot(data = num_var, kde = True)
```
![image](https://github.com/user-attachments/assets/69f7997e-9031-455d-bcbb-9a1e686bcd96)


```python
df=pd.read_csv("titanic_dataset.csv")
sns.histplot(data=df,x="Pclass", hue="Survived", kde=True)
```
![image](https://github.com/user-attachments/assets/fda03625-1acc-4dad-b8b1-ab597a00802c)


```python
tips=sns.load_dataset('tips')
sns.boxplot(x=tips['day'], y=tips ['total_bill'], hue=tips['sex'])
```
![image](https://github.com/user-attachments/assets/b3f0e814-f2d3-42d5-b3de-d2962b2c0599)


```python
sns.boxplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, boxprops={"facecolor": "lightblue", "edgecolor": "darkblue"},
whiskerprops={"color": "black", "linestyle": "--", "linewidth": 1.5}, capprops={"color": "black", "linestyle": "--", "linewidth": 1.5})
```
![image](https://github.com/user-attachments/assets/23a03a09-0b49-42e0-bccc-8e7968487974)


```python
sns.violinplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, palette="Set3", inner="quartile")
plt.xlabel("Day of the Week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")
```
![image](https://github.com/user-attachments/assets/cf76e651-1a0d-4dff-923d-8052e256a305)


```python
mart=pd.read_csv("titanic_dataset.csv")
mart
```

![image](https://github.com/user-attachments/assets/75e6b8e9-a9c3-445f-990b-98bd7e3c3361)


```python
mart=mart[['PassengerId', 'Survived', 'Age', 'Name', 'Ticket', 'Embarked']]
mart.head(10)
```
![image](https://github.com/user-attachments/assets/56b612cb-d860-4ba3-9017-8f74196e5579)


```python
sns.kdeplot(data=mart,x='PassengerId')
```
![image](https://github.com/user-attachments/assets/0fb97eeb-ae4f-4da5-aff1-54ed56bb92b6)


```python
sns.kdeplot(data=mart,x='Age')
```
![image](https://github.com/user-attachments/assets/20f07488-30d8-4a2a-ae34-4c1a3daeeb7c)


```python
sns.kdeplot(data=mart)
```
![image](https://github.com/user-attachments/assets/65008564-f958-402b-9d3c-8d6a47c98520)


```python
sns.kdeplot(data=mart,x='PassengerId',hue='Survived',multiple='stack')
```
![image](https://github.com/user-attachments/assets/e8e88cc3-bcb4-4b3c-86c4-d67e81fcde3c)


```python
sns.kdeplot(data=mart,x='PassengerId',y='Survived')
```
![image](https://github.com/user-attachments/assets/8a640374-af35-481a-98fc-c349578192ae)


```python
data = np.random.randint(low = 1, high = 100, size = (10,10))
hm=sns.heatmap(data=data,annot=True)
```
![image](https://github.com/user-attachments/assets/8250012b-bb8f-4fad-a814-7e747fb42164)


```python
hm=sns.heatmap(data=data)
```
![image](https://github.com/user-attachments/assets/e189a204-d2aa-4f0d-9d15-53ce68fe121b)



# Result:
The program has been executed successfully.
