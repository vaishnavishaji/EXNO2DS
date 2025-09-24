# EXNO2DS
# AIM:
To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
```
import pandas as pd
import numpy as np
import seaborn as sns
a=pd.read_csv("/content/titanic_dataset.csv")
a
```
<img width="1418" height="476" alt="489383243-c89771fb-53da-4d07-aa01-e4e9b154a924" src="https://github.com/user-attachments/assets/70a22f9a-74db-42d6-96b0-06d6eaa4954d" />

```
a.info()
```
<img width="435" height="392" alt="489383501-5d30d6c6-eb87-4e0d-9855-57bfe399d2a2" src="https://github.com/user-attachments/assets/97e630fb-940a-4893-b24c-ccd8a8fea145" />

```
a.describe()
```
<img width="815" height="334" alt="489383572-f99db55d-afdf-4260-a39a-bdf123365ced" src="https://github.com/user-attachments/assets/75608be7-a104-41e8-98a0-db31f816fe66" />

```
a.dtypes
```
<img width="278" height="507" alt="489383904-362be858-cb36-4dfc-828a-6af53ae7a6a8" src="https://github.com/user-attachments/assets/70688f56-a49c-49a0-9469-8387a251c345" />

```
a.shape
```
<img width="170" height="47" alt="489383966-0b3b0954-2ddc-4066-ba1a-1bb2459e0aec" src="https://github.com/user-attachments/assets/d87eeed5-55b1-46da-9661-088612e58006" />

```
a.value_counts()
```
<img width="1393" height="550" alt="489384191-b1d24c93-59cf-4764-952e-a73e4f95f19b" src="https://github.com/user-attachments/assets/29471218-2c47-4c17-89d8-cbbb71891d67" />

```
a['Age'].value_counts()
```
<img width="239" height="755" alt="489384323-9fc4fe89-be07-46ef-844b-292ba8ee0875" src="https://github.com/user-attachments/assets/1ec9c45f-884c-4df0-ad49-c9e51f01ef2e" />

```
a.set_index("PassengerId",inplace=True)
a
```
<img width="474" height="343" alt="489384527-49c6e447-bbed-4a12-a327-c94af8c3f5fa" src="https://github.com/user-attachments/assets/be9ff243-b5ca-4e8d-b160-57e3d7a9cade" />

```
a.nunique()
```
<img width="255" height="403" alt="489384609-36482443-d33e-4ebc-809b-b9a94e12d888" src="https://github.com/user-attachments/assets/db9ccc9e-de40-4596-92a9-dfc2f99d217b" />

```
sns.countplot(data=a,x='Age')
```
<img width="574" height="423" alt="489384920-9dacbf24-31f5-4e90-a406-cb45b64e2f93" src="https://github.com/user-attachments/assets/1d7a5c73-9842-4e6f-a3e4-88b02cd54847" />

```
a.rename(columns={'Sex':'Gender'},inplace=True)
a
```
<img width="1128" height="410" alt="489385028-bd99cc57-fad1-4ba0-a80a-c2b3cefc63a4" src="https://github.com/user-attachments/assets/d089056b-75a6-4ca6-bd84-23778223302d" />

```
sns.catplot(x="Gender",col="Survived",kind="count",data=a)
```
<img width="1096" height="489" alt="489392454-6b029986-65a8-4101-939e-ae603b057065" src="https://github.com/user-attachments/assets/b764d156-e58a-4769-b03e-0bd57ce455f8" />

```
a.boxplot(column="Age",by="Survived")
```
<img width="578" height="457" alt="489392737-f94045bf-92e3-4e73-84c0-999afe49fd23" src="https://github.com/user-attachments/assets/987dd5c3-ba9e-408a-8d4e-25ab563aac6a" />

```
sns.scatterplot(x=a["Age"],y=a["Fare"])
```
<img width="593" height="433" alt="489392853-641b0688-a275-4437-a57c-32a6814b4d97" src="https://github.com/user-attachments/assets/0195b350-4fc9-4d26-b3b4-2060449e8107" />

```
plt=sns.boxplot(x="Pclass",y="Age",hue="Gender",data=a)
```
<img width="585" height="421" alt="489392987-6158f3c7-d1f2-4470-8eb9-7fbf0af4618a" src="https://github.com/user-attachments/assets/e17c1dd9-997b-4e15-8f8a-6770221e87d1" />

```
sns.catplot(x="Pclass",y="Age",hue="Gender",col="Survived",kind="box",data=a)
```
<img width="593" height="276" alt="489393123-289fa90a-5550-480a-b620-c712b1ab724d" src="https://github.com/user-attachments/assets/c6249d0a-fc3c-437a-91d0-1b70a8a5e07b" />

```

corr=a.corr(numeric_only=True)
sns.heatmap(corr,annot=True)
```
<img width="549" height="413" alt="489394222-dff991b8-1632-4708-a4b3-3ab767bd90e3" src="https://github.com/user-attachments/assets/f19c9a81-1129-4f7b-9640-faff526efa48" />




























































# RESULT
Exploratory Data Analysis on the given data set is successful
