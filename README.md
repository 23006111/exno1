# Exno:1
Data Cleaning Process

# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

# Coding and Output:
import pandas as pd
df=pd.read_csv("/content/SAMPLEIDS (1).csv")
df
![image](https://github.com/user-attachments/assets/614ffc29-2117-4184-afdb-0e85f8fbf2b2)
![image](https://github.com/user-attachments/assets/9e23804e-2719-4a22-a35a-059ebc5bd0e3)

df.isnull().sum()
![image](https://github.com/user-attachments/assets/83567941-006f-454f-bcca-f6a3de9c6ce8)

df.isnull().any()

![image](https://github.com/user-attachments/assets/bde6d829-0fe8-4bc3-98e4-f4bee0ee471a)

df.dropna()

![image](https://github.com/user-attachments/assets/a776c15f-cfa9-41dc-98c7-70eae9a78d92)

df.fillna(0)

![image](https://github.com/user-attachments/assets/0112f608-180a-4a1e-879e-54fa7f88dd2b)

![image](https://github.com/user-attachments/assets/d635de27-35c7-413e-a057-c695b8877f42)

df.fillna(method = 'ffill')

![image](https://github.com/user-attachments/assets/58106212-18d6-4de7-9cd4-e6740333cfa0)










            
# Result
          <<include your Result here>>
