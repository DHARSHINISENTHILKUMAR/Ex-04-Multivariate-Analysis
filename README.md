# Ex-04-Multivariate-Analysis

# AIM:
To perform Multivariate EDA on the given data set.
# Explanation:
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
# Algorithm:
## STEP 1
Import the built libraries required to perform EDA and outlier removal.

## STEP 2
Read the given csv file

## STEP 3
Convert the file into a dataframe and get information of the data.

## STEP 4
Return the objects containing counts of unique values using (value_counts()).

## STEP 5
Plot the counts in the form of Histogram or Bar Graph.

## STEP 6
Use seaborn the bar graph comparison of data can be viewed.

## STEP 7
Find the pairwise correlation of all columns in the dataframe.corr()

## STEP 8
Save the final data set into the file
# Program:
~~~
Name : Divya Bharathi K
Register Number : 212220220011

import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
df=pd.read_csv("SuperStore.csv")
df
df.info()
df.describe()
df.isnull().sum()
df['Postal Code'] = df["Postal Code"].fillna(df['Postal Code'].mode()[0])
df.isnull().sum()
df.dtypes
sns.scatterplot(df['Row ID'],df['Sales'])
states=df.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("SALES")
plt.show()
states=df.loc[:,["State","Row ID"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Row ID")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Row ID",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("ROW ID")
plt.show()
states=df.loc[:,["Segment","Row ID"]]
states=states.groupby(by=["Segment"]).sum().sort_values(by="Row ID")
sns.barplot(x=states.index,y="Row ID",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("SEGMENT")
plt.ylabel=("ROW ID")
plt.show()
sns.barplot(df['Sales'],df['Ship Mode'],hue=df['Region'])
df.corr()
sns.heatmap(df.corr(),annot=True)
~~~
# Output:
## DATA
![image](https://user-images.githubusercontent.com/113699377/230833750-4903b53b-0779-44e2-b884-2142f2d72728.png)
## Data Info
![image](https://user-images.githubusercontent.com/113699377/230833817-f876c620-c152-4f08-a8ac-3a4404745534.png)
## Data Describe
![image](https://user-images.githubusercontent.com/113699377/230833886-25526536-a6f9-4886-83a4-5246a701d5ed.png)
## Checking the null values and cleaning it
![image](https://user-images.githubusercontent.com/113699377/230834091-a12040bc-1c29-4353-80b4-5d626bdac4b6.png)
![image](https://user-images.githubusercontent.com/113699377/230834203-b34b6173-6444-4e6d-bbb2-30caeda81133.png)
## Data types
![image](https://user-images.githubusercontent.com/113699377/230834243-9c5c10b7-13b5-419d-a7e9-338f741d793b.png)
## Scatter Plot
![image](https://user-images.githubusercontent.com/113699377/230834394-b38ba5ee-2391-4d99-9f4a-edd6848d185d.png)
## Barplot
![image](https://user-images.githubusercontent.com/113699377/230834429-ed258cfa-6c96-43ff-8801-13ea478b5bba.png)
![image](https://user-images.githubusercontent.com/113699377/230834510-cfa22608-4235-4bc8-9a61-a72de4484331.png)
![image](https://user-images.githubusercontent.com/113699377/230834543-ed2bface-2f04-4896-a710-c0191916366b.png)
![image](https://user-images.githubusercontent.com/113699377/230834582-9d787235-13f7-44e7-9695-fd1cd954dc0b.png)
## CORRELATION COEFFICIENT INTERPRETATION
![image](https://user-images.githubusercontent.com/113699377/230834641-734f88ad-65bc-4c9c-8b92-98ae74a82ea6.png)
## Heatmap
![image](https://user-images.githubusercontent.com/113699377/230834736-105def8b-8dca-49ce-9f2b-c7b606d1ee29.png)
# Result:
~~~
Thus we have read the given data and performed the multivariate analysis with different types of plots.
~~~





