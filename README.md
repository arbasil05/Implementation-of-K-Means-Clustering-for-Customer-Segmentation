# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
#### Step 1: Start 
#### Step 2:Initialization
#### Step 3: Assign data points to clusters
#### Step 4: Update centroids
#### Step 5: Repeat
#### Step 6: Output
#### Step 7: Stop

## Program:

```
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("D:/introduction to ML/jupyter notebooks/Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
    kmeans = KMeans(n_clusters = i,init = "k-means++")
    kmeans.fit(data.iloc[:,3:]) 
    wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No. of clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])
y_pred = km.predict(data.iloc[:,3:])
data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label = "cluster0")
plt.scatter(df1["Annual Income (k$)"], df1["Spending Score (1-100)"], c="blue", label="cluster1")
plt.scatter(df2["Annual Income (k$)"], df2["Spending Score (1-100)"], c="green", label="cluster2")
plt.scatter(df3["Annual Income (k$)"], df3["Spending Score (1-100)"], c="purple", label="cluster3")
plt.scatter(df4["Annual Income (k$)"], df4["Spending Score (1-100)"], c="orange", label="cluster4")

plt.legend()
plt.title("Customer Segments")
plt.show()
```



```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: 
RegisterNumber:  
*/
```

## Output:
### Elbow Method :
![image](https://github.com/arbasil05/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/144218037/aa5eac9a-2336-4c29-8681-019d03a473b4)
### Cluster segmentation:
![image](https://github.com/arbasil05/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/144218037/4b4f73ab-5ec9-43e8-9645-22965cdbf6b8)




## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
