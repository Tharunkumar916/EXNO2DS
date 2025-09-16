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
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("titanic_dataset.csv")
df

<img width="1398" height="540" alt="Screenshot 2025-09-16 074529" src="https://github.com/user-attachments/assets/4c7f6a26-30f5-4588-afe3-58b55c73cfb9" />

<img width="1412" height="537" alt="Screenshot 2025-09-16 074631" src="https://github.com/user-attachments/assets/da64fd2b-f699-4595-a937-42fbb3b3f7ce" />

df.info()


<img width="1071" height="821" alt="Screenshot 2025-09-16 074757" src="https://github.com/user-attachments/assets/71c4cdce-8150-47bd-8dcd-eafc6ef42585" />

df.describe()


<img width="865" height="708" alt="Screenshot 2025-09-16 074958" src="https://github.com/user-attachments/assets/9c5e46cb-0dd3-4a81-9682-4fd871af7caf" />

df.dtypes


<img width="342" height="502" alt="Screenshot 2025-09-16 075130" src="https://github.com/user-attachments/assets/af560833-99bc-4597-b13a-3b654376095f" />


<img width="274" height="583" alt="Screenshot 2025-09-16 075142" src="https://github.com/user-attachments/assets/a6bfeac6-1281-40be-b4e6-997fbf349a5d" />

df.value_counts()


<img width="1449" height="636" alt="Screenshot 2025-09-16 075307" src="https://github.com/user-attachments/assets/cb8df876-32a4-472d-b115-c684c3fb91aa" />


<img width="1446" height="594" alt="Screenshot 2025-09-16 075357" src="https://github.com/user-attachments/assets/40adf68c-600f-4a18-b40b-e9049e646c19" />

df['Age'].value_counts()


<img width="409" height="583" alt="Screenshot 2025-09-16 075448" src="https://github.com/user-attachments/assets/e97a8dc5-b3b7-41ad-bc6f-21277a2a9354" />


<img width="731" height="577" alt="Screenshot 2025-09-16 075550" src="https://github.com/user-attachments/assets/f326d028-18a1-4990-bb20-88dd196235a9" />

df.shape


<img width="1098" height="65" alt="Screenshot 2025-09-16 075640" src="https://github.com/user-attachments/assets/aeaf9067-b094-4432-a10b-deb677084765" />

df.reset_index(inplace=True)
df.set_index("PassengerId",inplace=True)
df.describe()


<img width="848" height="707" alt="Screenshot 2025-09-16 075749" src="https://github.com/user-attachments/assets/60dca83b-9078-409c-89af-9077d84a0975" />

df.nunique()


<img width="562" height="563" alt="Screenshot 2025-09-16 075842" src="https://github.com/user-attachments/assets/a5ed9cbd-6150-4ca6-964a-1736f666b24c" />


<img width="412" height="541" alt="Screenshot 2025-09-16 075915" src="https://github.com/user-attachments/assets/57109cfb-de28-4044-8adb-b9b230a15e5d" />

sns.countplot(data=df,x="Survived")


<img width="850" height="558" alt="Screenshot 2025-09-16 080004" src="https://github.com/user-attachments/assets/40900c6c-86e4-4c8d-910f-2c0d7cbe89f1" />


<img width="798" height="571" alt="Screenshot 2025-09-16 080034" src="https://github.com/user-attachments/assets/10da7c85-3b27-4545-a5fa-89b8288189d0" />

df.Pclass.unique()


<img width="520" height="52" alt="Screenshot 2025-09-16 080114" src="https://github.com/user-attachments/assets/0c5a0b30-0a83-4f2a-9ff9-29e19a69e3a4" />

df.rename(columns={'Sex':'Gender'},inplace=True)
df


<img width="1406" height="588" alt="Screenshot 2025-09-16 080204" src="https://github.com/user-attachments/assets/53afc57f-17cb-43b8-bf35-2911b206c02d" />


<img width="1440" height="587" alt="Screenshot 2025-09-16 080246" src="https://github.com/user-attachments/assets/03324ec7-010b-4f66-82af-cd79ce946c34" />

sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)


<img width="922" height="630" alt="Screenshot 2025-09-16 080337" src="https://github.com/user-attachments/assets/3547d8ba-d078-4337-a4e8-37b0422a4666" />


<img width="991" height="633" alt="Screenshot 2025-09-16 080413" src="https://github.com/user-attachments/assets/7b1dcd46-a0b1-4817-84de-2281701021cd" />

df.boxplot(column="Age",by="Survived")


<img width="798" height="598" alt="Screenshot 2025-09-16 080454" src="https://github.com/user-attachments/assets/09718bd4-96e9-47f5-b8ef-4ded3ab3d81b" />


<img width="765" height="596" alt="Screenshot 2025-09-16 080530" src="https://github.com/user-attachments/assets/2fef4ea3-91b0-469c-aa18-5a08db0e546d" />

sns.scatterplot(x=df["Age"],y=df["Fare"])


<img width="794" height="558" alt="Screenshot 2025-09-16 080621" src="https://github.com/user-attachments/assets/d53a0fcb-e4ba-42c0-a83d-3dc5d0d1dedf" />


<img width="774" height="559" alt="Screenshot 2025-09-16 080655" src="https://github.com/user-attachments/assets/bab66f3d-c2f3-4b9a-b558-c1bb5546bd6c" />

fig,ax1=plt.subplots(figsize=(8,5))
plt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)


<img width="903" height="546" alt="Screenshot 2025-09-16 080750" src="https://github.com/user-attachments/assets/5741c436-87a9-4e6b-8099-93f10f2e2ff7" />


<img width="895" height="544" alt="Screenshot 2025-09-16 080922" src="https://github.com/user-attachments/assets/a38ad8b8-bdf9-48e8-b255-998fcf0c2fb3" />

plt=sns.boxplot(x="Pclass",y="Age",hue='Gender',data=df)


<img width="787" height="528" alt="Screenshot 2025-09-16 081016" src="https://github.com/user-attachments/assets/129cce41-1ba3-4919-9e6a-f1153b215a22" />


<img width="814" height="526" alt="Screenshot 2025-09-16 081046" src="https://github.com/user-attachments/assets/f0523101-53a6-4f8d-bb00-927e9a6d4cac" />

sns.catplot(data=df,col='Survived',x="Gender",hue="Pclass",kind="count")


<img width="1359" height="625" alt="Screenshot 2025-09-16 081220" src="https://github.com/user-attachments/assets/4bc88df3-c551-4da1-9dab-c33d6529c813" />


<img width="1361" height="636" alt="Screenshot 2025-09-16 081305" src="https://github.com/user-attachments/assets/c71f4651-702b-4c61-9456-76960517c9b3" />

corr=df.select_dtypes(include=np.number).corr()
sns.heatmap(corr,annot=True)


<img width="817" height="544" alt="Screenshot 2025-09-16 081347" src="https://github.com/user-attachments/assets/309b6463-690d-46bb-b459-50d6f35112c9" />


<img width="863" height="537" alt="Screenshot 2025-09-16 081428" src="https://github.com/user-attachments/assets/fa6995ee-e3c4-47ea-b535-cc920b43c368" />
















# RESULT
        Hence the program is successfilly created and output is executed.
