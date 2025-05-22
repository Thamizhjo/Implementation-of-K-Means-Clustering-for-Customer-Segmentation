# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

1. Import the necessary packages using import statement.

2. Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3. Import KMeans and use for loop to cluster the data.

4. Predict the cluster and plot data graphs.

5. Print the outputs and end the program


## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: THAMIZH KUMARAN S
RegisterNumber: 212223240166
*/


import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("Mall_Customers.csv")
data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss = []

for i in range(1,11):
  kmeans = KMeans(n_clusters = i, init = "k-means++")
  kmeans.fit(data.iloc[:, 3:])
  wcss.append(kmeans.inertia_)
  
plt.plot(range(1, 11), wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km = KMeans(n_clusters = 5)
km.fit(data.iloc[:, 3:])

y_pred = km.predict(data.iloc[:, 3:])
y_pred

data["cluster"] = y_pred
df0 = data[data["cluster"] == 0]
df1 = data[data["cluster"] == 1]
df2 = data[data["cluster"] == 2]
df3 = data[data["cluster"] == 3]
df4 = data[data["cluster"] == 4]
plt.scatter(df0["Annual Income (k$)"], df0["Spending Score (1-100)"], c = "red", label = "cluster0")
plt.scatter(df1["Annual Income (k$)"], df1["Spending Score (1-100)"], c = "black", label = "cluster1")
plt.scatter(df2["Annual Income (k$)"], df2["Spending Score (1-100)"], c = "blue", label = "cluster2")
plt.scatter(df3["Annual Income (k$)"], df3["Spending Score (1-100)"], c = "green", label = "cluster3")
plt.scatter(df4["Annual Income (k$)"], df4["Spending Score (1-100)"], c = "magenta", label = "cluster4")
plt.legend()
plt.title("Customer Segments")
```

## Output:

## Dataset:

![Screenshot 2025-05-21 233252](https://github.com/user-attachments/assets/297bb6e1-89ec-49d3-b9e1-6e37e17ca504)


## Info:

![Screenshot 2025-05-21 233301](https://github.com/user-attachments/assets/3d618104-0c44-4a1d-9b72-4eecf1aa9fc5)


## Null values:

![Screenshot 2025-05-21 233308](https://github.com/user-attachments/assets/3616f757-cb77-4c0e-8de8-2e066484cf3c)


## Elbow Plot:

![Screenshot 2025-05-21 233318](https://github.com/user-attachments/assets/a6ce5fc6-296c-4d8c-bd1d-ab605c390184)


## Kmeans :

![Screenshot 2025-05-21 233324](https://github.com/user-attachments/assets/0f2c75d6-074a-4b06-b03b-75d9b4896bf9)


## Predict :

![Screenshot 2025-05-21 233331](https://github.com/user-attachments/assets/61b7e75d-07da-4681-91ce-b353338f95b0)


## Cluster Plot:

![Screenshot 2025-05-21 233338](https://github.com/user-attachments/assets/4fb65794-485c-4cd7-9e5f-7259057b3224)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
