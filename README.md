# PF-project
import pandas as pd
df = pd.read_csv("data.csv")
df.columns
## Data Cleaning
df.dropna()
df.dropna(inplace=True)
## Duplications
df.duplicated()
pd.set_option("display.max_rows",None)
pd.set_option("display.max_columns",None)
df.duplicated()
## Add column
df['Tax']=100
df
df.drop(columns=['Tax'],inplace=True)
df
df.head(6)
## Shape of the Data
df.shape
df.tail(6)
## Sample of the data
df.sample(6)
## Rename columns
df.columns
df.rename(columns={"Geography":"Country"})
df.head(6)
## Data information
df.info()
## Describe
df.describe()
a = df.describe(include="all")
a.loc[["std","mean"]]
a.iloc[[0,1,2,3,4,5,6]]
pd.set_option('display.max_rows',None)
pd.set_option('display.max_columns',None)
df[["Age","Balance"]]
## Mean Mode Median
df["CreditScore"].mean()
df["CreditScore"].mode()
df["CreditScore"].median()
df["Gender"].value_counts()
## plots
df['Gender'].value_counts().plot(kind="bar",title="Gender",color="red")
df['Gender'].value_counts().plot(kind="line",title="Gender",color="red")
df['Gender'].value_counts().plot(kind="hist",title="Gender",color="red")
df['Gender'].value_counts().plot(kind="pie",title="Gender",color="red")
df['Gender'].value_counts().plot(kind="barh",title="Gender",color="red")
df['Gender'].value_counts().plot(kind="kde",title="Gender",color="red")
## Finding null values
df.isnull().sum()
df[df["Card Type"].isnull()]
df["final_Age"] = df["Age"].fillna(df["Age"].mean())
df[df["Age"].isnull()]
## relation 
df.groupby("Gender").describe()
df.to_csv("data2.csv")
df = pd.read_csv("data.csv")
df
df.to_excel("newdata.xlsx", sheet_name="newsheet")
pip install openpyxl
