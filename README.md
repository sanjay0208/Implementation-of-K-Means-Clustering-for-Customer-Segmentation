# Implementation-of-K-Means-Clustering-for-Customer-Segmentation>

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required :
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm :

1.Import the necessary packages using import statement.

2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3.Import KMeans and use for loop to cluster the data.

4.Predict the cluster and plot data graphs.

5.Print the outputs and end the program

## Program :
```
-------------------------------------------------------------------------
Program to implement the K Means Clustering for Customer Segmentation.
Developed by : Sanjay M
RegisterNumber : 212222110038
-------------------------------------------------------------------------
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("Mall_Customers.csv")

data.head()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss=[]

for i in range(1,11):
  kmeans=KMeans(n_clusters=i,init="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No.of clusters")
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
plt.title("Customer Segments")
  
```

## Output:

### data.head()

![image](https://github.com/Pradeeppachiyappan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118707347/f2904ef4-4ac6-4d70-9091-d8d8c124e711)

### data.info()

![image](https://github.com/Pradeeppachiyappan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118707347/cb4c4424-25b3-4f58-9d2a-891e9686c78b)

### data.isnull.sum()

![image](https://github.com/Pradeeppachiyappan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118707347/dd848006-57e9-4d03-91dc-d976a155051c)

### Elbow Method Graph:

![image](https://github.com/Pradeeppachiyappan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118707347/37ed90ed-b00b-44cc-8b1b-f3f9940e5439)

### KMeans clusters:

![image](https://github.com/Pradeeppachiyappan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118707347/50602d46-9c77-4c15-9977-cdbb71e67808)

### y_predicton:

![image](https://github.com/Pradeeppachiyappan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118707347/f16f1269-f4cf-4721-a7ac-a8bd239fed8a)

### Customer Segments Graph:

![image](https://github.com/Pradeeppachiyappan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118707347/742327ee-68d7-4d31-9741-cefd88031699)


## Result :
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
