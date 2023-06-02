# Implementation of K Means Clustering for Customer Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.  Import the dataset and print dataset info
2. check for null values
3. Import kmeans and fit it to dataset
4. Plot the graph using elbow method
5. Print the predicted array values
6. Plot the customer segments graph


## Program:
```txt

Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Krupa Varsha P
RegisterNumber:  212220220022
```
```python3
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("/content/Mall_Customers (1).csv")
data.head()
```
```python3
data.info()
```
```python3
data.isnull().sum()
```
```python3
from sklearn.cluster import KMeans
wcss=[]
for i in range(1,11):
  kmeans=KMeans(n_clusters=i,init="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)
```
```python3
plt.plot(range(1,11),wcss)
plt.xlabel("No of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
```
```python3
km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])
```
```python3
y_pred=km.predict(data.iloc[:,3:])
y_pred
```
```python3
data["cluster"]=y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```
## Output:
![Screen Shot 2023-06-02 at 10 04 51 PM](https://github.com/Krupa-Varsha-P/ML_8/assets/100466625/47ccc387-14c3-449d-a394-c745b85c33e3)
![Screen Shot 2023-06-02 at 10 04 55 PM](https://github.com/Krupa-Varsha-P/ML_8/assets/100466625/3a225402-d53c-4fbc-8cea-2407181df701)
![Screen Shot 2023-06-02 at 10 05 02 PM](https://github.com/Krupa-Varsha-P/ML_8/assets/100466625/11fbb4a0-bd3c-40d5-993f-d8b0b20c2596)
![ML8_1](https://github.com/Krupa-Varsha-P/ML_8/assets/100466625/be6a2aa7-8fac-40cf-b88d-da255dd41bda)
![Screen Shot 2023-06-02 at 10 06 08 PM](https://github.com/Krupa-Varsha-P/ML_8/assets/100466625/a9c2aa7e-53e4-458d-be04-40f9c02fe432)
![ML8_2](https://github.com/Krupa-Varsha-P/ML_8/assets/100466625/a055e1c1-2cce-4357-834b-80d31cac6453)





## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
