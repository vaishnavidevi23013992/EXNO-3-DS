## EXNO-3-DS

# AIM:
To read the given data and perform Feature Encoding and Transformation process and save the data to a file.

# ALGORITHM:
STEP 1:Read the given Data.
STEP 2:Clean the Data Set using Data Cleaning Process.
STEP 3:Apply Feature Encoding for the feature in the data set.
STEP 4:Apply Feature Transformation for the feature in the data set.
STEP 5:Save the data to the file.

# FEATURE ENCODING:
1. Ordinal Encoding
An ordinal encoding involves mapping each unique label to an integer value. This type of encoding is really only appropriate if there is a known relationship between the categories. This relationship does exist for some of the variables in our dataset, and ideally, this should be harnessed when preparing the data.
2. Label Encoding
Label encoding is a simple and straight forward approach. This converts each value in a categorical column into a numerical value. Each value in a categorical column is called Label.
3. Binary Encoding
Binary encoding converts a category into binary digits. Each binary digit creates one feature column. If there are n unique categories, then binary encoding results in the only log(base 2)ⁿ features.
4. One Hot Encoding
We use this categorical data encoding technique when the features are nominal(do not have any order). In one hot encoding, for each level of a categorical feature, we create a new variable. Each category is mapped with a binary variable containing either 0 or 1. Here, 0 represents the absence, and 1 represents the presence of that category.

# Methods Used for Data Transformation:
  # 1. FUNCTION TRANSFORMATION
• Log Transformation
• Reciprocal Transformation
• Square Root Transformation
• Square Transformation
  # 2. POWER TRANSFORMATION
• Boxcox method
• Yeojohnson method

# CODING AND OUTPUT:
```
    import pandas as pd
    df=pd.read_csv("/content/Encoding Data (1).csv")
    df
```

![image](https://github.com/user-attachments/assets/d9953b6c-69d5-40be-a6db-913fa5d06c6a)

```
     from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
     pm=['Hot','Warm','Cold']
     e1=OrdinalEncoder(categories=[pm])
     e1.fit_transform(df[["ord_2"]])
```
![image](https://github.com/user-attachments/assets/9d140ba8-4eb6-4abe-8e61-ef8e997d20be)
```
    df['bo2']=e1.fit_transform(df[["ord_2"]])
```
![image](https://github.com/user-attachments/assets/dae1b7ad-89e2-4fb4-a938-9c34517906ee)
```
     le=LabelEncoder()
     dfc=df.copy()
     dfc['ord_2']=le.fit_transform(dfc['ord_2'])
```
![image](https://github.com/user-attachments/assets/0495feff-6f79-49e7-9ab5-c5aa534b9935)
```
      from sklearn.preprocessing import OneHotEncoder
       ohe=OneHotEncoder(sparse=False)
       df2=df.copy()
       enc=pd.DataFrame(ohe.fit_transform(df2[['nom_0']]))
```
![image](https://github.com/user-attachments/assets/30c67614-d2aa-4019-99e2-419f00ef327d)
```
        df2=pd.concat([df2,enc],axis=1)
```
![image](https://github.com/user-attachments/assets/fbc4952e-2785-43ea-9c63-f1bef32040a2)
![image](https://github.com/user-attachments/assets/4ec52166-80e2-4717-8872-cca38aa97fc5)

```
         from category_encoders import BinaryEncoder
         df=pd.read_csv("/content/data.csv")
         be=BinaryEncoder()
         nd=be.fit_transform(df['Ord_2'])
         dfb=pd.concat([df,nd],axis=1)
         dfb1=df.copy()
```
![image](https://github.com/user-attachments/assets/426e05dd-cfd3-4bb4-92c6-35cfbfe92e51)

```
         from category_encoders import TargetEncoder
         te=TargetEncoder()
         cc=df.copy()
         new=te.fit_transform(X=cc["City"],y=cc["Target"])
         cc=pd.concat([cc,new],axis=1)
```
![image](https://github.com/user-attachments/assets/91441007-ae50-4cac-b192-8f412f3b6cc1)

![image](https://github.com/user-attachments/assets/f090f2e8-089b-477d-9536-328a3ca4744f)

![image](https://github.com/user-attachments/assets/06ce705f-34ad-432d-b761-bc686fc8ab74)

![image](https://github.com/user-attachments/assets/cd21f668-621a-47c6-b848-3242ae6d3f72)

![image](https://github.com/user-attachments/assets/d2c91ee7-dc1c-4a52-aaae-01b4d78d9aba)

```
df["Higly Positive Skew_borcox"],parameters=stats.boxcox(df["Highly Positive Skew"])
```
![image](https://github.com/user-attachments/assets/3f66a0c1-9ffe-4ce9-a04d-243f4b619ff9)

```
df["Highly Negative Skew_yeojohnson"],parameters=stats.yeojohnson(df["Highly Negative Skew"])
```
![image](https://github.com/user-attachments/assets/265fd4ad-3ea8-454b-8857-85f19b6e54d4)
```
         from sklearn.preprocessing import QuantileTransformer
         qt=QuantileTransformer(output_distribution='normal')
```
![image](https://github.com/user-attachments/assets/68f685aa-c06f-493e-b291-4b04cae65819)

![image](https://github.com/user-attachments/assets/a1e3a651-2e5e-4a18-bda7-2abb6c06f80c)

![image](https://github.com/user-attachments/assets/234a44b4-d247-4085-98ab-2e944ea20d30)

![image](https://github.com/user-attachments/assets/5a7f0984-eb19-484f-bc76-001db65836b3)

![image](https://github.com/user-attachments/assets/388bfafc-6016-43ff-aaa5-de8e92057f55)

![image](https://github.com/user-attachments/assets/f36d49d3-10e0-4db9-bb6e-1ed3ffdef770)

![image](https://github.com/user-attachments/assets/1ddb8e9a-817a-4a27-80c1-c8fa5fff522e)

### RESULT:
Thus To read the given data and perform Feature Encoding and Transformation process and save the data to a file has successfully executed
       
