# Name:Ramya P
# Register number:212223230168



# Exno:1
Data Cleaning Process

# AIM:
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation:
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm:
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

# Coding and Output:
~~~
import pandas as pd
df=pd.read_csv("/content/SAMPLEIDS (1).csv")
df
~~~
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

![image](https://github.com/user-attachments/assets/083fcbc7-903a-4e66-9bbd-758b056dc793)

df.fillna(method = 'bfill')

![image](https://github.com/user-attachments/assets/bab65d48-8217-45e5-8828-8788ef759f8b)

![image](https://github.com/user-attachments/assets/29cc2fe1-b64e-440b-a819-eec49931996a)
~~~
df_dropped = df.dropna()
df_dropped
~~~

![image](https://github.com/user-attachments/assets/d8d190a8-5a03-4179-9d39-602d76819e59)

df.fillna({'GENDER':'MALE','NAME':'SRI','ADDRESS':'POONAMALEE','M1':98,'M2':87,'M3':92,'TOTAL':305,'AVG':89.999999})

![image](https://github.com/user-attachments/assets/9a6f267e-588c-4050-b434-9f3eee7005cf)

![image](https://github.com/user-attachments/assets/d21af305-0044-408f-a984-10c9824a578e)
~~~
import pandas as pd
ir=pd.read_csv('/content/iris (1).csv')
ir
~~~

![image](https://github.com/user-attachments/assets/c8f83913-9d54-4d3c-8c68-48a0d4cc5b3c)

ir.describe()

![image](https://github.com/user-attachments/assets/d2ed9f44-3148-4c3b-88ca-e3c0a63322d1)
~~~
import pandas as pd
import seaborn as sns
import numpy as np
sns.boxplot(x='sepal_width',data=ir)
~~~

![image](https://github.com/user-attachments/assets/ac1d27ec-8b6f-4d93-a6e0-c31e30d0acb9)
~~~
c1=ir.sepal_width.quantile(0.25)
c3=ir.sepal_width.quantile(0.75)
iq=c3-c1
print(c3)
~~~

![image](https://github.com/user-attachments/assets/b2aa6775-116f-48a2-87c6-778cde058d57)
~~~
rid=ir[((ir.sepal_width<(c1-1.5*iq))|(ir.sepal_width>(c3+1.5*iq)))]
rid['sepal_width']
~~~

![image](https://github.com/user-attachments/assets/1bc86bca-4629-4e12-9a02-fb6fd9ba665b)
~~~
delid=ir[~((ir.sepal_width<(c1-1.5*iq))|(ir.sepal_width>(c3+1.5*iq)))]
delid
~~~

![image](https://github.com/user-attachments/assets/241d8e35-a1de-42c1-b2c8-bd85966c144d)

sns.boxplot(x='sepal_width',data=delid)

![image](https://github.com/user-attachments/assets/2a126e6d-8f1b-4ab0-b9dd-c5c4c46ffa5d)
~~~
import matplotlib.pyplot as plt
import pandas as pd
import numpy as np
import scipy.stats as stats
dataset=pd.read_csv("/content/heights.csv")
dataset
~~~

![image](https://github.com/user-attachments/assets/782165f3-7612-4898-accb-14206d7d715d)
~~~
df = pd.read_csv("heights.csv")
q1 = df['height'].quantile(0.25)
q2 = df['height'].quantile(0.5)
q3 = df['height'].quantile(0.75)
iqr = q3-q1
iqr
~~~

![image](https://github.com/user-attachments/assets/dabc2ba6-9cf2-4179-abe8-91ec692549fb)
~~~
low = q1 - 1.5*iqr
low
~~~

![image](https://github.com/user-attachments/assets/d4ded8c3-1a5c-4c7b-8b67-18ef90b386f9)
~~~
high = q3 + 1.5*iqr
high
~~~

![image](https://github.com/user-attachments/assets/fc672341-6b04-40a6-abb2-2d738e6adbf4)
~~~
df1 = df[((df['height'] >=low)& (df['height'] <=high))]
df1
~~~

![image](https://github.com/user-attachments/assets/542258db-4b03-4b2c-bc16-2a6ec6af6cfe)
~~~
z = np.abs(stats.zscore(df['height']))
z
~~~

![image](https://github.com/user-attachments/assets/78dcb005-46c9-41d9-a008-1be2c5b5da2d)
~~~
df1 = df[z<3]
df1
~~~

![image](https://github.com/user-attachments/assets/9c9e6831-5f43-4794-8704-a5a75e4eafd1)

# Result:
  Thus we have cleaned the data and removed the outliers by detection using IQR and Z-score method. 
























