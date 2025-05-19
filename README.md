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

5.Print the outputs and end the program.

## Program:
```.py

/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: THIRUMURUGAN R
RegisterNumber: 212223220118
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
## DATA.HEAD():

![image](https://github.com/user-attachments/assets/0da21897-e5e9-4c64-8aca-d9ec44aa0672)

## DATA.INF0():

![image](https://github.com/user-attachments/assets/91e2a338-c036-479b-ac57-abc3fd0d031a)


## DATA.ISNULL().SUM():


![image](https://github.com/user-attachments/assets/c5d99b4d-0765-4d28-8d0d-85730808aa20)




## PLOT USING ELBOW METHOD:


![image](https://github.com/user-attachments/assets/f90e29cc-9647-46e3-a893-5c186de3f04b)




## K-MEANS CLUSTERING:


![image](https://github.com/user-attachments/assets/5d53880e-395e-41f9-ac5a-fd9702ad6161)




## Y_PRED ARRAY:



![image](https://github.com/user-attachments/assets/45f7402d-e9f2-47f9-b1da-b3ce11d60dd3)

## CUSTOMER SEGMENT:


![image](https://github.com/user-attachments/assets/d5cd8012-1a60-4807-bfe4-ef7bb39371cf)







## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
