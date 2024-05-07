# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:

To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:

1. Hardware – PCs
   
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

1.Import pandas and matplotlib.pyplot

2.Read the dataset and transform it

3.Import KMeans and fit the data in the model

4.Plot the Cluster graph 

### program:

```
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Nivetha A
RegisterNumber:212222230101

import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("/content/Mall_Customers.csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss=[]

for i in range(1,11):
  kmeans=KMeans(n_clusters=i,init="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No.of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])

y_pred=km.predict(data.iloc[:,3:])
y_pred

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
plt.title("Customer Segments")

```
## Output:

### data.head() function:

![image](https://github.com/nivetharajaa/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/120543388/313733bf-2230-4c10-b189-e8702d134ef8)

### data.info():

![image](https://github.com/nivetharajaa/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/120543388/7ee70b41-d098-4ef7-adea-1c57b206aeb7)

### data.isnull().sum():

![image](https://github.com/nivetharajaa/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/120543388/5658d66d-bd9d-4b94-a2c1-4f9be59bf890)

### Elbow Method Graph:

![image](https://github.com/nivetharajaa/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/120543388/abdc556b-bc55-4fcf-bc86-02b90f07ce44)


### KMeans Clusters:

![image](https://github.com/nivetharajaa/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/120543388/04c1170c-40b3-4f05-9c1f-4390a2f8fc42)

### y-pred:

![image](https://github.com/nivetharajaa/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/120543388/da14c5d4-2845-4d2f-a279-20e34764765f)

### Customer Segment Graph:

![image](https://github.com/nivetharajaa/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/120543388/e6816aa6-88fe-45e1-aaff-e75e5afa4d32)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
