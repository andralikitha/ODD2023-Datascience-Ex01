# Ex-01_DS_Data_Cleansing


## AIM
To read the given data and perform data cleaning and save the cleaned data to a file. 

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. 
Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information. 

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Get the information about the data
### STEP 3
Remove the null values from the data
### STEP 4
Save the Clean data to the file

# CODE and OUTPUT


import pandas as pd

df=pd.read_csv("/content/SAMPLEDS - Sheet1.csv")

df

![image](https://github.com/andralikitha/ODD2023-Datascience-Ex01/assets/131592130/c4bc9aba-4dd3-4579-aaf6-914e265c979a)


df.shape

![image](https://github.com/andralikitha/ODD2023-Datascience-Ex01/assets/131592130/aab1b69c-02aa-42ca-a010-173a597ab2ca)


df.describe()

![image](https://github.com/andralikitha/ODD2023-Datascience-Ex01/assets/131592130/5c6f059d-bbf0-4dcb-9fb4-21184f35a326)


df.info()

![image](https://github.com/andralikitha/ODD2023-Datascience-Ex01/assets/131592130/070ee5ad-3c7a-49aa-9ada-6ef89cdb4671)


df.isnull().sum()

![image](https://github.com/andralikitha/ODD2023-Datascience-Ex01/assets/131592130/06f0e8e1-2115-408b-abff-db39d9426c43)


df.dropna(how='any').shape

![image](https://github.com/andralikitha/ODD2023-Datascience-Ex01/assets/131592130/481b2fbb-ce06-41ec-aa7b-57270df89e2e)


x=df.dropna(how='any')

x

![image](https://github.com/andralikitha/ODD2023-Datascience-Ex01/assets/131592130/2d3ba166-a8a1-4716-91ab-ee35f256574e)


df.dropna(how='all').shape

![image](https://github.com/andralikitha/ODD2023-Datascience-Ex01/assets/131592130/561d4a61-3664-49aa-a190-16ee80913d4a)


df

![image](https://github.com/andralikitha/ODD2023-Datascience-Ex01/assets/131592130/5c0def34-e4cd-4cc0-9376-b2852cd935b4)


tot=df.dropna(subset=['TOTAL'],how='any')

tot

![image](https://github.com/andralikitha/ODD2023-Datascience-Ex01/assets/131592130/853196b0-04c4-4cd5-93f8-a478e5e2f2f9)


tot=df.dropna(subset=['M1','M2','M3','M4'],how='any')

tot

![image](https://github.com/andralikitha/ODD2023-Datascience-Ex01/assets/131592130/e03b6204-cf51-4d5a-b1ac-75a86e5b98d0)


df.fillna(0)

![image](https://github.com/andralikitha/ODD2023-Datascience-Ex01/assets/131592130/081e93be-652b-4eba-a719-87c97e7e9e4c)


df

![image](https://github.com/andralikitha/ODD2023-Datascience-Ex01/assets/131592130/4603fb4e-117c-4691-9a60-a9cd9028829b)


df.fillna(method='ffill')

![image](https://github.com/andralikitha/ODD2023-Datascience-Ex01/assets/131592130/2ead8b63-5230-4878-943f-bdf6333a9505)


df.interpolate()

![image](https://github.com/andralikitha/ODD2023-Datascience-Ex01/assets/131592130/e800cb9b-2c00-45f0-bbae-7bf645ca8ca0)


mn=df.TOTAL.mean()

mn

![image](https://github.com/andralikitha/ODD2023-Datascience-Ex01/assets/131592130/abf457b0-5a1d-4faf-b23c-dca2b9a5448a)


df.TOTAL.fillna(mn,inplace=True)

df

![image](https://github.com/andralikitha/ODD2023-Datascience-Ex01/assets/131592130/3b53c51c-b2ee-42d6-9965-ae5a4555a16b)


l=df.M1.interpolate()

l

![image](https://github.com/andralikitha/ODD2023-Datascience-Ex01/assets/131592130/bffa917c-19f4-4a5e-9561-543c14bd3c9d)


df.M1.fillna(l,inplace=True)

df

![image](https://github.com/andralikitha/ODD2023-Datascience-Ex01/assets/131592130/e73006ab-113b-4609-9059-d104b38f3af6)


mn=df.TOTAL.median()
mn

![image](https://github.com/andralikitha/ODD2023-Datascience-Ex01/assets/131592130/6f21f8c0-9543-44b6-b6f0-60cf94171639)


mn=df.TOTAL.mode()
mn

![image](https://github.com/andralikitha/ODD2023-Datascience-Ex01/assets/131592130/301a7556-4ec3-4478-9115-ae841a3dfc09)


df.isnull()

![image](https://github.com/andralikitha/ODD2023-Datascience-Ex01/assets/131592130/3fc54b9f-368e-48e8-8795-3969ed0933f7)


df.duplicated()

![image](https://github.com/andralikitha/ODD2023-Datascience-Ex01/assets/131592130/3466cd52-965a-4bcf-93df-fd134c28d959)


df.drop_duplicates(inplace=True)

df

![image](https://github.com/andralikitha/ODD2023-Datascience-Ex01/assets/131592130/2671086f-bf44-4caf-96b4-8a721be78ed9)


df['cd']=pd.to_datetime(df['DOB'])

df

![image](https://github.com/andralikitha/ODD2023-Datascience-Ex01/assets/131592130/61f78b9f-ec49-4141-88db-ee9be0053d00)


for x in df.index:
  if df.loc[x,"AVG"]>100:
    df.drop(x,inplace=True)

df

![image](https://github.com/andralikitha/ODD2023-Datascience-Ex01/assets/131592130/2391fa59-ee13-4abe-ac1e-5608332700a8)



RESULT:

Thus the given data perform data cleaning and save the cleaned data to a file are successfully executed and hence proved
