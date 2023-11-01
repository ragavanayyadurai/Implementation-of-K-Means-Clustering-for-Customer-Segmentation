# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the necessary packages using import statement.
2. .Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().
3. Import KMeans and use for loop to cluster the data.
4. Predict the cluster and plot data graphs.
5. Print the output and end the program.

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Ragavendran A
RegisterNumber:  212222230114
/*

import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("/content/Mall_Customers (1) (1).csv")
```
```python
data.head()
```
```python
data.info()
```
```python
data.isnull().sum()
```
```python
from sklearn.cluster import KMeans
wcss = []
```
```python
for i in range(1,11):
  kmeans = KMeans(n_clusters = i,init="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)
```
```python
plt.plot(range(1,11),wcss)
plt.xlabel("No . of clusters")
plt.ylabel("wcss")
plt.title("Elbow method")
```
```python
km=KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])
```
```python
y_pred = km.predict(data.iloc[:,3:])
y_pred
```
```python
data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments   ")
```
## Output:

![image](https://github.com/KothaiKumar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121215739/d16401ee-0a7a-41c1-9da9-9a2b1d7023f8)

![image](https://github.com/KothaiKumar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121215739/3e762761-9fa8-428d-81f4-6513a227b86b)

![image](https://github.com/KothaiKumar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121215739/d6c2b1e5-5461-43a6-905a-4766fd44cc0c)

![image](https://github.com/KothaiKumar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121215739/dc1cc3ec-c98b-45cc-8644-7adc8890afac)

![image](https://github.com/KothaiKumar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121215739/c8bb3def-f5ff-42e8-a672-ef945fb09883)

![image](https://github.com/KothaiKumar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121215739/88f28979-9ebf-4376-b9ad-5fb06fdfe0cd)

![image](https://github.com/KothaiKumar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121215739/80f2b622-1a6b-422f-98df-75a32afe60b8)

![image](https://github.com/KothaiKumar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121215739/e458fc92-fb10-43e8-8376-c47dd8522dd2)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
