# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
~~~
1.Import the necessary packages using import statement.
2.Read the given csv file using read_csv() method and print the number of the contents to be displayed using df.head().
3.Import KMeans and use for loop to cluster the data.
4.predict the cluster and plot data graphs.
5.Print the outputs and end the program.
~~~

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Mourya .G 
RegisterNumber:212224230170  
*/
```
~~~
import pandas as pd
import matplotlib.pyplot as plt

data = pd.read_csv(r"C:\Users\admin\Downloads\Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()

from sklearn.cluster import KMeans
wcss = []

for i in range(1,11):
    kmeans = KMeans(n_clusters=i, init = "k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No. of clusters")
plt.ylabel("wcss")
plt.title("Elbow method")

km = KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])

y_pred = km.predict(data.iloc[:,3:])
y_pred

data["cluster"] = y_pred

df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster 0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster 1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster 2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster 3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster 4")

plt.legend()
plt.title("customer segmentation")
~~~

## Output:
![440927284-f7d39f9d-bf81-4101-b7ad-16e88c1df2d2](https://github.com/user-attachments/assets/312e214c-d80a-41d3-95de-f25d60787979)
![440927325-c66dbd56-89e9-42db-a22f-ae6f7531150e](https://github.com/user-attachments/assets/d9c5affe-c39c-41bf-ae64-1ec73a1f5b73)
![440927505-71a3ddd0-fa52-4a55-b0e1-399fbd253d70](https://github.com/user-attachments/assets/67c8c7f4-0fa5-4b9e-823e-32341b50bbc0)
![440927546-0898f356-d7f5-482d-bf3e-b6ebd1d4d087](https://github.com/user-attachments/assets/ef22f914-9892-4801-9850-d1b7fc9245a2)
![440927593-fa80dedc-e841-4d48-9f95-b62a745951ec](https://github.com/user-attachments/assets/2118d30a-3f97-4750-a62e-e344ee5198b0)
![440927745-65f4984a-aab3-4a46-a3d3-617f97a03be0](https://github.com/user-attachments/assets/3f9025df-3363-47e0-9776-833c4ebcd3c6)
![440927788-51c2e9d3-585c-493d-b75c-d981c32d34ae](https://github.com/user-attachments/assets/0c74ebd9-183c-4b89-bb1e-b2b476550a87)





## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
