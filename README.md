# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the necessary packages using import statement.

2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3.Import KMeans and use for loop to cluster the data.

4.Predict the cluster and plot data graphs.

5.Print the outputs and end the program
## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Vishal S
RegisterNumber:  212223110063
```
*/
```
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
  kmeans = KMeans (n_clusters = i, init ="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("no of cluster")
plt.ylabel("wcss")
plt.title("Elbow Metthod")
km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])
y_pred = km.predict(data.iloc[:,3:])
y_pred
data["cluster"]=y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="pink",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="green",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="blue",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="black",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```

## Output:
## Dataset:
![1](https://github.com/vishal23000591/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/147139719/9d97df49-7ad1-4425-86e3-2c679c8895f8)

## Dataset information:
![2](https://github.com/vishal23000591/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/147139719/94c942ef-865b-4886-9dfe-109c8349fcd6)

![3](https://github.com/vishal23000591/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/147139719/8aaa5baf-70c1-4ed7-bf41-7640807d2ecd)

## Elbow method graph (wcss vs each iteration):
![4](https://github.com/vishal23000591/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/147139719/43cc1edc-c620-454b-9115-952b0b3b613a)

## Cluster represnting customer segments-graph:
![5](https://github.com/vishal23000591/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/147139719/b2cc4273-3aab-4f69-b086-42f03e07c889)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
