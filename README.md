# Ex-07-Data-Visualization-

## AIM
To Perform Data Visualization on the given dataset and save the data to a file. 

# Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature generation and selection techniques to all the features of the data set
### STEP 4
Apply data visualization techniques to identify the patterns of the data.
# CODE:
```
#Reading the given dataset

import pandas as pd
df=pd.read_csv("Superstore.csv",encoding='unicode_escape')

df.head()

#Data Visualization using Seaborn

import seaborn as sns
from matplotlib import pyplot as plt

#1.Line Plot

plt.figure(figsize=(9,6))
sns.lineplot(x="Segment",y="Region",data=df,marker='o')
plt.xticks(rotation = 90)

sns.lineplot(x='Ship Mode',y='Category', hue ="Segment",data=df)

sns.lineplot(x="Category",y="Sales",data=df,marker='o')

#2.Scatterplot

sns.scatterplot(x='Category',y='Sub-Category',data=df)

sns.scatterplot(x='Category', y='Sub-Category', hue ="Segment",data=df)

plt.figure(figsize=(10,7))
sns.scatterplot(x="Region",y="Sales",data=df)
plt.xticks(rotation = 90)

#3.Boxplot

sns.boxplot(x="Sub-Category",y="Discount",data=df)

sns.boxplot( x="Profit", y="Category",data=df)

#4.Violin Plot

sns.violinplot(x="Profit",data=df)

#5.Barplot

sns.barplot(x="Sub-Category",y="Sales",data=df)
plt.xticks(rotation = 90)

sns.barplot(x="Category",y="Sales",data=df)
plt.xticks(rotation = 90)

#6.Pointplot

sns.pointplot(x=df["Quantity"],y=df["Discount"])

#7.Count plot

sns.countplot(x="Category",data=df)

sns.countplot(x="Sub-Category",data=df)

#8.Histogram

sns.histplot(data=df,x ='Ship Mode',hue='Sub-Category')

#9.KDE Plot

sns.kdeplot(x="Profit", data = df,hue='Category')

#Data Visualization Using MatPlotlib

#1.Plot

plt.plot(df['Category'], df['Sales'])
plt.show()

#2.Heatmap

df.corr()
plt.subplots(figsize=(12,7))
sns.heatmap(df.corr(),annot=True)

#3.Piechart

df1=df.groupby(by=["Ship Mode"]).sum()
labels=[]
for i in df1.index:
    labels.append(i)
colors=sns.color_palette("bright")
plt.pie(df1["Sales"],labels=labels,autopct="%0.0f%%")
plt.show()

df3=df.groupby(by=["Category"]).sum()
labels=[]
for i in df3.index:
    labels.append(i) 
plt.figure(figsize=(8,8))
colors = sns.color_palette('pastel')
plt.pie(df3["Profit"],colors = colors,labels=labels, autopct = '%0.0f%%')
plt.show()

#4.Histogram

plt.hist(df["Sub-Category"],facecolor="peru",edgecolor="blue",bins=10)
plt.show()

#5.Bargraph

plt.bar(df.index,df['Category'])
plt.show()

#6.Scatterplot

plt.scatter(df["Region"],df["Profit"], c ="blue")
plt.show() 

#7.Boxplot

plt.boxplot(x="Sales",data=df)
plt.show()
```
# OUTPUT:
# Reading the given dataset
### ![image](https://github.com/Irenejecinthamerlin/Ex-08-Data-Visualization-/assets/128350225/a5cf8460-d6e2-4c32-857a-155c23db9d55)
# Data Visualization Using Seaborn:
## 1.Line Plot
### ![image](https://github.com/Irenejecinthamerlin/Ex-08-Data-Visualization-/assets/128350225/b522ebe2-549c-4c4f-8d18-a60efd41e0ca)
### ![image](https://github.com/Irenejecinthamerlin/Ex-08-Data-Visualization-/assets/128350225/95f217c0-82ce-4e33-8140-e750212c3879)
## 2.Scatterplot
### ![image](https://github.com/Irenejecinthamerlin/Ex-08-Data-Visualization-/assets/128350225/fdd18f81-e9a4-4073-b369-709ad653812e)
### ![image](https://github.com/Irenejecinthamerlin/Ex-08-Data-Visualization-/assets/128350225/2f43a897-81fa-4e3b-be35-9094a2a5387f)
## 3.Boxplot:
### ![image](https://github.com/Irenejecinthamerlin/Ex-08-Data-Visualization-/assets/128350225/d794e1a7-2db9-4445-88f0-6bac8ae8873c)
## 4.Violin Plot
### ![image](https://github.com/Irenejecinthamerlin/Ex-08-Data-Visualization-/assets/128350225/5fb12215-4e53-4868-be78-edff0ac3f139)
## 5.Barplot
### ![image](https://github.com/Irenejecinthamerlin/Ex-08-Data-Visualization-/assets/128350225/8b745382-aa1e-477f-88d4-aebc08508107)
### ![image](https://github.com/Irenejecinthamerlin/Ex-08-Data-Visualization-/assets/128350225/a89d25e0-b968-43e4-909d-bf0eef992d89)
### ![image](https://github.com/Irenejecinthamerlin/Ex-08-Data-Visualization-/assets/128350225/8f2ec502-36ea-4f4e-a972-bdaebfcf1095)
## 6.Pointplot
### ![image](https://github.com/Irenejecinthamerlin/Ex-08-Data-Visualization-/assets/128350225/d8d84742-c2b8-4a6a-8866-496bab6a1ac2)
## 7.Count plot
### ![image](https://github.com/Irenejecinthamerlin/Ex-08-Data-Visualization-/assets/128350225/00290797-8118-4ea3-878d-441d67718335)
### ![image](https://github.com/Irenejecinthamerlin/Ex-08-Data-Visualization-/assets/128350225/4eac2829-af63-40b4-adce-f053fd04439d)
## 8.Histogram
### ![image](https://github.com/Irenejecinthamerlin/Ex-08-Data-Visualization-/assets/128350225/cf13a9b2-f413-414c-ae4a-b58762a487cd)
## 9.KDE Plot
### ![image](https://github.com/Irenejecinthamerlin/Ex-08-Data-Visualization-/assets/128350225/374bdeff-96ff-4877-a8ad-4af3777864cd)
# Data Visualization Using Matplotlib:
## 1.Plot:
### ![image](https://github.com/Irenejecinthamerlin/Ex-08-Data-Visualization-/assets/128350225/aa6795ca-7ffb-492c-9f35-5792a5bec502)
## 2.Heatmap: 
### ![image](https://github.com/Irenejecinthamerlin/Ex-08-Data-Visualization-/assets/128350225/d271b434-e954-4429-a405-9f9a62258f4e)
## 3.Piechart:
### ![image](https://github.com/Irenejecinthamerlin/Ex-08-Data-Visualization-/assets/128350225/56434557-154b-4043-8bcf-7a16d2a5199f)
### ![image](https://github.com/Irenejecinthamerlin/Ex-08-Data-Visualization-/assets/128350225/2d7bd7b3-6464-4bf9-a2de-6e4151195f4e)
## 4.Histogram:
### ![image](https://github.com/Irenejecinthamerlin/Ex-08-Data-Visualization-/assets/128350225/f2fa4fe2-addb-46d5-954c-3d5fe2d259b0)
## 5.Bargraph:
### ![image](https://github.com/Irenejecinthamerlin/Ex-08-Data-Visualization-/assets/128350225/31752be8-a21d-4afe-aeb8-b0cb290a53dc)
## 6.Scatterplot:
### ![image](https://github.com/Irenejecinthamerlin/Ex-08-Data-Visualization-/assets/128350225/2509ccc2-9494-4807-9f00-328086d30868)
## 7.Boxplot:
### ![image](https://github.com/Irenejecinthamerlin/Ex-08-Data-Visualization-/assets/128350225/d17a53c7-1962-4751-bf51-013d83e2236e)
# Result:
Hence,Data Visualization is applied on the complex dataset using libraries like Seaborn and Matplotlib successfully and the data is saved to file


