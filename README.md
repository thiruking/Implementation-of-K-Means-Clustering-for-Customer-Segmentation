# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import dataset and print head,info of the dataset

2.check for null values

3.Import kmeans and fit it to the dataset

4.Plot the graph using elbow method

5.Print the predicted array

6.Plot the customer segments

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: THIRUMALAI K
RegisterNumber:  212224240176
*/
```
```

import pandas as pd

import matplotlib.pyplot as plt

data=pd.read_csv("/content/Mall_Customers (1).csv")

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

plt.xlabel("No_of_Clusters")

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

plt.title("Customer Segment")

```

## OUTPUT:

##1.DATA.HEAD():

![440882074-d58bcdf7-8eb6-429c-82a4-13ec3e3e7ba6](https://github.com/user-attachments/assets/56e5cdc3-8168-4a06-9e66-2eb7e1c15824)

##2.DATA.INF0():

![440882543-5f2b5e24-9d91-4e09-b8aa-29f220438d70](https://github.com/user-attachments/assets/e1456db8-5a33-4c35-9315-96fb097d59d8)

##3.DATA.ISNULL().SUM():

![440882671-67872e89-c256-4c6f-9ea4-1ff6764eb81f](https://github.com/user-attachments/assets/ba761dbf-4bcb-4dc0-b514-8e6cb8c03ebc)

##4.PLOT USING ELBOW METHOD:


![440882771-d0d49335-086d-45dd-9e36-3680d6a4b58f](https://github.com/user-attachments/assets/2d7f4f5f-aa29-467f-9bf0-f3950e26b0a4)

##5.K-MEANS CLUSTERING:

![440883668-97445ebf-ad88-4671-9784-a668be9a7e5c](https://github.com/user-attachments/assets/8d55cb59-ce6b-41ce-a3d2-1060d619a6f6)

##6.Y_PRED ARRAY:

![440883748-b82f4370-138b-46fb-aff9-3e26422cad18](https://github.com/user-attachments/assets/0e1ff4bb-0965-4da6-b206-1a783b6b7699)

##7.CUSTOMER SEGMENT:
![440883860-d2809bfa-4c16-4cff-9648-6d24e2c6dfb9](https://github.com/user-attachments/assets/956c10ae-3c0a-46b3-9e25-19f336932828)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
