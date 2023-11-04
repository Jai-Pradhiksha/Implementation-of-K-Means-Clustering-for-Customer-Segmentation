# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the necessary packages.
2. Read the given csv file and display the few contents of the data.
3. Import KMeans and use for loop to calculate the within cluster sum of squares the data.
4. Plot the wcss for each iteration, also known as the elbow method plot.
5. Predict the clusters and plot them. 

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Jai Pradhiksha D P
RegisterNumber:  212221040062
*/
```
```
import pandas as pd
import matplotlib.pyplot as plt
df=pd.read_csv("Mall_Customers.csv")
df.head()
#checking the data information and null presence
df.info()
df.isnull().sum()


from sklearn.cluster import KMeans
wcss = []  
for i in range(1,11):
    kmeans = KMeans(n_clusters = i,init = "k-means++")
    kmeans.fit(df.iloc[:,3:])
    wcss.append(kmeans.inertia_)


plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
plt.show()


km = KMeans(n_clusters = 5)
km.fit(df.iloc[:,3:])
y_pred = km.predict(df.iloc[:,3:])
df["cluster"] = y_pred
df0 = df[df["cluster"]==0]
df1 = df[df["cluster"]==1]
df2 = df[df["cluster"]==2]
df3 = df[df["cluster"]==3]
df4 = df[df["cluster"]==4]


plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="yellow",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="pink",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="cyan",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="skyblue",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="violet",label="cluster4")
plt.legend()
plt.title("Customer Segments")
plt.show()
```

## Output:
1. data.head()![image](https://github.com/Jai-Pradhiksha/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/100289733/c49d5799-ba7b-4da8-9a1f-3fea2a5a5a41)

2. data.info()![image](https://github.com/Jai-Pradhiksha/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/100289733/bb6a6d46-cac0-41a8-9604-ffb5b513ad9a)

3. data.isnull().sum()![image](https://github.com/Jai-Pradhiksha/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/100289733/001c849a-7aaa-4aaf-b6c6-5656c7decefc)

4. Elbow method![image](https://github.com/Jai-Pradhiksha/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/100289733/505f0076-a137-4217-98a4-b320a9c6ec02)

5. KMeans clusters![image](https://github.com/Jai-Pradhiksha/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/100289733/19c6cd6c-d38b-48b8-9b0d-2af62082c122)

6. array![image](https://github.com/Jai-Pradhiksha/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/100289733/e8a28baa-af4b-4cb4-af88-36e67d1d3da9)

7. Customer Segment graph
   ![image](https://github.com/Jai-Pradhiksha/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/100289733/19293d62-4021-4413-ac65-5f8531acd200)



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
