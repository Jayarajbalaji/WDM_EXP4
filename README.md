### EX4 Implementation of Cluster and Visitor Segmentation for Navigation patterns

### AIM: To implement Cluster and Visitor Segmentation for Navigation patterns in Python.
### Description:
<div align= "justify">Cluster visitor segmentation refers to the process of grouping or categorizing visitors to a website, 
  application, or physical location into distinct clusters or segments based on various characteristics or behaviors they exhibit. 
  This segmentation allows businesses or organizations to better understand their audience and tailor their strategies, marketing efforts, 
  or services to meet the specific needs and preferences of each cluster.</div>
  
### Procedure:
1) Read the CSV file: Use pd.read_csv to load the CSV file into a pandas DataFrame.
2) Define Age Groups by creating a dictionary containing age group conditions using Boolean conditions.
3) Segment Visitors by iterating through the dictionary and filter the visitors into respective age groups.
4) Visualize the result using matplotlib.

### Program:
```python
import pandas as pd
df = pd.read_csv('/content/clustervisitor (Salary).csv')
df
cluster={'Young':(df['Age']<=30),'Middle':((df['Age'])>30 & (df['Age']<=50)),'Old':(df['Age']>50)}
cluster
count=[]
for g,c in cluster.items():
    visitor=df[c]
    count.append(len(visitor))
    print(f"Visitors in {g} group")
    print(visitor)
    print(count)
```
### Output:
<img width="607" height="1197" alt="image" src="https://github.com/user-attachments/assets/7503e6ad-6cce-4d8d-bb24-0b83b2210cd0" />

### Visualization:

```python
import matplotlib.pyplot as plt
plt.figure(figsize=(8,6))
plt.bar(list(cluster.keys()),count,color='skyblue')
plt.xlabel('Age Group')
plt.ylabel('Number of Visitors')
plt.title('Visitors distribution Across Age Groups')
plt.show()
```
```python
from sklearn.preprocessing import StandardScaler
from sklearn.cluster import KMeans
df3 = df[['Age', 'Salary']]
scaler=StandardScaler()
scaldata=scaler.fit_transform(df3)
kmeans=(KMeans(n_clusters=3, random_state=42))
df3['cluster']=kmeans.fit_predict(df3)

plt.scatter(df3['Age'],df3['Salary'],c=df3['cluster'])
plt.xlabel ("Age")
plt.ylabel("Income In thousands")
plt.show()
```

### Output:
<img width="686" height="547" alt="image" src="https://github.com/user-attachments/assets/441d2b76-6cd2-4cb0-8124-857e8377095a" />

<img width="589" height="432" alt="image" src="https://github.com/user-attachments/assets/00217773-aa0b-462b-938f-2a1595546ed2" />

### Result:
The implement Cluster and Visitor Segmentation for Navigation patterns in Python is execute successfully
